---
title: Fase 5 de autenticación federada de alta disponibilidad Configure federated authentication for Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 0f1dbf52-5bff-44cc-a264-1b48641af98f
description: 'Resumen: configure Azure AD Conectar para la autenticación federada de alta disponibilidad para Microsoft 365 en Microsoft Azure.'
ms.openlocfilehash: 2bca2b758486b85d185870e2e14b495b8f084cb7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929413"
---
# <a name="high-availability-federated-authentication-phase-5-configure-federated-authentication-for-microsoft-365"></a>Fase 5 de autenticación federada de alta disponibilidad: Configurar la autenticación federada para Microsoft 365

En esta fase final de implementación de la autenticación federada de alta disponibilidad para Microsoft 365 en los servicios de infraestructura de Azure, obtiene e instala un certificado emitido por una entidad de certificación pública, comprueba la configuración y, a continuación, instala y ejecuta Azure AD Conectar en el servidor de sincronización de directorios. Azure AD Conectar la suscripción Microsoft 365 y los servicios de federación de Active Directory (AD FS) y los servidores proxy de aplicaciones web para la autenticación federada.
  
Consulte [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) para todas las fases.
  
## <a name="get-a-public-certificate-and-copy-it-to-the-directory-synchronization-server"></a>Obtener un certificado público y copiarlo en el servidor de sincronización de directorios

Obtenga un certificado digital de una entidad de certificación con las siguientes propiedades:
  
- Un certificado X.509 adecuado para crear conexiones SSL.
    
- La propiedad extendida de nombre alternativo del firmante (SAN) se establece en el FQDN de servicio de federación (ejemplo: fs.contoso.com).
    
- El certificado debe tener la clave privada y estar almacenado en formato PFX.
    
Además, los equipos y dispositivos de la organización deben confiar en la entidad de certificación pública que emite el certificado digital. Esta confianza se establece al tener un certificado raíz de la entidad de certificación pública instalado en el almacén de entidades de certificación raíz de confianza en sus equipos y dispositivos. Los equipos que ejecutan Microsoft Windows normalmente tienen instalado un conjunto de estos tipos de certificados de entidades de certificación usadas frecuentemente. Si el certificado raíz de la entidad de certificación pública no está instalado, debe implementarlo en los equipos y dispositivos de su organización.
  
Para obtener más información sobre los requisitos de certificado para la autenticación federada, consulte [Requisitos previos para la instalación y la configuración de la federación](/azure/active-directory/connect/active-directory-aadconnect-prerequisites#prerequisites-for-federation-installation-and-configuration).
  
Cuando reciba el certificado, cópielo en una carpeta de la unidad C: del servidor de sincronización de directorios. Por ejemplo, asigne al archivo el nombre SSL.pfx y guárdalo en la carpeta C: Certs del servidor de sincronización \\ de directorios.
  
## <a name="verify-your-configuration"></a>Comprobar la configuración

Ahora debería estar listo para configurar azure ad Conectar autenticación federada para Microsoft 365. Para asegurarse de estarlo, aquí tiene una lista de comprobación:
  
- El dominio público de la organización se agrega a la Microsoft 365 suscripción.
    
- Las cuentas de Microsoft 365 de usuario de la organización están configuradas con el nombre de dominio público de la organización y pueden iniciar sesión correctamente.
    
- Ha determinado un FQDN de servicio de federación en función de su nombre de dominio público.
    
- Un registro A de DNS público del FQDN de servicio de federación apunta a la dirección IP pública del equilibrador de carga de Azure accesible desde Internet para los servidores proxy de aplicación web.
    
- Un registro D de DNS privado del FQDN de servicio de federación apunta a la dirección IP privada del equilibrador de carga interno de Azure para los servidores de AD FS.
    
- Un certificado digital con autorización de certificación pública adecuado para conexiones SSL con el SAN establecido en el FQDN del servicio de federación es un archivo PFX almacenado en el servidor de sincronización de directorios.
    
- El certificado raíz de la entidad de certificación pública está instalado en el almacén de entidades de certificación raíz de confianza en sus equipos y dispositivos.
    
Este es un ejemplo de la organización Contoso:
  
**Ejemplo de configuración de una infraestructura de autenticación federada de alta disponibilidad en Azure**

![Una configuración de ejemplo de la infraestructura de autenticación federada Microsoft 365 alta disponibilidad en Azure](../media/ac1a6a0d-0156-4407-9336-6e4cd6db8633.png)
  
## <a name="run-azure-ad-connect-to-configure-federated-authentication"></a>Ejecutar Azure AD Connect para configurar la autenticación federada

La herramienta de Conectar azure AD configura los servidores de AD FS, los servidores proxy de aplicación web y Microsoft 365 para la autenticación federada con estos pasos:
  
1. Cree una conexión de escritorio remoto al servidor de sincronización de directorios con una cuenta de dominio que tenga privilegios de administrador local.
    
2. Desde el escritorio del servidor de sincronización de directorios, abra Internet Explorer y vaya a [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .
    
3. En la página **Microsoft Azure Active Directory Connect**, haga clic en **Descargar** y, después, en **Ejecutar**.
    
4. En la página **Bienvenido a Azure AD Connect**, haga clic en **Acepto** y, después, en **Continuar**.
    
5. En la página **Configuración rápida**, haga clic en **Personalizar**.
    
6. En la página **Instalar componentes necesarios**, haga clic en **Instalar**.
    
7. En la página **Inicio de sesión de usuario**, haga clic en **Federación con AD FS** y, después, haga clic en **Siguiente**.
    
8. En la **Conectar a Azure AD,** escriba el nombre y la contraseña de una cuenta de administrador global para su suscripción Microsoft 365 y, a continuación, haga clic en **Siguiente**.
    
9. En la **Conectar** de directorios, asegúrese de que el bosque local de Servicios de dominio de Active Directory (AD DS) está seleccionado en **Bosque,** escriba el nombre y la contraseña de una cuenta de administrador de dominio, haga clic en Agregar directorio y, a continuación, haga clic en **Siguiente**. 
    
10. En la página **Configuración de inicio de sesión de Azure AD**, haga clic en **Siguiente**.
    
11. En la página **Filtrado de dominios y unidades organizativas**, haga clic en **Siguiente**.
    
12. En la página **Identificación de forma exclusiva de usuarios**, haga clic en **Siguiente**.
    
13. En la página **Filtrar usuarios y dispositivos**, haga clic en **Siguiente**.
    
14. En la página **Características opcionales**, haga clic en **Siguiente**.
    
15. En la página **Granja de AD FS**, haga clic en **Configurar una nueva granja de servidores de AD FS**.
    
16. Haga clic en **Examinar** y especifique la ubicación y el nombre del certificado SSL de la entidad de certificación pública.
    
17. Cuando se le pida, escriba la contraseña del certificado y, después, haga clic en **Aceptar**.
    
18. Compruebe que el **Nombre del firmante** y el **Nombre del servicio de federación** están establecidos en el FQDN de servicio de federación y, después, haga clic en **Siguiente**.
    
19. En la página **Servidores de AD FS**, escriba el nombre del primer servidor de AD FS (tabla M, elemento 4, columna Nombre de máquina virtual) y, después, haga clic en **Agregar**.
    
20. Escriba el nombre del segundo servidor de AD FS (tabla M, elemento 5, columna Nombre de máquina virtual), haga clic en **Agregar** y, después, haga clic en **Siguiente**.
    
21. En la página **Servidores de Proxy de aplicación web**, escriba el nombre del primer servidor proxy de aplicación web (tabla M, elemento 6, columna Nombre de máquina virtual) y, después, haga clic en **Agregar**.
    
22. Escriba el nombre del segundo servidor proxy de aplicación web (tabla M, elemento 7, columna Nombre de máquina virtual), haga clic en **Agregar** y, después, haga clic en **Siguiente**.
    
23. En la página **Credenciales de administrador de dominio**, escriba el nombre de usuario y la contraseña de una cuenta de administrador de dominio y después haga clic en **Siguiente**.
    
24. En la página **Cuenta del servicio AD FS**, escriba el nombre de usuario y la contraseña de una cuenta de administrador empresarial y después haga clic en **Siguiente**.
    
25. En la página **Dominio de Azure AD**, en **Dominio**, seleccione el nombre de dominio DNS de su organización y, después, haga clic en **Siguiente**.
    
26. En la página **Listo para configurar**, haga clic en **Instalar**.
    
27. En la página **Instalación completada**, haga clic en **Comprobar**. Debe ver dos mensajes que indican que tanto la configuración de Internet como la de la intranet se han comprobado correctamente.
    
  - El mensaje de la intranet debe mostrar la dirección IP privada del equilibrador de carga interno de Azure para los servidores de AD FS.
    
  - El mensaje de Internet debe mostrar la dirección IP pública del equilibrador de carga de Azure accesible desde Internet para los servidores proxy de aplicación web.
    
28. En la página **Instalación completada**, haga clic en **Salir**.
    
Esta es la configuración final, con nombres de marcador de posición para los servidores.
  
**Fase 5: Configuración final de una infraestructura de autenticación federada de alta disponibilidad en Azure**

![La configuración final de la infraestructura de autenticación federada Microsoft 365 alta disponibilidad en Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
Se ha completado la infraestructura de autenticación federada de alta Microsoft 365 en Azure.
  
## <a name="see-also"></a>Consulte también

[Implementar la autenticación federada de alta disponibilidad para Microsoft 365 en Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Identidad federada para el entorno Microsoft 365 de desarrollo y pruebas](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Centro de soluciones y arquitectura de Microsoft 365](../solutions/index.yml)

[Identidad federada para Microsoft 365](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9#bk_federated)