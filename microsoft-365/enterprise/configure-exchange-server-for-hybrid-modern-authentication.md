---
title: Cómo configurar Exchange Server local para usar la autenticación moderna híbrida
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar un servidor de Exchange local para usar la autenticación moderna híbrida (HMA), lo que le ofrece una autenticación y autorización de usuario más seguras.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 291c7c220fb4ee56db2a42409d5b81724de5da32
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693589"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Cómo configurar Exchange Server local para usar la autenticación moderna híbrida

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*

La autenticación moderna híbrida (HMA) es un método de administración de identidades que ofrece autenticación y autorización de usuario más seguras, y está disponible para las implementaciones híbridas locales de Exchange Server.
  
## <a name="fyi"></a>FYI

Antes de empezar, debo llamar a:
  
- HMA de autenticación moderna híbrida \>

- T local de Exchange \>

- Exo de Exchange Online \>

Además, *si un gráfico de este artículo tiene un objeto que está "atenuado" o "atenuado", lo que significa que el elemento que se muestra en gris no se incluye en la configuración específica del HMA* .
  
## <a name="enabling-hybrid-modern-authentication"></a>Habilitación de la autenticación moderna híbrida

La activación de la HMA significa:
  
1. Asegúrese de que cumple los requisitos previos antes de empezar.

1. Dado que muchos **requisitos previos** son comunes para Skype empresarial y Exchange, introducción a la [autenticación moderna híbrida y requisitos previos para su uso con Skype empresarial local y servidores de Exchange](hybrid-modern-auth-overview.md). Hágalo antes de empezar con cualquiera de los pasos de este artículo.

1. Agregar direcciones URL de servicios web locales como **nombres principales de servicio (SPN)** en Azure ad.

1. Asegurarse de que todos los directorios virtuales están habilitados para HMA

1. Comprobación del objeto de servidor de autenticación de EvoSTS

1. Habilitación de la HMA en EXCH

 **Nota:** ¿Su versión de Office es compatible con MA? Vea [Cómo funciona la autenticación moderna para las aplicaciones cliente de office 2013 y office 2016](modern-auth-for-office-2013-and-2016.md).
  
## <a name="make-sure-you-meet-all-the-prerequisites"></a>Asegurarse de que cumple todos los requisitos previos

Dado que muchos requisitos previos son comunes para Skype empresarial y Exchange, revise la [Introducción a la autenticación moderna híbrida y los requisitos previos para usarlo con Skype empresarial y los servidores de Exchange locales](hybrid-modern-auth-overview.md). Hágalo  *antes*  de empezar con cualquiera de los pasos de este artículo.
  
## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Agregar direcciones URL de servicios web locales como SPN en Azure AD

Ejecute los comandos que asignan las direcciones URL del servicio Web local como SPN de Azure AD. Los equipos cliente y los dispositivos usan los SPN durante la autenticación y la autorización. Todas las direcciones URL que se pueden usar para conectarse de local a Azure Active Directory (Azure AD) deben registrarse en Azure AD (esto incluye los espacios de nombres internos y externos).
  
En primer lugar, reúna todas las direcciones URL que necesite agregar en AAD. Ejecute estos comandos de forma local:
  
```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```
    
Asegúrese de que las direcciones URL a las que se pueden conectar los clientes aparecen como nombres de entidad de servicio HTTPS en AAD.
  
1. En primer lugar, conéctese a AAD con [estas instrucciones](connect-to-microsoft-365-powershell.md).

 **Nota:** Debe usar la opción _Connect-MsolService_ de esta página para poder usar el comando siguiente.

2. Para las direcciones URL relacionadas con Exchange, escriba el siguiente comando:

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
```

Tome nota de (y captura de pantalla para comparaciones posteriores) el resultado de este comando, que debe incluir un https://  *Autodiscover.yourdomain.com*  y https://  *mail.yourdomain.com* dirección URL, pero en su mayoría consta de SPN que comienzan con 00000002-0000-0ff1-ce00-000000000000/. Si hay direcciones URL de https://de su local que no se encuentran, tendrá que agregar esos registros específicos a esta lista.
  
3. Si no ve los registros interno y externo de MAPI/HTTP, EWS, ActiveSync, OAB y detección automática en esta lista, debe agregarlos mediante el siguiente comando (las direcciones URL de ejemplo son ' `mail.corp.contoso.com` ' y ' `owa.contoso.com` '), pero debe **reemplazar las direcciones URL de ejemplo con las suyas** : <br/>
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
$x.ServicePrincipalnames.Add("https://owa.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```

4. Compruebe que los nuevos registros se han agregado ejecutando el comando Get-MsolServicePrincipal del paso 2 de nuevo y observando los resultados. Compare la lista o la captura de pantalla de antes con la nueva lista de SPN (también puede mostrar una captura de pantalla de la nueva lista de sus registros). Si ha tenido éxito, verá las dos nuevas direcciones URL en la lista. Siguiendo nuestro ejemplo, la lista de SPN ahora incluirá las direcciones URL específicas  `https://mail.corp.contoso.com`  y  `https://owa.contoso.com` . 
  
## <a name="verify-virtual-directories-are-properly-configured"></a>Comprobar que los directorios virtuales están correctamente configurados

Ahora, compruebe que OAuth está correctamente habilitado en Exchange en todos los directorios virtuales que Outlook puede usar mediante la ejecución de los siguientes comandos:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth* 
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Compruebe el resultado para asegurarse de que **OAuth** está habilitado en cada uno de estos VDirs, que tendrá un aspecto similar al siguiente (y que lo clave que debe analizar es "OAuth"):

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```
  
Si OAuth no está en ningún servidor y en cualquiera de los cuatro directorios virtuales, debe agregarlo mediante los comandos pertinentes antes de continuar ([set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-mapivirtualdirectory?view=exchange-ps), [set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-webservicesvirtualdirectory?view=exchange-ps), [set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/email-addresses-and-address-books/set-oabvirtualdirectory?view=exchange-ps)y [set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-autodiscovervirtualdirectory?view=exchange-ps)).
  
## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Confirmar que el objeto de servidor de autenticación de EvoSTS está presente

Vuelva al shell de administración de Exchange local para este último comando. Ahora puede validar que su entorno local tiene una entrada para el proveedor de autenticación de evoSTS:
  
```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

El resultado debe mostrar un AuthServer del nombre EvoSts y el estado "habilitado" debe ser true. Si no ve esto, debe descargar y ejecutar la versión más reciente del Asistente para la configuración híbrida.
  
 **Importante** Si está ejecutando Exchange 2010 en su entorno, no se creará el proveedor de autenticación EvoSTS. 
  
## <a name="enable-hma"></a>Habilitar HMA

Ejecute el siguiente comando en el shell de administración de Exchange, local:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true  
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a>Comprueba

Una vez habilitada la HMA, el próximo inicio de sesión de un cliente usará el nuevo flujo de autenticación. Tenga en cuenta que, al activar la HMA no se activará una nueva autenticación para ningún cliente. Los clientes se vuelven a autenticar en función de la duración de los tokens de autenticación o de los certificados que tienen.
  
También debe mantener presionada la tecla CTRL al mismo tiempo que se hace clic en el icono del cliente de Outlook (también en la bandeja de notificaciones de Windows) y en "estado de conexión". Busque la dirección SMTP del cliente en un "authn" tipo de "portador \* ", que representa el token del portador usado en OAuth.
  
 **Nota:** ¿Necesita configurar Skype empresarial con HMA? Necesitará dos artículos: uno que muestre las [topologías admitidas](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)y otro que muestre [Cómo realizar la configuración](configure-skype-for-business-for-hybrid-modern-authentication.md).
 
## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Uso de híbridos modernos de autenticación con Outlook para iOS y Android

Si es un cliente local que usa Exchange Server en TCP 443, debe tener en la lista blanca los siguientes intervalos de direcciones IP:  <BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR>

## <a name="related-topics"></a>Temas relacionados

[Requisitos de configuración de autenticación moderna para la transición de Office 365 dedicado/ITAR a vNext](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)