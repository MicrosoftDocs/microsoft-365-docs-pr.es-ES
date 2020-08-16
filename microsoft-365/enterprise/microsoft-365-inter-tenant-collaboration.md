---
title: Colaboración entre inquilinos de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/08/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo funciona la colaboración de Microsoft 365 en los inquilinos y las organizaciones, lo que permite a distintas organizaciones trabajar conjuntamente de manera segura.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 529d4a320fe9aefa5d1ddfbac56742991dbd732d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693963"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Colaboración entre inquilinos de Microsoft 365

En este artículo se describen varias formas de colaborar entre dos inquilinos de Microsoft 365. Está destinado a los administradores de Microsoft 365.
  
Supongamos que dos organizaciones, Fabrikam y Contoso, tienen un inquilino de Microsoft 365 para empresas y quieren trabajar juntos en varios proyectos; algunos de los cuales se ejecutan durante un tiempo limitado y algunos de los cuales están en curso. ¿Cómo puede Fabrikam y contoso permitir que sus usuarios y equipos colaboren de manera más eficaz en sus distintos inquilinos de Microsoft 365 de forma segura? Microsoft 365, junto con la colaboración B2B de Azure Active Directory, proporciona varias opciones. En este artículo se describen varios escenarios clave que Fabrikam y contoso pueden tener en cuenta.
  
Las opciones de colaboración entre espacios empresariales de Microsoft 365 incluyen el uso de una ubicación central para los archivos y las conversaciones, el uso compartido de calendarios, el uso de la mensajería instantánea, las llamadas de audio y vídeo para la comunicación y la protección del acceso a recursos y aplicaciones. Use las tablas siguientes para seleccionar soluciones y obtener más información.
  
## <a name="exchange-online-collaboration-options"></a>Opciones de colaboración de Exchange Online

|**Finalidad del uso compartido**|**Acción administrativa**|**Información de procedimientos**|
|:-----|:-----|:-----|
|Compartir calendarios con otra organización de 365 de Microsoft  <br/> |Los administradores pueden configurar diferentes niveles de acceso al calendario en Exchange Online para permitir a las empresas colaborar con otras empresas y permitir que los usuarios compartan las programaciones (información de disponibilidad) con otras personas.  <br/> |[Uso compartido en Exchange Online](https://technet.microsoft.com/library/jj916670%28v=exchg.150%29.aspx) <br/> [Relaciones de organización en Exchange Online](https://technet.microsoft.com/library/jj916658%28v=exchg.150%29.aspx) <br/> [Crear una relación de organización en Exchange Online](https://technet.microsoft.com/library/jj916671%28v=exchg.150%29.aspx) <br/> [Modificar y relación de organización en Exchange Online](https://technet.microsoft.com/library/jj916659%28v=exchg.150%29.aspx) <br/> [Quitar una relación de organización en Exchange Online](https://technet.microsoft.com/library/jj916657%28v=exchg.150%29.aspx) <br/> [Compartir calendarios con usuarios externos](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) <br/> |
|Controlar la forma en que los usuarios comparten sus calendarios con personas de fuera de la organización  <br/> |Los administradores aplican directivas de uso compartido a los buzones de correo de los usuarios para controlar con quién se puede compartir y el nivel de acceso que se le concede.  <br/> |[Directivas de uso compartido en Exchange Online](https://technet.microsoft.com/library/jj916673%28v=exchg.150%29.aspx) <br/> [Crear una directiva de uso compartido en Exchange Online](https://technet.microsoft.com/library/jj916676%28v=exchg.150%29.aspx) <br/> [Aplicar una directiva de uso compartido a buzones de correo en Exchange Online](https://technet.microsoft.com/library/jj916672%28v=exchg.150%29.aspx) <br/> [Modificar, deshabilitar o quitar una directiva de uso compartido en Exchange Online](https://technet.microsoft.com/library/jj916674%28v=exchg.150%29.aspx) <br/> |
|Configurar canales de correo electrónico seguro y controlar el flujo de correo con organizaciones asociadas  <br/> |Los administradores crean conectores para aplicar seguridad a los intercambios de correo con una organización asociada o un proveedor de servicios. Los conectores aplican el cifrado a través de la seguridad de la capa de transporte (TLS), así como restricciones en los nombres de dominio o en los intervalos de direcciones IP a los que envían sus socios de correo electrónico.  <br/> |[Uso de TLS por Exchange Online para proteger las conexiones de correo electrónico](https://technet.microsoft.com/library/mt163898.aspx) <br/> [Configurar el flujo de correo mediante conectores](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx) <br/> [Dominios remotos en Exchange Online](https://technet.microsoft.com/library/jj966211%28v=exchg.150%29.aspx) <br/> [Configurar el conector para el flujo de correo seguro con una organización asociada](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx) <br/> [Procedimientos recomendados de flujo de correo para Exchange Online (Introducción)](https://technet.microsoft.com/library/0e6cd9d5-ad3e-418a-8ea9-3bf33332c491%28v=exchg.150%29) <br/> |
   
## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>Opciones de colaboración de SharePoint Online y OneDrive para la empresa

|**Objetivos de uso compartido**|**Acción administrativa**|**Información de procedimientos**|
|:-----|:-----|:-----|
|Compartir sitios y documentos con usuarios externos  <br/> |Los administradores configuran el uso compartido en el espacio empresarial o en el nivel de colección de sitios de las cuentas autenticadas, de la cuenta profesional o educativa o de la cuenta de Microsoft.  <br/> |[Administrar el uso compartido externo en su entorno de SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) <br/> [Restringir el uso compartido de contenido de SharePoint y OneDrive por dominio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) <br/> [Usar SharePoint Online como una solución de extranet de negocio a negocio (B2B)](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) <br/> |
|Seguimiento y control del uso compartido externo de usuarios finales  <br/> |Los propietarios de archivos de OneDrive para la empresa y los usuarios finales de SharePoint Online configuran el uso compartido de sitios y documentos y establecen notificaciones para el seguimiento del uso compartido  <br/> |[Configurar las notificaciones para el uso compartido externo de OneDrive para la empresa](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) <br/> [Uso compartido de archivos o carpetas de SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) <br/> |
   
## <a name="skype-for-business-collaboration-options"></a>Opciones de colaboración de Skype empresarial

|**Finalidad del uso compartido**|**Acción administrativa**|**Información de procedimientos**|
|:-----|:-----|:-----|
|Skype empresarial online: mensajería instantánea, llamadas y presencia con otros usuarios de Skype empresarial  <br/> |Los administradores pueden habilitar a sus usuarios de Skype empresarial online para la mensajería instantánea, realizar llamadas de audio y vídeo y ver la presencia con los usuarios en otro inquilino de Microsoft 365.  <br/> |[Permitir a los usuarios contactar con usuarios externos de Skype Empresarial](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94) <br/> |
|Skype empresarial online: mensajería instantánea, llamadas y presencia con usuarios de Skype (consumidor)  <br/> |Los administradores pueden habilitar a sus usuarios de Skype empresarial online para la mensajería instantánea, realizar llamadas y ver la presencia con los usuarios de Skype (consumidor).  <br/> |[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460) <br/> |
   
## <a name="azure-ad-b2b-collaboration-options"></a>Opciones de colaboración B2B de Azure AD

|**Finalidad del uso compartido**|**Acción administrativa**|**Información de procedimientos**|
|:-----|:-----|:-----|
|Colaboración B2B de Azure AD: uso compartido de contenido al agregar usuarios externos a un grupo en el directorio de una organización  <br/> |Un administrador global para un inquilino de Microsoft 365 puede invitar a personas en otro inquilino de Microsoft 365 para que se unan a su directorio, agreguen dichos usuarios externos a un grupo y concedan acceso al contenido, como los sitios y las bibliotecas de SharePoint para el grupo.  <br/> |[¿Qué es la vista previa de colaboración B2B de Azure AD?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) <br/> [B2B de Azure AD: las nuevas actualizaciones hacen que las collab para varios negocios sean fáciles](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) <br/> [Uso compartido externo y colaboración B2B de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-o365-external-user) <br/> [API y personalización de colaboración B2B de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-api) <br/> [Azure AD y programa de identidad: colaboración B2B de Azure AD (empresa a empresa](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) <br/> |
   
## <a name="microsoft-365-collaboration-options"></a>Opciones de colaboración de 365 de Microsoft

|**Finalidad del uso compartido**|**Acción administrativa**|**Información de procedimientos**|
|:-----|:-----|:-----|
|Microsoft 365 grupos: correo electrónico, calendario, OneNote y archivos compartidos en un punto central  <br/> |Los grupos son compatibles con Business Essentials, Business Premium, Education y los planes Enterprise E1, E3 y E5. Los usuarios de un inquilino de Microsoft 365 pueden crear un grupo e invitar a personas en otro inquilino de Microsoft 365 como usuarios invitados. También se aplica a Dynamics CRM.  <br/> |[Obtener más información sobre los grupos de Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) <br/> [Acceso de invitado en Microsoft 365 grupos](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) <br/> [Implementación de grupos de Microsoft 365](https://technet.microsoft.com/library/dn896591.aspx) <br/> |
   
## <a name="yammer-collaboration-options"></a>Opciones de colaboración de Yammer

|**Finalidad del uso compartido**|**Acción administrativa**|**Información de procedimientos**|
|:-----|:-----|:-----|
|Yammer: colaboración a través de un medio social empresarial  <br/> |A menos que un administrador de Yammer deshabilite la capacidad de crear grupos externos, los usuarios pueden crear grupos externos para colaborar en Yammer a través de conversaciones, la capacidad de ir y seguir publicaciones, compartir archivos y chatear en línea.  <br/> |[Crear y administrar grupos externos en Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a) <br/> |
   
## <a name="teams-collaboration-options"></a>Opciones de colaboración de Teams

|**Finalidad del uso compartido**|**Acción administrativa**|**Información de procedimientos**|
|:-----|:-----|:-----|
|Colaborar en Teams con usuarios externos a la organización  <br/> |Un administrador global para el inquilino invitando a Microsoft 365 debe habilitar la colaboración externa en Teams. Ahora, los administradores globales y los propietarios de los equipos podrán invitar a cualquier persona con una dirección de correo electrónico para que colabore en Microsoft Teams.  <br/> Los administradores también pueden administrar y editar invitados que ya están presentes en su espacio empresarial.  <br/> |[Autorizar el acceso de invitado](https://docs.microsoft.com/microsoftteams/teams-dependencies) <br/> [Activar o desactivar el acceso de invitado en Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) <br/> [Usar PowerShell para controlar el acceso de invitado](https://docs.microsoft.com/microsoftteams/guest-access-powershell) <br/> [Lista de comprobación de acceso de invitado](https://docs.microsoft.com/microsoftteams/guest-access-checklist) <br/> [Ver usuarios invitados](https://docs.microsoft.com/microsoftteams/view-guests) <br/> [Editar información del usuario invitado](https://docs.microsoft.com/microsoftteams/edit-guests-information) <br/> |
|Los propietarios de equipo pueden invitar y administrar la forma en que los invitados colaboran en sus equipos.  <br/> |Los propietarios de equipo tienen controles adicionales sobre lo que los invitados pueden hacer en sus equipos.  <br/> |[Agregar invitados](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) <br/> [Agregar un invitado a un equipo](https://docs.microsoft.com/microsoftteams/add-guests) <br/> [Administrar el acceso de invitado en Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-guests) <br/> [Ver quién está en un equipo o en un canal](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) <br/> |
|Los invitados de otros inquilinos pueden ver el contenido de Microsoft Teams y colaborar con otros miembros  <br/> |Ninguno.  <br/> |[La experiencia de acceso de invitado](https://docs.microsoft.com/microsoftteams/guest-experience) <br/> |

## <a name="power-bi-collaboration-options"></a>Opciones de colaboración de Power BI

|**Finalidad del uso compartido**|**Acción administrativa**|**Información de procedimientos**|
|:-----|:-----|:-----|
|Power BI permite a los usuarios invitados externos consumir contenido compartido con ellos a través de vínculos. Esto permite a los usuarios de la organización distribuir contenido de forma segura en todas las organizaciones.<br/> | El administrador de Power BI puede controlar si los usuarios pueden invitar a usuarios externos para ver el contenido de la organización. <br/> |[Distribuir contenido de Power BI a usuarios invitados externos con la B2B de Azure AD](https://docs.microsoft.com/power-bi/service-admin-azure-ad-b2b) <br/> |
 
## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Puntos que deben tenerse en cuenta sobre la colaboración entre espacios empresariales de Microsoft 365

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>Uso compartido de cuentas de usuario, licencias, suscripciones y almacenamiento

Cada organización mantiene sus propias cuentas de usuario, identidades, grupos de seguridad, suscripciones, licencias y almacenamiento. Los usuarios usan las características de colaboración de Microsoft 365 junto con las directivas de uso compartido y la configuración de seguridad para proporcionar acceso a la información necesaria a la vez que mantienen el control de los activos de la compañía.
  
- **Cuentas de usuario:** Las cuentas no se pueden compartir y las cuentas no se pueden duplicar entre los inquilinos o particiones en los servicios de directorio de Active Directory local. 
    
- **Licenses &amp; subscriptions:** en Microsoft 365, las licencias de los planes de licencias (también denominados SKU o planes de Microsoft 365) proporcionan a los usuarios acceso a los servicios de Microsoft 365 que se definen para los planes. 
    
- **Almacenamiento:** En los planes de Microsoft 365, los límites de software y los límites de SharePoint Online se administran independientemente de los límites de almacenamiento de los buzones. Los límites de almacenamiento de buzones se configuran y administran mediante Exchange Online. En ambos casos, el almacenamiento no se puede compartir entre inquilinos. 
    
### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>¿Podemos compartir espacios de nombres de dominio entre inquilinos de Microsoft 365?

No. Los dominios de cortesía, como fabrikam.com o tailspintoys.com, solo se pueden asociar y usar con un inquilino en el momento. Cada inquilino debe tener su propio espacio de nombres; Los espacios de nombres UPN, SMTP y SIP no se pueden compartir entre los inquilinos.
  
### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>¿Qué ocurre con los componentes híbridos y la colaboración entre espacios empresariales de Microsoft 365?

Los componentes híbridos locales, como una organización de Exchange y Azure AD Connect, no se pueden dividir en varios inquilinos.
  
