---
title: Modelos de identidad de Microsoft 365 y Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 06/09/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: Aprenda a administrar el servicio de identidad de usuario de Azure AD en Microsoft 365 usando modelos de identidad híbrido o solo de nube.
ms.openlocfilehash: d91e14f678e487365805b024e4025e9a39db0c2c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694206"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a>Modelos de identidad de Microsoft 365 y Azure Active Directory

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*

Microsoft 365 usa Azure Active Directory (Azure AD), una identidad de usuario basada en la nube y un servicio de autenticación que se incluye con la suscripción a Microsoft 365, para administrar las identidades y la autenticación de Microsoft 365. La obtención de una infraestructura de identidad configurada correctamente es vital para administrar el acceso y los permisos de usuario de Microsoft 365 para la organización.

Antes de empezar, vea este vídeo para obtener una introducción a los modelos de identidad y autenticación de Microsoft 365.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

La primera opción de planeación es el modelo de identidad de Microsoft 365.

## <a name="microsoft-365-identity-models"></a>Modelos de identidad de Microsoft 365

Para planear las cuentas de usuario, primero debe conocer los dos modelos de identidad de Microsoft 365. Puede mantener las identidades de su organización solo en la nube o puede mantener sus identidades locales de servicios de dominio de Active Directory (AD DS) y usarlas para la autenticación cuando los usuarios obtienen acceso a los servicios en la nube de 365 de Microsoft.  

Estos son los dos tipos de identidad y sus mejores ventajas y ventajas.

| Atributo | Identidad solo de nube | Identidad híbrida |
|:-------|:-----|:-----|
| **Definición** | La cuenta de usuario solo existe en el inquilino de Azure AD para su suscripción a Microsoft 365. | La cuenta de usuario existe en AD DS y una copia también se encuentra en el inquilino de Azure AD para su suscripción a Microsoft 365. La cuenta de usuario de Azure AD también puede incluir una versión de hash de la contraseña de la cuenta de usuario de AD DS ya con hash. |
| **Cómo autentica Microsoft 365 las credenciales de usuario** | El inquilino de Azure AD para su suscripción a Microsoft 365 realiza la autenticación con la cuenta de identidad de nube. | El inquilino de Azure AD para su suscripción de Microsoft 365 administra el proceso de autenticación o redirige al usuario a otro proveedor de identidades. |
| **Ideal para** | Organizaciones que no tienen ni necesitan un AD DS local. | Organizaciones que usan AD DS u otro proveedor de identidades. |
| **Mayor beneficio** | Fácil de usar. No se necesitan servidores o herramientas de directorio adicionales. | Los usuarios pueden usar las mismas credenciales al obtener acceso a los recursos locales o basados en la nube. |
||||

## <a name="cloud-only-identity"></a>Identidad solo de nube

Una identidad de solo nube usa cuentas de usuario que solo existen en Azure AD. La identidad de nube suele usarse en organizaciones pequeñas que no tienen servidores locales o que no usan AD DS para administrar identidades locales. 

Estos son los componentes básicos de la identidad solo de la nube.
 
![Componentes básicos de identidad solo en la nube](../media/about-microsoft-365-identity/cloud-only-identity.png)

Los usuarios locales y remotos (en línea) usan sus cuentas de usuario y contraseñas de Azure AD para acceder a los servicios en la nube de Microsoft 365. Azure AD autentica las credenciales de usuario en función de sus cuentas de usuario y contraseñas almacenadas.

### <a name="administration"></a>Administración
Como las cuentas de usuario se almacenan solo en Azure AD, se administran las identidades de nube con herramientas como el [centro de administración de Microsoft 365](https://admin.microsoft.com) y [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md). 

## <a name="hybrid-identity"></a>Identidad híbrida

La identidad híbrida usa cuentas que se originan en un AD DS local y tienen una copia en el inquilino de Azure AD de una suscripción a Microsoft 365. Sin embargo, la mayoría de los cambios solo fluyen en un sentido. Los cambios que realice en las cuentas de usuario de AD DS se sincronizan con su copia en Azure AD. Pero los cambios realizados en cuentas basadas en la nube en Azure AD, como nuevas cuentas de usuario, no se sincronizan con AD DS.

Azure AD Connect proporciona la sincronización de cuentas en curso. Se ejecuta en un servidor local, comprueba los cambios en AD DS y reenvía dichos cambios a Azure AD. Azure AD Connect permite filtrar las cuentas que se van a sincronizar y si se debe sincronizar una versión hash de las contraseñas de usuario, conocidas como sincronización de hash de contraseña (PHS).

Al implementar la identidad híbrida, su AD DS local es el origen de autoridad para la información de la cuenta. Esto significa que las tareas de administración se realizan principalmente en el entorno local, que luego se sincronizan con Azure AD. 

Estos son los componentes de la identidad híbrida.

![Componentes de la identidad híbrida](../media/about-microsoft-365-identity/hybrid-identity.png)

El inquilino de Azure AD tiene una copia de las cuentas de AD DS. En esta configuración, los usuarios locales y remotos que tienen acceso a los servicios en la nube de Microsoft 365 se autentican con Azure AD.

>[!Note]
>Siempre tiene que usar Azure AD Connect para sincronizar las cuentas de usuario para la identidad híbrida. Necesita las cuentas de usuario sincronizadas en Azure AD para realizar la asignación de licencias y la administración de grupos, configurar permisos y otras tareas administrativas que implican cuentas de usuario.
>

### <a name="administration"></a>Administración

Debido a que las cuentas de usuario originales y autorizadas se almacenan en AD DS local, administra las identidades con las mismas herramientas que AD DS, como la herramienta usuarios y equipos de Active Directory. 

No usa el centro de administración de Microsoft 365 o PowerShell para Microsoft 365 para administrar cuentas de usuario sincronizadas en Azure AD.

## <a name="next-step"></a>Paso siguiente

Si necesita el modelo de identidad solo de la nube, consulte [identidad solo de nube](cloud-only-identities.md).

Si necesita el modelo de identidad híbrida, consulte [Hybrid Identity](plan-for-directory-synchronization.md).


## <a name="see-also"></a>Recursos adicionales

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)