---
title: Información de la red de 365 de Microsoft (versión preliminar)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Información de la red de 365 de Microsoft (versión preliminar)
ms.openlocfilehash: b30af89d480383fdc9011d24409e3b418339c70b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693909"
---
# <a name="microsoft-365-network-insights-preview"></a>Información de la red de 365 de Microsoft (versión preliminar)

**Network Insights** son métricas de rendimiento de Live que recopila el inquilino de Microsoft 365 y que solo pueden ver los usuarios administrativos de su espacio empresarial. La información se muestra en el centro de administración de Microsoft 365 en <https://portal.microsoft.com/adminportal/home#/networkperformance> .

La información está destinada a ayudar en el diseño de perímetros de red para sus ubicaciones de oficina. Cada conocimiento proporciona detalles sobre las características de rendimiento de un problema común específico para cada ubicación geográfica en la que los usuarios obtienen acceso a su inquilino.

Hay cinco información de red específica que se puede mostrar para cada ubicación de la oficina:

- [Salida de red en recorrido](#backhauled-network-egress)
- [Se ha detectado un mejor rendimiento para los clientes cercanos](#better-performance-detected-for-customers-near-you)
- [Uso de una puerta principal no óptima del servicio de Exchange Online](#use-of-a-non-optimal-exchange-online-service-front-door)
- [Uso de puerta frontal del servicio de SharePoint Online no óptimo](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Velocidad de descarga baja desde la puerta frontal de SharePoint](#low-download-speed-from-sharepoint-front-door)

>[!IMPORTANT]
>Información sobre la red, recomendaciones de rendimiento y evaluaciones en el centro de administración de Microsoft 365 se encuentra actualmente en estado de versión preliminar y solo está disponible para los inquilinos de Microsoft 365 que se han inscrito en el programa de vista previa de características.

## <a name="backhauled-network-egress"></a>Salida de red en recorrido

Esta información se mostrará si el servicio de Network Insights detecta que la distancia desde una ubicación de usuario determinada a la red de salida es superior a 500 millas (800 kilómetros), lo que indica que el tráfico de Microsoft 365 se está reteniendo en un dispositivo perimetral de Internet o proxy común.

Esta información se abrevia como "salida" en algunas vistas de resumen.

![Salida de red en recorrido](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a>Escenario

Esto identifica que la distancia entre la ubicación de la oficina y la red de salida es de más de 500 millas (800 kilómetros). La ubicación de la oficina se identifica con una ubicación de equipo cliente confusa y la ubicación de salida de red se identifica con las bases de datos dirección IP inversa para la ubicación. La ubicación de la oficina puede no ser exacta si servicios de ubicación de Windows está deshabilitado en los equipos. La ubicación de salida de red puede ser inexacta si la información de la base de datos de direcciones IP inversas no es exacta.

Los detalles de esta visión incluyen la ubicación de la oficina, el porcentaje estimado del usuario total del inquilino en la ubicación, la ubicación de salida actual de la red, la relevancia de la ubicación de salida, la distancia entre la ubicación y el punto de salida actual, la fecha en que se detectó la condición por primera vez y la fecha en que se resolvió la condición.

### <a name="what-should-i-do"></a>¿Qué tengo que hacer?

Para esta idea, recomendamos que se acerque la salida de red a la ubicación de la oficina para que la conectividad pueda enrutarse de forma óptima a la red global de Microsoft y a la puerta frontal del servicio Microsoft 365 más cercana. Dejar la red cercana a los usuarios las ubicaciones de Office también permiten un mejor rendimiento en el futuro, ya que Microsoft expande tanto los puntos de presencia de red como las puertas frontales del servicio 365 de Microsoft en el futuro.

Para obtener más información acerca de cómo resolver este problema, vea [conexiones de red de salida de forma local](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) en los principios de conectividad de red de [Office 365](microsoft-365-network-connectivity-principles.md).

## <a name="better-performance-detected-for-customers-near-you"></a>Se ha detectado un mejor rendimiento para los clientes cercanos

Esta información se mostrará si el servicio de Network Insights detecta que un número importante de clientes en el área metropolitana tiene mejor rendimiento que los usuarios de la organización en esta ubicación de la oficina.

Esta información se abrevia como "homólogos" en algunas vistas de resumen.

![Rendimiento de red relativo](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a>Escenario

Esta visión examina el rendimiento agregado de los clientes de Microsoft 365 en la misma ciudad que esta ubicación de la oficina. Esta información se muestra si el promedio de latencia de los usuarios es un 10% mayor que la latencia media de los inquilinos vecinos.

### <a name="what-should-i-do"></a>¿Qué tengo que hacer?

Puede haber muchas razones para esta condición, como la latencia en la red corporativa o los problemas de diseño de la arquitectura o del ISP, o los cuellos de botella. Examine la latencia entre cada salto en la ruta entre la red de la oficina y la puerta de frontal de Microsoft 365. Para obtener más información, consulte [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a>Uso de una puerta principal no óptima del servicio de Exchange Online

Esta información se mostrará si el servicio de Network Insights detecta que los usuarios de una ubicación específica no se conectan a una puerta de enlace de servicio de Exchange Online óptima.

Esta información se abrevia como "enrutamiento" en algunas vistas de resumen.

![Puerta delantera no óptima](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a>Escenario

Enumeramos las puertas frontales del servicio de Exchange online que son adecuadas para su uso desde la ciudad de la ubicación de la oficina con buen rendimiento. Si la prueba actual muestra el uso de una puerta de servicio de Exchange online que no está en esta lista, se indica esta recomendación.

### <a name="what-should-i-do"></a>¿Qué tengo que hacer?

El uso de un servicio de Exchange online no óptimo puede deberse a una backhaul? n de red antes de que la red corporativa se deshaga, en cuyo caso se recomienda la salida local y directa de la red. También podría deberse al uso de un servidor remoto de resolución de recursiva de DNS, en cuyo caso se recomienda alinear el servidor de resolución de DNS recursivo con la salida de red.

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a>Uso de puerta frontal del servicio de SharePoint Online no óptimo

Esta información se mostrará si el servicio de Network Insights detecta que los usuarios de una ubicación específica no se conectan a la puerta frontal del servicio de SharePoint Online más cercana.

Esta información se abrevia como "AFD" en algunas vistas de resumen.

![Puerta delantera no óptima](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a>Escenario

Identificamos la puerta frontal del servicio de SharePoint Online a la que se conecta el cliente de prueba. A continuación, para la ciudad de la ubicación de la oficina, la encontrarás en la puerta frontal esperada del servicio de SharePoint Online para esa ciudad. Si no coincide, realizamos esta recomendación.

### <a name="what-should-i-do"></a>¿Qué tengo que hacer?

El uso de un servicio de SharePoint Online no óptimo puede deberse a la backhaul? n de red antes de que la red corporativa se deshaga, en cuyo caso se recomienda la salida local y directa de la red. También podría deberse al uso de un servidor remoto de resolución de recursiva de DNS, en cuyo caso se recomienda alinear el servidor de resolución de DNS recursivo con la salida de red.

## <a name="low-download-speed-from-sharepoint-front-door"></a>Velocidad de descarga baja desde la puerta frontal de SharePoint

Esta información se mostrará si el servicio de Network Insights detecta que el ancho de banda entre la ubicación específica de la oficina y SharePoint Online es inferior a 1 MBps.

Esta información se abrevia como "rendimiento" en algunas vistas de resumen.

### <a name="what-does-this-mean"></a>Escenario

La velocidad de descarga que un usuario puede obtener del servicio de SharePoint Online y OneDrive para la empresa las puertas del anverso se mide en megabytes por segundo (MBps). Si este valor es inferior a 1 MBps, proporcionaremos esta visión.

### <a name="what-should-i-do"></a>¿Qué tengo que hacer?

Para mejorar la velocidad de descarga, es posible que sea necesario aumentar el ancho de banda. Como alternativa, puede que exista una congestión de red entre los equipos de los usuarios en la ubicación de la oficina y la puerta de servicio de SharePoint Online. A veces se denomina pérdida de Congestive y restringe la velocidad de descarga disponible para los usuarios, incluso si hay suficiente ancho de banda disponible.

## <a name="china-user-optimal-network-egress"></a>Salida de red óptima de usuario de China

Esta información se mostrará si su organización tiene usuarios en China que se conectan a su inquilino de Microsoft 365 en otras ubicaciones geográficas. 

### <a name="what-does-this-mean"></a>Escenario

Si su organización tiene conectividad WAN privada, le recomendamos configurar un circuito de WAN de red desde sus ubicaciones de oficina en China que tenga red de salida a Internet en cualquiera de las siguientes ubicaciones:

- RAE de Hong Kong
- Japón
- Taiwán
- Corea del Sur
- Singapur
- Malasia

Internet sale aún más de los usuarios que estas ubicaciones reducirán el rendimiento y los resultados en China podrían causar problemas de alta latencia y conectividad debido a congestión transfronteriza.

### <a name="what-should-i-do"></a>¿Qué tengo que hacer?

Para obtener más información acerca de cómo mitigar problemas de rendimiento relacionados con esta visión, consulte [Office 365 global tenant performance Optimization for China users](microsoft-365-networking-china.md).

## <a name="related-topics"></a>Temas relacionados

[Recomendaciones de rendimiento de red en el centro de administración de Microsoft 365 (versión preliminar)](office-365-network-mac-perf-overview.md)

[Evaluación de red de Microsoft 365 (versión preliminar)](office-365-network-mac-perf-score.md)

[Prueba de conectividad de Microsoft 365 en el centro de administración de M365 (versión preliminar)](office-365-network-mac-perf-onboarding-tool.md)

[Servicios de ubicación de conectividad de red 365 de Microsoft (versión preliminar)](office-365-network-mac-location-services.md)