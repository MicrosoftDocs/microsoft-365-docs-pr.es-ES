---
title: Suscripciones, licencias, cuentas y espacios empresariales para las ofertas de la nube de Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.assetid: c720cffc-f9b5-4f43-9100-422f86a1027c
ms.custom:
- seo-marvel-apr2020
- Ent_Architecture
description: Información sobre las relaciones de las organizaciones, las suscripciones, las licencias, las cuentas de usuario y los espacios empresariales en las ofertas de la nube de Microsoft.
ms.openlocfilehash: 34e920e6b5a48adaffcc31150090e96f9c8d8b0e
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604326"
---
# <a name="subscriptions-licenses-accounts-and-tenants-for-microsofts-cloud-offerings"></a>Suscripciones, licencias, cuentas y espacios empresariales para las ofertas de la nube de Microsoft

Microsoft facilita una jerarquía de organizaciones, suscripciones, licencias y cuentas de usuario para un uso coherente de las identidades y la facturación en todas sus ofertas de la nube:
  
- Microsoft 365 y Microsoft Office 365
- Microsoft Azure
- Microsoft Dynamics 365

## <a name="elements-of-the-hierarchy"></a>Elementos de la jerarquía

Estos son los elementos de la jerarquía:
  
### <a name="organization"></a>Organización

Una organización representa una entidad empresarial que usa ofertas de la nube de Microsoft, normalmente identificadas por uno o más sistemas de nombres de dominio (DNS) público, como contoso.com. La organización es un contenedor para las suscripciones.
  
### <a name="subscriptions"></a>Suscripciones

Una suscripción es un contrato con Microsoft para utilizar uno o más servicios o plataformas de la nube de Microsoft, para los que se acumulan los cargos en función de un precio de licencia por usuario o en el consumo de recursos basados en la nube. 

- Las ofertas de la nube basadas en el software como servicio (SaaS) de Microsoft 365 y Dynamics 365 cobran precios de licencia por usuario. 
- Las ofertas de la nube de plataforma como servicio (PaaS) y de infraestructura como servicio (IaaS) de Microsoft (Azure) se cobran en función del consumo de recursos de la nube.
 
También puede usar una suscripción de prueba, pero la suscripción expira después de un periodo de tiempo o cargos por consumo determinados. Puede convertir una suscripción de prueba en una suscripción de pago.
  
Las organizaciones pueden tener varias suscripciones para las ofertas de la nube de Microsoft. En la ilustración 1, se muestra una sola organización con varias suscripciones de Microsoft 365, una suscripción de Dynamics 365 y varias suscripciones de Azure.

**Ilustración 1: Ejemplo de varias suscripciones para una organización**

![Una organización de ejemplo con varias suscripciones para las ofertas de la nube de Microsoft.](../media/Subscriptions/Subscriptions-Fig1.png)
  
### <a name="licenses"></a>Licencias

Para las ofertas de la nube de SaaS de Microsoft, una licencia permite a una cuenta de usuario específica utilizar los servicios de la oferta de la nube. Se le cobrará un precio mensual fijo como parte de su suscripción. Los administradores asignan licencias a cuentas de usuario individuales en la suscripción. Para el ejemplo en la figura 2, Contoso Corporation tiene una suscripción a Microsoft 365 E5 con 100 licencias, que permite a hasta 100 cuentas de usuario individuales utilizar las características y los servicios de Microsoft 365 E5.
  
**Ilustración 2: Licencias en las suscripciones basadas en SaaS para una organización**

![Un ejemplo de varias licencias de suscripciones para las ofertas de la nube de Microsoft basadas en SaaS.](../media/Subscriptions/Subscriptions-Fig2.png)

>[!Note]
>Un procedimiento recomendado de seguridad es usar cuentas de usuario separadas a las que se les asignen roles específicos para funciones administrativas. No es necesario que a estas cuentas de administrador dedicadas se les asigne una licencia para los servicios en la nube que administran. Por ejemplo, no es necesario que se asigne una cuenta de administrador de SharePoint a una licencia de Microsoft 365.
>

Para los servicios en la nube basados en PaaS de Azure, las licencias de software están integradas en los precios del servicio.
  
Para las máquinas virtuales basadas en IaaS de Azure, podrían necesitarse licencias adicionales para utilizar el software o la aplicación instalada en una imagen de la máquina virtual. Algunas imágenes de máquina virtual tienen versiones con licencia de software instalado y el costo está incluido en la tarifa por minuto para el servidor. Algunos ejemplos son las imágenes de la máquina virtual para SQL Server 2014 y SQL Server 2016. 
  
Algunas imágenes de máquina virtual tienen versiones de prueba de aplicaciones instaladas y necesitan licencias adicionales de aplicación de software para su uso más allá del período de prueba. Por ejemplo, la imagen de la máquina virtual de prueba de SharePoint Server 2016 incluye una versión de prueba de SharePoint Server 2016 instalada previamente. Para seguir utilizando SharePoint Server 2016 después de la fecha de expiración de la versión de prueba, debe adquirir una licencia de SharePoint Server 2016 y licencias de cliente de Microsoft. Estos cargos son independientes de la suscripción de Azure y la tarifa por minuto para ejecutar la máquina virtual sigue vigente.
  
### <a name="user-accounts"></a>Cuentas de usuario

Las cuentas de usuario para todas las ofertas de la nube de Microsoft se almacenan en un espacio empresarial de Azure Active Directory (Azure AD), que contiene grupos y cuentas de usuario. Un inquilino de Azure AD se puede sincronizar con las cuentas existentes de Active Directory Domain Services (AD DS) mediante Azure AD Connect, un servicio basado en Windows Server. Esto se conoce como sincronización de directorios.
  
En la ilustración 3, se muestra un ejemplo de varias suscripciones de una organización con un espacio empresarial de Azure AD común que contiene las cuentas de la organización.
  
**Ilustración 3: Varias suscripciones de una organización que usan el mismo espacio empresarial de Azure AD**

![Una organización de ejemplo con varias suscripciones que usan el mismo espacio empresarial de Azure AD.](../media/Subscriptions/Subscriptions-Fig3.png)
  
### <a name="tenants"></a>Espacios empresariales

Para las ofertas de la nube de SaaS, el inquilino es la ubicación regional que hospeda a los servidores que proporcionan servicios en la nube. Por ejemplo, Contoso Corporation eligió la región europea para hospedar sus suscripciones de Microsoft 365, EMS y Dynamics 365 para los 15 000 trabajadores en su sede de París.
  
Los servicios de PaaS de Azure y las cargas de trabajo basadas en máquina virtual hospedadas en IaaS de Azure pueden tener un arrendamiento en cualquier centro de datos de Azure en todo el mundo. Especifique el centro de datos de Azure, conocido como la ubicación, al crear la aplicación o el servicio de PaaS de Azure, o el elemento de una carga de trabajo de IaaS.
  
Un espacio empresarial de Azure AD es una instancia específica de Azure AD que contiene cuentas y grupos. Las suscripciones de pago o de prueba de Microsoft 365 o Dynamics 365 incluyen un espacio empresarial de Azure AD gratuito. Este inquilino de Azure AD no incluye otros servicios de Azure y no es lo mismo que una suscripción de prueba o de pago de Azure.
  
### <a name="summary-of-the-hierarchy"></a>Resumen de la jerarquía

Presentamos un breve resumen:
  
- Una organización puede tener varias suscripciones.
    
  - Una suscripción puede tener varias licencias.
    
  - Las licencias se pueden asignar a cuentas de usuario individuales.
    
  - Las cuentas de usuario se almacenan en un inquilino de Azure AD.
    
Aquí tiene un ejemplo de la relación de las organizaciones, suscripciones, licencias y cuentas de usuario.
  
- Una organización identificada mediante su nombre de dominio público.
    
  - Una suscripción a Microsoft 365 E3 con licencias de usuario.
    
    Una suscripción a Microsoft 365 E5 con licencias de usuario.
    
    Una suscripción de Dynamics 365 con licencias de usuario.
    
    Varias suscripciones de Azure.
    
  - Las cuentas de usuario de la organización en un inquilino común de Azure AD.
    
Varias suscripciones de la oferta de la nube de Microsoft pueden usar el mismo inquilino de Azure AD, que actúa como proveedor común de identidades. Un espacio empresarial central de Azure AD que contiene las cuentas sincronizadas de su servidor local de AD DS le proporciona identidad como servicio (IDaaS) basada en la nube para su organización. 
  
**Ilustración 4: Cuentas locales sincronizadas e IDaaS para una organización**

![IDaaS de identidad como servicio (IaaS) para su organización.](../media/Subscriptions/Subscriptions-Fig4.png)
  
En la figura 4, se muestra cómo las ofertas de la nube de SaaS de Microsoft, las aplicaciones de PaaS de Azure y las máquinas virtuales de IaaS de Azure que usan Azure AD Domain Services usan un inquilino común de Azure AD. Azure AD Connect sincroniza el bosque de AD DS local con el inquilino de Azure AD.
  
## <a name="combining-subscriptions-for-multiple-microsoft-cloud-offerings"></a>Combinación de suscripciones para varias ofertas de la nube de Microsoft

En la siguiente tabla se describe cómo combinar varias ofertas de la nube de Microsoft si ya se cuenta con una suscripción para un tipo de oferta de la nube (las etiquetas de la primera columna) y si se agrega una suscripción para una oferta de la nube diferente (que pasan por todas las columnas).
  
||**Microsoft 365**|**Azure**|**Dynamics 365**|
|:-----|:-----|:-----|:-----|:-----|
|**Microsoft 365** <br/> |N/D  <br/> |Agregue una suscripción de Azure a la organización desde el portal de Azure.  <br/> |Agregue una suscripción de Dynamics 365 a la organización desde el Centro de administración de Microsoft 365.  <br/> |
|**Azure** <br/> |Agregue una suscripción de Microsoft 365 a su organización.  <br/> |N/D  <br/> |Agregue una suscripción de Dynamics 365 a su organización.  <br/> |
|**Dynamics 365** <br/> |Agregue una suscripción de Microsoft 365 a su organización.  <br/> |Agregue una suscripción de Azure a la organización desde el portal de Azure.  <br/> |N/D  <br/> |
   
Una forma sencilla de agregar suscripciones a su organización para los servicios basados en SaaS para Microsoft es a través del Centro de administración:
  
1. Inicie sesión en el Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) con su cuenta de administrador global.
    
2. En el panel de navegación izquierdo de la página principal del **Centro de administración**, haga clic en **Facturación** y, después, en **Servicios de compra**.
    
3. En la página **Servicios de compra**, compre las nuevas suscripciones.
    
El Centro de administración asigna la organización y el espacio empresarial de Azure AD de su suscripción de Microsoft 365 a las nuevas suscripciones para las ofertas en la nube basadas en SaaS.
  
Para agregar una suscripción de Azure con la misma organización y espacio empresarial de Azure AD que su suscripción de Microsoft 365:
  
1. Inicie sesión en Azure Portal ([https://portal.azure.com](https://portal.azure.com)) con su cuenta de administrador global de Microsoft 365.
    
2. En el panel de navegación izquierdo, haga clic en **Suscripciones** y después en **Agregar**.
    
3. En la página **Agregar suscripción**, seleccione una oferta y complete la información de pago y el contrato.
    
Si compró suscripciones de Microsoft 365 y Azure por separado y quiere acceder al espacio empresarial de Azure AD de Microsoft 365 desde su suscripción de Azure, vea las instrucciones en [Añadir una suscripción existente de Azure a su espacio empresarial de Azure Active Directory](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory).
 
## <a name="see-also"></a>Ver también

[Ilustraciones de la nube de Microsoft para arquitectos empresariales](../solutions/cloud-architecture-models.md)
  
[Modelos de arquitectura para SharePoint, Exchange, Skype Empresarial y Lync](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md)
  
[Soluciones híbridas](hybrid-solutions.md)

## <a name="next-step"></a>Paso siguiente

[Evaluar la conectividad de red de Microsoft 365](assessing-network-connectivity.md)
