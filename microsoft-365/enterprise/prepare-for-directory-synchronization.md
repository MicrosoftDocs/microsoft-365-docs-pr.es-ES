---
title: Prepararse para la sincronización de directorios de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Describe cómo preparar el aprovisionamiento de usuarios a Microsoft 365 mediante la sincronización de directorios y las ventajas a largo plazo del uso de este método.
ms.openlocfilehash: cf5afc05b8273974c069662c2b887092fdd20b96
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696579"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Prepararse para la sincronización de directorios de Microsoft 365

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Microsoft 365 Enterprise.*

Entre las ventajas de la identidad híbrida y la sincronización de directorios de su organización se incluyen:
  
- Reducción de los programas administrativos de la organización
- Habilitar opcionalmente escenario de inicio de sesión único
- Automatizar cambios de cuenta en Microsoft 365
    
Para obtener más información acerca de las ventajas del uso de la sincronización de directorios, consulte [Guía básica de sincronización de directorios]( https://go.microsoft.com/fwlink/p/?LinkId=525398) e [identidad híbrida para Microsoft 365](plan-for-directory-synchronization.md).

Sin embargo, la sincronización de directorios requiere planeación y preparación para garantizar que los servicios de dominio de Active Directory (AD DS) se sincronicen con el inquilino de Azure Active Directory (Azure AD) de la suscripción a Microsoft 365 con un mínimo de errores. 

Siga estos pasos en orden para obtener los mejores resultados.
  
## <a name="1-directory-cleanup-tasks"></a>1. tareas de limpieza de directorios

Antes de sincronizar AD DS con su espacio empresarial de Azure AD, debe limpiar su AD DS.

> [!IMPORTANT]
> Si no realiza la limpieza de AD DS antes de sincronizar, puede haber un efecto negativo significativo en el proceso de implementación. Puede tardar días, o incluso semanas, en pasar por el ciclo de sincronización de directorios, identificar errores y volver a sincronizar. 
  
En AD DS, complete las siguientes tareas de limpieza para cada cuenta de usuario a la que se asignará una licencia de 365 de Microsoft:
  
1. Asegúrese de que haya una dirección de correo electrónico válida y única en el atributo **proxyAddresses** . 
  
2. Quite los valores duplicados en el atributo **proxyAddresses** . 
    
3.  Si es posible, asegúrese de un valor válido y único para el atributo **userPrincipalName** en el objeto de **usuario** del usuario. Para obtener una mejor experiencia de sincronización, asegúrese de que el UPN de AD DS coincida con el UPN de Azure AD. Si un usuario no tiene un valor para el atributo **userPrincipalName** , el objeto de **usuario** debe contener un valor válido y único para el atributo **samAccountName** . Quite los valores duplicados en el atributo **userPrincipalName** . 
    
4. Para un uso óptimo de la lista global de direcciones (GAL), asegúrese de que la información de los siguientes atributos de la cuenta de usuario de AD DS es correcta:
    
  - givenName
  - surname
  - displayName
  - Puesto
  - Departamento
  - Oficina
  - Teléfono de la oficina
  - Teléfono móvil
  - Número de fax
  - Dirección
  - Ciudad
  - Provincia
  - Código postal
  - País o región
    
## <a name="2-directory-object-and-attribute-preparation"></a>2. preparación del objeto y el atributo del directorio

La correcta sincronización de directorios entre AD DS y Microsoft 365 requiere que los atributos de AD DS estén preparados correctamente. Por ejemplo, debe asegurarse de que no se usan caracteres específicos en determinados atributos que se sincronizan con el entorno de Microsoft 365. Los caracteres inesperados no causan un error en la sincronización de directorios, pero podrían devolver una advertencia. Caracteres no válidos, se producirá un error en la sincronización de directorios.
  
También se producirá un error en la sincronización de directorios si algunos de los usuarios de AD DS tienen uno o más atributos duplicados. Cada usuario debe tener atributos únicos.
  
A continuación se enumeran los atributos que debe preparar:
  
- **displayName**
    
  - Si el atributo existe en el objeto de usuario, se sincronizará con Microsoft 365.
  - Si este atributo existe en el objeto de usuario, debe haber un valor para él. Es decir, el atributo no debe estar en blanco.
  - Número máximo de caracteres: 256
    
- **givenName**
    
  - Si el atributo existe en el objeto de usuario, se sincronizará con Microsoft 365, pero Microsoft 365 no lo necesita ni lo usa.
  - Número máximo de caracteres: 64
    
- **tales**
    
  - El valor del atributo debe ser único dentro del directorio.
    
    > [!NOTE]
    > Si hay valores duplicados, se sincroniza el primer usuario con el valor. Los usuarios posteriores no aparecerán en Microsoft 365. Debe modificar el valor de Microsoft 365 o modificar ambos valores en AD DS para que ambos usuarios aparezcan en Microsoft 365. 
  
- **mailNickname** (alias de Exchange) 
    
  - El valor del atributo no puede comenzar con un punto (.).
  - El valor del atributo debe ser único dentro del directorio.
  
    > [!NOTE]
    > El carácter de subrayado ("_") en el nombre sincronizado indica que el valor original de este atributo contiene caracteres no válidos. Para obtener más información sobre este atributo, consulte [Exchange alias Attribute](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps).
    >
      
- **proxyAddresses**
    
  - Atributo de varios valores
  - Número máximo de caracteres por valor: 256
  - El valor del atributo no debe contener un espacio.
  - El valor del atributo debe ser único dentro del directorio.
  - Caracteres no válidos: \< \> ();, [] "'
    
    Tenga en cuenta que los caracteres no válidos se aplican a los caracteres que siguen al delimitador de tipo y ":", de modo que SMTP:User@contso.com está permitido, pero SMTP:user:M@contoso.com no lo es.
    
    > [!IMPORTANT]
    > Todas las direcciones de Protocolo simple de transferencia de correo (SMTP) deben cumplir con los estándares de mensajería de correo electrónico. Si hay direcciones duplicadas o no deseadas, consulte el tema [de la ayuda quitar direcciones proxy duplicadas y no deseadas en Exchange](https://go.microsoft.com/fwlink/?LinkId=293860). 
  
- **sAMAccountName**
    
  - Número máximo de caracteres: 20
  - El valor del atributo debe ser único dentro del directorio.
  - Caracteres no válidos: [\ "|,/: \< \> + =;? \* ']
  - Si un usuario tiene un atributo **samAccountName** no válido, pero tiene un atributo **userPrincipalName** válido, se crea la cuenta de usuario en Microsoft 365. 
  - Si **samAccountName** y **userPrincipalName** no son válidos, se debe actualizar el atributo **userPrincipalName** de AD DS. 
    
- **SN** (Apellidos) 
    
  - Si el atributo existe en el objeto de usuario, se sincronizará con Microsoft 365, pero Microsoft 365 no lo necesita ni lo usa.
    
- **targetAddress**
    
    Es necesario que el atributo **targetAddress** (por ejemplo, SMTP:Tom@contoso.com) que se rellene para el usuario deba aparecer en la GAL de Microsoft 365. En los escenarios de migración de mensajería de terceros, sería necesaria la extensión de esquema de Microsoft 365 para AD DS. La extensión de esquema de 365 de Microsoft también agrega otros atributos útiles para administrar los objetos de Microsoft 365 que se rellenan con una herramienta de sincronización de directorios de AD DS. Por ejemplo, se agregaría el atributo **msExchHideFromAddressLists** para administrar los buzones ocultos o los grupos de distribución. 
   
  - Número máximo de caracteres: 256
  - El valor del atributo no debe contener un espacio.
  - El valor del atributo debe ser único dentro del directorio.
  - Caracteres no válidos: \ \< \> ();, [] "
  - Todas las direcciones de Protocolo simple de transferencia de correo (SMTP) deben cumplir con los estándares de mensajería de correo electrónico.
    
- **userPrincipalName**
    
  - El atributo **userPrincipalName** debe estar en el formato de inicio de sesión de estilo Internet, donde el nombre de usuario está seguido del signo de arroba (@) y de un nombre de dominio: por ejemplo, user@contoso.com. Todas las direcciones de Protocolo simple de transferencia de correo (SMTP) deben cumplir con los estándares de mensajería de correo electrónico.
  - El número máximo de caracteres para el atributo **userPrincipalName** es de 113. Se permite un número específico de caracteres antes y después de la arroba (@), de la siguiente manera: 
  - Número máximo de caracteres para el nombre de usuario que está delante del signo (@): 64
  - Número máximo de caracteres para el nombre de dominio después de la arroba (@): 48
  - Caracteres no válidos: \% &amp; \* +/=? { } | \< \> ( ) ; : , [ ] " '
  - Una umlaut también es un carácter no válido.
  - El carácter @ es necesario en cada valor **userPrincipalName** . 
  - El carácter @ no puede ser el primer carácter de cada valor **userPrincipalName**. 
  - El nombre de usuario no puede terminar con un punto (.), un signo de y comercial ( &amp; ), un espacio o un signo de arroba (@).
  - El nombre de usuario no puede contener espacios.
  - Deben usarse dominios enrutables; por ejemplo, no se pueden usar dominios locales o internos.
  - Unicode se convierte a guiones bajos.
  - **userPrincipalName** no puede contener valores duplicados en el directorio. 
    
## <a name="3-prepare-the-userprincipalname-attribute"></a>3. preparar el atributo userPrincipalName

Active Directory está diseñado para permitir que los usuarios finales de la organización inicien sesión en su directorio mediante **samAccountName** o **userPrincipalName**. De forma similar, los usuarios finales pueden iniciar sesión en Microsoft 365 mediante el nombre principal de usuario (UPN) de su cuenta profesional o educativa. La sincronización de directorios intenta crear nuevos usuarios en Azure Active Directory con el mismo UPN que se encuentra en AD DS. El UPN tiene el mismo formato que una dirección de correo electrónico. 

En Microsoft 365, el UPN es el atributo predeterminado que se usa para generar la dirección de correo electrónico. Es fácil obtener **userPrincipalName** (en AD DS y en Azure ad) y la dirección de correo electrónico principal en **proxyAddresses** se establece en valores diferentes. Cuando se establecen en valores diferentes, puede haber confusión para los administradores y los usuarios finales. 
  
Es mejor alinear estos atributos para reducir la confusión. Para cumplir los requisitos de inicio de sesión único con los servicios de Federación de Active Directory (AD FS) 2,0, debe asegurarse de que los UPN de Azure Active Directory y su AD DS coinciden y usan un espacio de nombres de dominio válido.
  
## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. agregar un sufijo UPN alternativo a AD DS

Es posible que deba agregar un sufijo UPN alternativo para asociar las credenciales corporativas del usuario con el entorno 365 de Microsoft. Un sufijo UPN es la parte de un UPN situada a la derecha del carácter @. Los UPN que se usan para el inicio de sesión único pueden contener letras, números, puntos, guiones y caracteres de subrayado, pero ningún otro tipo de carácter.
  
Para obtener más información acerca de cómo agregar un sufijo UPN alternativo a Active Directory, consulte [preparar la sincronización de directorios]( https://go.microsoft.com/fwlink/p/?LinkId=525430).
  
## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. hacer coincidir el UPN AD DS con el UPN 365 de Microsoft

Si ya ha configurado la sincronización de directorios, es posible que el UPN del usuario de Microsoft 365 no concuerda con el UPN AD DS del usuario definido en AD DS. Esto puede suceder cuando se ha asignado una licencia a un usuario antes de que se comprobara el dominio. Para solucionar esto, use [PowerShell para corregir el UPN duplicado](https://go.microsoft.com/fwlink/p/?LinkId=396730) y actualizar el UPN del usuario para asegurarse de que el UPN 365 de Microsoft coincida con el nombre de usuario corporativo y el dominio. Si actualiza el UPN en AD DS y desea que se sincronice con la identidad de Azure Active Directory, debe quitar la licencia del usuario en Microsoft 365 antes de realizar los cambios en AD DS. 
  
Consulte también [Cómo preparar un dominio no enrutable (como un dominio. local) para la sincronización de directorios](prepare-a-non-routable-domain-for-directory-synchronization.md).

## <a name="next-steps"></a>Pasos siguientes

Si ha realizado los pasos 1 a 5 anteriores, consulte [configurar la sincronización de directorios](set-up-directory-synchronization.md).