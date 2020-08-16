---
title: Información general de conectividad de red de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Se explica por qué es importante la optimización de red para los servicios SaaS, el objetivo de la red de Microsoft 365 y cómo SaaS requiere distintas redes de otras cargas de trabajo.
ms.openlocfilehash: 4fea7364dc79717583ebca8ce0dbe333ee818f1f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693804"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Introducción a la conectividad de red 365 de Microsoft

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*

Microsoft 365 es una nube de software como servicio (SaaS) distribuida que proporciona escenarios de productividad y colaboración a través de un conjunto diverso de micro-servicios y aplicaciones. Los componentes de cliente de Microsoft 365 como Outlook, Word y PowerPoint se ejecutan en los equipos de los usuarios y se conectan a otros componentes de Microsoft 365 que se ejecutan en los centros de usuarios de Microsoft. El factor más importante que determina la calidad de la experiencia del usuario final de Microsoft 365 es la confiabilidad de red y la baja latencia entre los clientes de Microsoft 365 y las puertas de servicio de Microsoft 365.

En este artículo, conocerá los objetivos de la red de Microsoft 365 y por qué las redes Microsoft 365 requieren un enfoque diferente para la optimización que el tráfico genérico de Internet.

## <a name="microsoft-365-networking-goals"></a>Objetivos de red de Microsoft 365

El objetivo final de la red de Microsoft 365 es optimizar la experiencia del usuario final al habilitar el acceso menos restrictivo entre los clientes y los puntos de conexión de Microsoft 365 más cercanos. La calidad de la experiencia del usuario final está directamente relacionada con el rendimiento y la capacidad de respuesta de la aplicación que está usando el usuario. Por ejemplo, Microsoft Teams depende de baja latencia para que las llamadas telefónicas de los usuarios, las conferencias y las colaboraciones de pantalla compartida no se puedan usar sin problemas, y Outlook se basa en una buena conectividad de red para las características de búsqueda instantánea que aprovechan las capacidades de indización y de AI del servidor.

El objetivo principal del diseño de red debería ser minimizar la latencia reduciendo el tiempo de ida y vuelta (RTT) de los equipos cliente a Microsoft Global Network, la red troncal de red pública de Microsoft que interconectan todos los centros de recursos de Microsoft con baja latencia, los puntos de entrada de la aplicación en la nube de alta disponibilidad se propagan por todo el mundo. Puede obtener más información sobre la Red Global de Microsoft en [Cómo construye Microsoft su red global rápida y confiable](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

No es necesario que la optimización del rendimiento de red de Microsoft 365 sea complicada. Puede obtener el mejor rendimiento posible si sigue unos cuantos principios clave:

- Identificar el tráfico de red de Microsoft 365
- Permitir la salida de bifurcaciones locales de tráfico de red de Microsoft 365 a Internet desde cada ubicación en la que los usuarios se conectan a Microsoft 365
- Permitir que el tráfico 365 de Microsoft omita servidores proxy y dispositivos de inspección de paquetes

Para obtener más información sobre los principios de conectividad de red de 365 de Microsoft, vea [microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).

## <a name="traditional-network-architectures-and-saas"></a>Arquitecturas de red tradicionales y SaaS

Los principios de arquitectura de red tradicional para las cargas de trabajo cliente-servidor se diseñan en torno al supuesto de que el tráfico entre los clientes y los extremos no se extienda fuera del perímetro de la red corporativa. Además, en muchas redes empresariales, todas las conexiones de Internet salientes atraviesan la red corporativa y se salida de una ubicación central.

En las arquitecturas de red tradicionales, la mayor latencia para el tráfico de Internet genérico es un equilibrio necesario para mantener la seguridad del perímetro de la red, y la optimización del rendimiento para el tráfico de Internet suele implicar la actualización o la ampliación del equipo en puntos de salida de red. Sin embargo, este enfoque no se redirecciona a los requisitos para un rendimiento óptimo de la red de los servicios SaaS como Microsoft 365.

## <a name="identifying-microsoft-365-network-traffic"></a>Identificación del tráfico de red de Microsoft 365

Estamos haciendo que sea más fácil identificar el tráfico de red de Microsoft 365 y simplificar la administración de la identificación de red.

- Nuevas categorías de puntos de conexión de red para diferenciar el tráfico de red de alta importancia del tráfico de red que no se ve afectado por las latencias de Internet. Hay solo un puñado de direcciones URL y admite direcciones IP en la categoría "optimizar" más importante.
- Servicios web para el uso de scripts o la configuración directa de dispositivos y la administración de cambios de la identificación de red de Microsoft 365. Los cambios están disponibles en el servicio Web, en el formato RSS o en el correo electrónico mediante una plantilla de Microsoft Flow.
- [Programa para socios de red de Office 365](https://aka.ms/Office365NPP) con asociados de Microsoft que proporcionan dispositivos o servicios que siguen los principios de conectividad de red de Microsoft 365 y tienen una configuración sencilla.

## <a name="securing-microsoft-365-connections"></a>Protección de las conexiones 365 de Microsoft

El objetivo de la seguridad de red tradicional es fortalecer el perímetro de la red corporativa frente a vulnerabilidades de seguridad malintencionadas e intrusiones. La mayoría de las redes empresariales exigen la seguridad de red para el tráfico de Internet mediante tecnologías como servidores proxy, firewalls, interrupción e inspección de SSL, inspección profunda de paquetes y sistemas de prevención de pérdida de datos. Estas tecnologías proporcionan una importante mitigación de riesgos para las solicitudes de Internet genéricas, pero pueden reducir drásticamente el rendimiento, la escalabilidad y la calidad de la experiencia del usuario final cuando se aplican a los puntos de conexión de Microsoft 365.

Microsoft 365 ayuda a satisfacer las necesidades de su organización para la seguridad del contenido y el uso de datos con características de gobierno y seguridad integradas diseñadas específicamente para las características y cargas de trabajo de Microsoft 365. Para obtener más información acerca de la seguridad y el cumplimiento de Microsoft 365, consulte la [Guía de seguridad de Office 365](https://docs.microsoft.com/office365/securitycompliance/security-roadmap). Para obtener más información sobre las recomendaciones de Microsoft y la posición de soporte en soluciones avanzadas de red que realizan un procesamiento de nivel avanzado en el tráfico de Microsoft 365, vea [usar dispositivos de red de terceros o soluciones en el tráfico de Office 365](https://support.microsoft.com/help/2690045).

## <a name="why-is-microsoft-365-networking-different"></a>¿Por qué es diferente la red de Microsoft 365?

Microsoft 365 está diseñado para obtener un rendimiento óptimo mediante el uso de la seguridad de extremos y conexiones de red cifradas, lo que reduce la necesidad de aplicar la seguridad perimetral. Los centros de recursos de Microsoft 365 se encuentran en todo el mundo y el servicio está diseñado para usar varios métodos para conectar clientes a los mejores extremos de servicio disponibles. Como los datos de usuario y el procesamiento se distribuyen entre muchos centros de datos de Microsoft, no hay un único extremo de red al que se puedan conectar los equipos cliente. De hecho, la red global de Microsoft optimiza dinámicamente los datos y servicios de su inquilino de Microsoft 365 para adaptarlos a las ubicaciones geográficas desde las que los usuarios finales tienen acceso.

Algunos problemas comunes de rendimiento se crean cuando el tráfico de Microsoft 365 está sujeto a la inspección de paquetes y salida centralizada:

- La alta latencia puede provocar un rendimiento extremadamente deficiente de las secuencias de audio y vídeo, y la respuesta lenta de la recuperación de datos, las búsquedas, la colaboración en tiempo real, la información de disponibilidad de calendario, el contenido del producto y otros servicios.
- La salida de conexiones desde una ubicación central derrota las capacidades de enrutamiento dinámico de la red global de Microsoft 365, lo que agrega latencia y tiempo de ida y vuelta
- El descifrado de tráfico de red de Microsoft 365 protegido con SSL y el nuevo cifrado puede provocar errores de protocolo y tener riesgo de seguridad

La reducción de la ruta de acceso de red a los puntos de entrada de Microsoft 365 al permitir que el tráfico de clientes salga lo más cerca posible de su ubicación geográfica puede mejorar el rendimiento de conectividad y la experiencia del usuario final en Microsoft 365. También puede ayudar a reducir el impacto de los cambios futuros a la arquitectura de red en el rendimiento y la confiabilidad de Microsoft 365. El modelo de conectividad óptimo es proporcionar siempre salida de red en la ubicación del usuario, independientemente de si se encuentra en la red corporativa o en las ubicaciones remotas, como los hogares, los hoteles, las cafeterías y los aeropuertos. El tráfico de Internet genérico y el tráfico de red corporativa basado en WAN se enrutarán por separado y no usarán el modelo de salida directo local. El siguiente diagrama representa este modelo de salida directa local.

![Arquitectura de red de salida local](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

La arquitectura de salida local tiene las siguientes ventajas para el tráfico de red de Microsoft 365 en el modelo tradicional:
  
- Ofrece rendimiento óptimo de Microsoft 365 al optimizar la longitud de la ruta. Las conexiones de usuario final se enrutan dinámicamente al punto de entrada de Microsoft 365 más cercano por parte de la infraestructura de _puerta de acceso del servicio distribuido_ de Microsoft Global Network y el tráfico se enruta internamente a los puntos de conexión de datos y servicios a través de fibra de alta disponibilidad de latencia ultra baja de Microsoft.
- Reduce la carga de la infraestructura de red corporativa al permitir la salida local para el tráfico de Microsoft 365, al omitir los proxies y los dispositivos de inspección de tráfico.
- Protege las conexiones en ambos extremos aprovechando la seguridad de los extremos de cliente y las características de seguridad en la nube, evitando la aplicación de tecnologías de seguridad de red redundantes.

> [!NOTE]
> La infraestructura de _puerta frontal de servicio distribuido_ es el perímetro de red de alta disponibilidad y escalabilidad de Microsoft Global Network con ubicaciones geográficamente distribuidas. Termina las conexiones de usuario final y las enruta de manera eficaz dentro de la red global de Microsoft. Puede obtener más información sobre la Red Global de Microsoft en [Cómo construye Microsoft su red global rápida y confiable](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Para obtener más información sobre cómo comprender y aplicar los principios de conectividad de red de Microsoft 365, consulte [microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).

## <a name="conclusion"></a>Conclusión

La optimización del rendimiento de red de Microsoft 365 realmente se reduce a la eliminación de obstáculos innecesarios. Al tratar las conexiones de Microsoft 365 como tráfico de confianza, puede evitar que la latencia se agregue mediante la inspección de paquetes y la competencia para el ancho de banda de proxy. Permitir conexiones locales entre los equipos cliente y los puntos de conexión de Office 365 permite enrutar dinámicamente el tráfico a través de la red global de Microsoft.

## <a name="related-topics"></a>Temas relacionados

[Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Administrar puntos de conexión de Office 365](managing-office-365-endpoints.md)

[Direcciones URL e intervalos de direcciones IP de Office 365](urls-and-ip-address-ranges.md)

[Dirección IP de Office 365 y servicio web de URL](microsoft-365-ip-web-service.md)

[Evaluar la conectividad de red de Microsoft 365](assessing-network-connectivity.md)

[Planeamiento de red y ajuste del rendimiento para Microsoft 365](network-planning-and-performance.md)

[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](performance-tuning-using-baselines-and-history.md)

[Plan de solución de problemas de rendimiento para Office 365](performance-troubleshooting-plan.md)

[Redes de entrega de contenido](content-delivery-networks.md)

[Prueba de conectividad de Microsoft 365](https://aka.ms/netonboard)

[Cómo construye Microsoft su red global rápida y confiable](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog de redes de Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)