---
title: Arquitecturas de Microsoft Azure para SharePoint 2013
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
- seo-marvel-apr2020
ms.assetid: 98fc1006-9399-4ff0-a216-c7c05820d822
description: Obtenga información sobre qué SharePoint soluciones de 2013 se pueden hospedar en Microsoft Azure máquinas virtuales y cómo configurar Azure para hospedar una.
ms.openlocfilehash: eed74e2dcbe383f0f63e7f6ea2fc70fe7b51b1b3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924181"
---
# <a name="microsoft-azure-architectures-for-sharepoint-2013"></a>Arquitecturas de Microsoft Azure para SharePoint 2013

Azure es un buen entorno para hospedar una solución SharePoint Server 2013. En la mayoría de los casos, recomendamos Microsoft 365, pero una granja de servidores de SharePoint hospedada en Azure puede ser una buena opción para soluciones específicas. En este artículo se describe cómo diseñar SharePoint soluciones para que sean adecuadas en la plataforma de Azure. Se usan como ejemplo las dos soluciones específicas siguientes:
  
- [Recuperación ante desastres de SharePoint Server 2013 en Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)
    
- [Sitios de Internet en Microsoft Azure con SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
    
## <a name="recommended-sharepoint-solutions-for-azure-infrastructure-services"></a>Soluciones de SharePoint recomendadas para servicios de infraestructura de Azure

Los servicios de infraestructura de Azure son una opción atractiva para hospedar soluciones de SharePoint. Algunas soluciones son más adecuadas para esta plataforma que otras. La siguiente tabla muestra soluciones recomendadas.
  
|**Solución**|**Por qué se recomienda esta solución para Azure**|
|:-----|:-----|
|Entornos de desarrollo y pruebas  <br/> |Es fácil crear y administrar estos entornos.  <br/> |
|Recuperación ante desastres de granjas de SharePoint locales para Azure  <br/> |**Centro de datos secundario y hospedado** Use Azure en lugar de invertir en un centro de datos secundario de una región diferente. <br/> **Entornos de recuperación ante desastres de coste más bajo** Mantenga y pague menos recursos que un entorno local de recuperación ante desastres. El número de recursos depende del entorno de recuperación ante desastres que elija: espera pasiva, estado de espera semiactiva o espera activa.<br/> **Plataforma más elástica** En caso de desastre, escale fácil y horizontalmente la granja de SharePoint de recuperación para satisfacer los requisitos de carga. Reduzca horizontalmente cuando ya no necesite los recursos.<br/> Vea [Recuperación ante desastres de SharePoint Server 2013 en Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md).  <br/> |
|Sitios con conexión a Internet que usan características y escala no están disponibles en Microsoft 365  <br/> |**Centre sus esfuerzos** Concéntrese en crear el mejor sitio posible y no en tener que crear la infraestructura necesaria. <br/> **Aproveche la flexibilidad de Azure** Asigne el tamaño a la granja según la demanda mediante la adición de servidores nuevos y pague únicamente los recursos que necesita. No se admite la asignación dinámica de máquinas (escala automática).<br/> **Use Azure Active Directory (AD)** Aproveche Azure AD para cuentas de clientes. <br/> **Agregar SharePoint funcionalidad no disponible en Microsoft 365** Agregue informes profundos y análisis web. <br/> Vea [Sitios de Internet en Microsoft Azure con SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md).  <br/> |
|Granjas de aplicaciones para admitir Microsoft 365 entornos locales o locales  <br/> |**Cree, pruebe y hospede a aplicaciones** en Azure para admitir entornos locales y en la nube. <br/> **Hospede a este rol** en Azure en lugar de comprar hardware nuevo para entornos locales. <br/> |
   
Para intranet y cargas de trabajo y soluciones de colaboración, considere las siguientes opciones:
  
- Determine si Microsoft 365 sus requisitos empresariales o puede formar parte de la solución. Microsoft 365 proporciona un conjunto de características enriquecido que siempre está actualizado.
    
- Si Microsoft 365 no cumple todos los requisitos empresariales, considere la posibilidad de una implementación estándar de SharePoint 2013 local desde Microsoft Consulting Services (MCS). Una arquitectura estándar puede ser una solución más rápida, económica y sencilla que una solución personalizada. 
    
- Si una implementación estándar no cumple los requisitos empresariales, considere una solución local personalizada.
    
- Si el uso de una plataforma en la nube es importante para los requisitos empresariales, le recomendamos que use una implementación estándar o personalizada de SharePoint 2013 hospedado en los servicios de infraestructura de Azure. Las soluciones de SharePoint ofrecen mucha más compatibilidad con Azure que otras plataformas en la nube pública que no son nativas de Microsoft.
    
## <a name="before-you-design-the-azure-environment"></a>Antes de diseñar el entorno de Azure

Aunque en este artículo se usan topologías de SharePoint como ejemplo, puede usar estos conceptos de diseño con cualquier topología de granja de SharePoint. Antes de diseñar el entorno de Azure, use la guía de topología, arquitectura, capacidad y rendimiento siguiente para diseñar la granja de SharePoint:
  
- [Diseño de la arquitectura de SharePoint 2013 para profesionales de TI](/SharePoint/technical-reference/technical-diagrams)
    
- [Plan for performance and capacity management in SharePoint Server 2013](/SharePoint/administration/performance-planning-in-sharepoint-server-2013)
    
## <a name="determine-the-active-directory-domain-type"></a>Determinar el tipo de dominio de Active Directory

Cada granja de SharePoint Server usa Active Directory para proporcionar cuentas administrativas para la configuración de granjas. En este momento, existen dos opciones para soluciones de SharePoint en Azure. Los detalles se describen en la siguiente tabla.
  
|**Opción**|**Descripción**|
|:-----|:-----|
|Dominio dedicado  <br/> |Puede implementar un dominio de Active Directory dedicado y aislado en Azure para admitir la granja de SharePoint. Esta es una buena opción para sitios de Internet orientados a uso público.  <br/> |
|Extender el dominio local a través de una conexión entre locales  <br/> |Cuando extiende el dominio local a través de una conexión entre locales, los usuarios tienen acceso a la granja de SharePoint mediante la intranet como si estuviera hospedada de forma local. Puede aprovechar su implementación de DNS y Active Directory local.  <br/> Se requiere una conexión entre locales para crear un entorno de recuperación ante desastres en Azure y realizar la conmutación por error desde la granja local.  <br/> |
   
En este artículo se incluyen conceptos de diseño para extender el dominio local a través de una conexión entre locales. Si la solución usa un dominio dedicado, no es necesario diseñar una conexión entre locales.
  
## <a name="design-the-virtual-network"></a>Diseñar la red virtual

En primer lugar, necesita una red virtual en Azure, que incluye las subredes en las que situará sus máquinas virtuales. La red virtual necesita un espacio de direcciones IP privadas, partes del cual se asignarán a las subredes.
  
Si está ampliando su red local a Azure mediante una conexión entre locales (necesaria para un entorno de recuperación ante desastres), debe elegir un espacio de direcciones privadas que no esté ya en uso en otro lugar de la red de su organización, que puede incluir su entorno local y otras redes virtuales de Azure. 
  
**Figura 1: Entorno local con una red virtual en Azure**

![Diseño de la red virtual de Microsoft Azure para una solución de SharePoint. Subred para la puerta de enlace de Azure. Subred para las máquinas virtuales.](../media/OPrrasconWA-AZarch.png)
  
En este diagrama:
  
- Se ilustra una red virtual en Azure en paralelo con el entorno local. Los dos entornos aún no están conectados mediante una conexión entre locales, la cual puede ser una conexión VPN de sitio a sitio o ExpressRoute.
    
- En este punto, la red virtual solo incluye las subredes y ningún otro elemento de arquitectura. Una subred hospedará la puerta de enlace de Azure y otras subredes hospedarán los niveles de la granja de servidores de SharePoint, con una adicional para Active Directory y DNS.
    
## <a name="add-cross-premises-connectivity"></a>Agregar conectividad entre locales

El siguiente paso de la implementación es crear la conexión entre locales (en caso de que sea aplicable a la solución). Para las conexiones entre locales, la puerta de enlace de Azure se encuentra en una subred de puerta de enlace independiente; debe crearla y asignarle un espacio de direcciones. 
  
Al planear una conexión entre locales, define y crea una conexión y una puerta de enlace de Azure hacia un dispositivo de puerta de enlace local.
  
**Figura 2: Uso de una puerta de enlace de Azure y un dispositivo de puerta de enlace local para proporcionar conectividad de sitio a sitio entre el entorno local y Azure**

![Entorno local conectado a una red virtual de Azure mediante una conexión entre locales, que puede ser una conexión VPN de sitio a sitio o ExpressRoute.](../media/AZarch-VPNgtwyconnct.png)
  
En este diagrama:
  
- Se agrega al diagrama previo el entorno local que está conectado a la red virtual de Azure mediante una conexión entre locales, que puede ser una conexión VPN de sitio a sitio o ExpressRoute.
    
- Una puerta de enlace de Azure se encuentra en una subred de puerta de enlace.
    
- El entorno local incluye un dispositivo de puerta de enlace, como un enrutador o un servidor VPN.
    
Para obtener información adicional para planear y crear una red virtual entre locales, consulte [Conectar una red local con una red virtual de Microsoft Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).
  
## <a name="add-active-directory-domain-services-ad-ds-and-dns"></a>Agregar servicios de dominio de Active Directory (AD DS) y DNS

Para la recuperación ante desastres en Azure, debe implementar Windows Server AD y DNS en un escenario híbrido donde se implementa Windows Server AD tanto de forma local como en máquinas virtuales de Azure.
  
**Figura 3: Configuración híbrida de dominios de Active Directory**

![Dos máquinas virtuales implementadas en la red virtual de Azure y la subred de la granja de servidores de SharePoint son réplicas de controladores de dominio y servidores DNS.](../media/AZarch-HyADdomainConfig.png)
  
Este diagrama es una continuación de los diagramas previos al agregar dos máquinas virtuales en una subred de Windows Server AD y DNS. Estas máquinas virtuales son réplicas de servidores DNS y controladores de dominio. Son una extensión del entorno de Windows Server AD local. 
  
La siguiente tabla proporciona recomendaciones de configuración para estas máquinas virtuales en Azure. Úselas como punto de partida para diseñar su propio entorno (incluso para un dominio de dedicado donde el entorno de Azure no se comunica con el entorno local.
  
|**Elemento**|**Configuración**|
|:-----|:-----|
|Tamaño de las máquinas virtuales en Azure  <br/> |Tamaño A1 o A2 en el nivel estándar  <br/> |
|Sistema operativo  <br/> |Windows Server 2012 R2  <br/> |
|Rol de Active Directory  <br/> |Controlador de dominio de AD DS designado como servidor de catálogo global. Esta configuración reduce el tráfico de salida a través de la conexión entre locales.  <br/> En un entorno de varios dominios con altos índices de cambio (esto no es común), configure controladores de dominio de forma local no para sincronizar con los servidores de catálogo globales en Azure, sino para reducir el tráfico de replicación.  <br/> |
|Rol de DNS  <br/> |Instale y configure el servicio de DNS Server en los controladores de dominio.  <br/> |
|Discos de datos  <br/> |Coloque la base de datos, los registros y SYSVOL de Active Directory en discos de datos de Azure adicionales. No los coloque en el disco del sistema operativo o discos temporales proporcionados por Azure.  <br/> |
|Direcciones IP  <br/> |Utilice direcciones IP estáticas y configure la red virtual para que las asigne a las máquinas virtuales de la red virtual tras la configuración de los controladores de dominio.  <br/> |
   
> [!IMPORTANT]
> Antes de implementar Active Directory en Azure, lea las [Directrices para implementar Windows Server Active Directory en máquinas virtuales de Azure](/windows-server/identity/ad-ds/introduction-to-active-directory-domain-services-ad-ds-virtualization-level-100). Le ayudarán a determinar si la solución requiere una arquitectura diferente u opciones de configuración diferentes. 
  
## <a name="add-the-sharepoint-farm"></a>Agregar la granja de SharePoint

Coloque las máquinas virtuales de la granja de servidores de SharePoint en niveles de las subredes apropiadas.
  
**Figura 4: Colocación de máquinas virtuales de SharePoint**

![Servidores de bases de datos y roles de servidor de SharePoint agregados a la red virtual Azure dentro de la subred de la granja de servidores de SharePoint.](../media/AZarch-SPVMsinCloudSer.png)
  
Este diagrama es una continuación de los diagramas previos al agregar los roles de servidor de granja de SharePoint en sus respectivos niveles.
  
- Dos máquinas virtuales de base de datos que ejecutan SQL Server crean el nivel de base de datos.
    
- Dos máquinas virtuales ejecutan SharePoint Server 2013 para cada uno de los siguientes niveles: servidores front-end, servidores de caché distribuidos y servidores back-end.
    
## <a name="design-and-fine-tune-server-roles-for-availability-sets-and-fault-domains"></a>Diseñar y ajustar roles de servidor para conjuntos de disponibilidad y dominios de error

Un dominio de error es un agrupamiento de hardware en el que se ejecutan instancias de rol. La infraestructura de Azure puede actualizar al mismo tiempo las máquinas virtuales dentro del mismo dominio de error, o bien pueden fallar al mismo tiempo porque comparten la misma estantería. Para evitar el riesgo de tener dos máquinas virtuales en el mismo dominio de error, puede configurar sus máquinas virtuales como conjunto de disponibilidad, lo que garantiza que cada máquina virtual se encuentre en un dominio de error diferente. Si tres máquinas virtuales están configuradas como conjunto de disponibilidad, Azure garantiza que no habrá más que dos de las máquinas virtuales ubicadas en el mismo servidor de error.
  
Cuando diseñe la arquitectura de Azure para una granja de SharePoint, configure roles de servidor idénticos para que formen parte de un conjunto de disponibilidad. Esto garantiza que las máquinas virtuales estén esparcidas por varios dominios de error.
  
**Figura 5: Uso de Conjuntos de disponibilidad de Azure para proporcionar alta disponibilidad para niveles de granja de servidores de SharePoint**

![Configuración de conjuntos de disponibilidad en la infraestructura de Azure para una solución de SharePoint 2013.](../media/AZenv-WinAzureAvailSetsHA.png)
  
Este diagrama llama a la configuración de conjuntos de disponibilidad dentro de la infraestructura de Azure. Cada uno de los siguientes roles comparte un conjunto de disponibilidad separado:
  
- Active Directory y DNS
    
- Base de datos
    
- Back-end
    
- Caché distribuido
    
- Front-end
    
Podría ser necesario ajustar la granja de SharePoint en la plataforma de Azure. Para garantizar la alta disponibilidad de todos los componentes, asegúrese de que los roles de servidor estén configurados todos de forma idéntica.
  
Este es un ejemplo que muestra una arquitectura estándar de Sitios de Internet que cumple objetivos específicos de capacidad y rendimiento. Este ejemplo se encuentra en el siguiente modelo de arquitectura: [Arquitecturas de búsqueda en sitios de Internet para SharePoint Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=261519).
  
**Figura 6: Ejemplo de planeación para objetivos de capacidad y rendimiento en una granja de tres niveles**

![Arquitectura estándar de sitios de Internet de SharePoint 2013 con asignaciones de componentes que cumplen objetivos específicos de rendimiento y capacidad.](../media/AZarch-CapPerfexmpArch.png)
  
En este diagrama:
  
- Se representa una granja de tres niveles: servidores web, servidores de aplicaciones y servidores de bases de datos.
    
- Los tres servidores web están configurados idénticamente con varios componentes.
    
- Los dos servidores de bases de datos están configurados idénticamente.
    
- Los tres servidores de aplicaciones no están configurados idénticamente. Estos roles de servidor requieren ajustes para conjuntos de disponibilidad en Azure.
    
Observemos más cerca el nivel de servidor de aplicaciones
  
**Figura 7: Nivel de servidor de aplicaciones antes del ajuste**

![Ejemplo de nivel de servidor de la aplicación de SharePoint Server 2013 antes de la optimización para conjuntos de disponibilidad de Microsoft Azure.](../media/AZarch-AppServtierBefore.png)
  
En este diagrama:
  
- Se incluyen tres servidores en el nivel de aplicación.
    
- El primer servidor incluye cuatro componentes.
    
- El segundo servidor incluye tres componentes.
    
- El tercer servidor incluye dos componentes.
    
Los objetivos de rendimiento y capacidad para la granja permiten determinar el número de componentes. Para adaptar esta arquitectura para Azure, replicaremos los cuatro componentes en los tres servidores. Esto incrementa el número de componentes más allá de lo necesario para rendimiento y capacidad. La desventaja es que este diseño garantiza la alta disponibilidad de los cuatro componentes en la plataforma de Azure cuando estas tres máquinas virtuales están asignadas a un conjunto de disponibilidad.
  
**Figura 8: Nivel de servidor de aplicaciones después del ajuste**

![Ejemplo de nivel de servidor de la aplicación de SharePoint Server 2013 después de la optimización para conjuntos de disponibilidad de Microsoft Azure.](../media/AZarch-AppServtierAfter.png)
  
Este diagrama muestra los tres servidores de aplicaciones configurados de forma idéntica con los mismos cuatro componentes.
  
Cuando agregamos conjuntos de disponibilidad a los niveles de la granja de servidores de SharePoint, se completa la implementación.
  
**Figura 9: La granja de SharePoint completada en los servicios de infraestructura de Azure**

![Ejemplo de granja de servidores de SharePoint 2013 en los servicios de infraestructura de Azure con red virtual, conectividad entre locales, subredes, máquinas virtuales y conjuntos de disponibilidad.](../media/7256292f-bf11-485b-8917-41ba206153ee.png)
  
Este diagrama muestra el conjunto de servidores de SharePoint implementado en los servicios de infraestructura de Azure, con conjuntos de disponibilidad para proporcionar dominios de error para los servidores de cada nivel.
  
## <a name="see-also"></a>Consulte también

[Centro de soluciones y arquitectura de Microsoft 365](../solutions/index.yml)
  
[Sitios de Internet en Microsoft Azure con SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
  
[Recuperación ante desastres de SharePoint Server 2013 en Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)