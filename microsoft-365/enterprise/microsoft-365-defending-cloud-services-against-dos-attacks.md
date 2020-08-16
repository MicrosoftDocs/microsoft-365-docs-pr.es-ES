---
title: Defensa de los servicios en la nube de Microsoft 365 contra ataques por denegación de servicio
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: En este artículo, obtenga información sobre cómo Microsoft defiende sus servicios en la nube contra ataques por denegación de servicio (DoS).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 26c3df54811ffee06797c635bc565fcbe78b58fa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694110"
---
# <a name="defending-microsoft-365-cloud-services-against-denial-of-service-attacks"></a>Defensa de los servicios en la nube de Microsoft 365 contra ataques por denegación de servicio

Los centros de recursos de Microsoft están protegidos por seguridad de defensa en profundidad que incluye entradas de perímetro, cámaras de vídeo, personal de seguridad y entradas seguras que usan la biometría, la tarjeta inteligente y la autenticación multifactor. La seguridad de defensa en profundidad sigue en todas las áreas de la instalación y en cada unidad física del servidor. La [infraestructura de nube de Microsoft y el grupo de operaciones](https://www.microsoft.com/cloud-platform/global-datacenters) proporcionan la infraestructura básica y las tecnologías de base para nuestros servicios en la nube. Nuestros centros de recursos cumplen con los estándares de la industria para la seguridad y la confiabilidad física y son administrados, supervisados y administrados por el personal de operaciones de Microsoft.

Para proteger aún más nuestros servicios en la nube, Microsoft proporciona un sistema de defensa DDoS que forma parte de los procesos de supervisión continua de Microsoft Azure y pruebas de penetración. El sistema de defensa DDoS de Azure está diseñado no solo para resistir ataques desde el exterior, sino también desde otros inquilinos de Azure. Azure usa técnicas de detección y mitigación estándar como cookies SYN, limitación de velocidad y límites de conexión para proteger contra ataques DDoS.

Los servicios en la nube de Microsoft están sujetos a la amenaza de ataque de varios orígenes. Para mitigar y proteger contra las distintas amenazas de DoS, se ha desarrollado e implementado un sistema de detección y mitigación de amenazas dinámico y escalable de Azure con el objetivo principal de proteger la infraestructura subyacente frente a ataques DoS y ayudar a evitar interrupciones del servicio para los clientes de servicios en la nube. El sistema de mitigación de DoS de Azure protege el tráfico entrante, saliente y de región a región.

La mayoría de los ataques de DoS se inician con destinos en las capas de red (L3) y transporte (L4) del modelo de [interconexión de sistemas abiertos](https://docs.microsoft.com/windows-hardware/drivers/network/windows-network-architecture-and-the-osi-model) (OSI). Los ataques dirigidos a las capas L3 y L4 están diseñados para inundar una interfaz o servicio de red con tráfico de ataque para saturar los recursos y denegar la capacidad de responder al tráfico legítimo. En concreto, los ataques L3 y L4 intentan saturar la capacidad de los vínculos de red, dispositivos o servicios o saturar las CPU de los servidores o las máquinas virtuales que admiten una aplicación.

Para protegerse contra ataques de L3 y L4 Microsoft ha diseñado, desarrollado e implementado una solución dirigida específicamente a proteger la infraestructura y los objetivos de los clientes que se encuentren en ataque al proteger estos niveles. La protección de la infraestructura asegura que el tráfico de ataques dirigido a un cliente no dé lugar a daños o a la calidad de servicio de la red de otros clientes. La solución usa los datos de muestreo de tráfico de los enrutadores del centro de datos. El servicio de supervisión de red analiza estos datos para detectar los ataques. Cuando se detecta un ataque, los mecanismos de defensa automatizada se expulsan.

## <a name="application-level-defenses"></a>Defensas en el nivel de aplicación
Microsoft Engineering Teams sigue los rigurosos estándares establecidos por el [aseguramiento de la seguridad operativa de Microsoft](https://www.microsoft.com/SDL/OperationalSecurityAssurance) para ayudar a proteger los datos de los clientes. Los servicios en la nube de Microsoft se crean de forma intencionada para admitir una carga muy alta, así como para proteger y mitigar los ataques de DoS en el nivel de aplicación. Hemos implementado una arquitectura escalada en la que los servicios se distribuyen en varios centros de información global con características de limitación y aislamiento regionales en algunas de las cargas de trabajo.

El país o la región de cada cliente, que identifica el administrador del cliente durante la configuración inicial de los servicios, determina la ubicación de almacenamiento principal de los datos del cliente. Los datos de los clientes se replican entre centros de datos redundantes de acuerdo con una estrategia principal/de copia de seguridad. Un centro de datos principal hospeda el software de la aplicación junto con todos los datos principales del cliente que se ejecutan en el software. Un centro de recursos de copia de seguridad proporciona conmutación por error automática. Si el centro de datos principal deja de funcionar por algún motivo, las solicitudes se redirigen a la copia del software y los datos del cliente en el centro de datos de copia de seguridad. En cualquier momento dado, los datos de los clientes se pueden procesar en el centro de datos principal o de copia de seguridad. La distribución de datos en varios centros de datos reduce el área de superficie afectada en caso de que un centro de datos sea atacado. Además, los servicios del centro de recursos afectado pueden redirigirse rápidamente al centro de recursos secundario como uno de los mecanismos de recuperación y viceversa (Redirigido de vuelta al centro de recursos principal una vez que se restaura el servicio).

Las cargas de trabajo individuales incluyen características integradas que administran la utilización de recursos. Por ejemplo, los mecanismos de limitación de peticiones de Exchange Online y SharePoint Online forman parte de un enfoque de varias capas para defenderse contra ataques DoS. La limitación de usuarios de Exchange Online se basa en el nivel de recursos consumido por el usuario final, independientemente de si los recursos están en Active Directory, el almacén de información de Exchange online o en otro lugar. Se asigna un presupuesto a cada cliente para limitar los recursos consumidos por un usuario. La limitación de Exchange Online para la actividad de los usuarios y los componentes del sistema se basa en la administración de la [carga de trabajo](https://technet.microsoft.com/library/jj150503(v=exchg.150).aspx). Una carga de trabajo de Exchange Online es una característica, un protocolo o un servicio de Exchange en línea que se ha definido explícitamente para la administración de recursos del sistema de Exchange Online. Cada carga de trabajo de Exchange Online requiere recursos del sistema como CPU, operaciones de base de datos de buzones o solicitudes de Active Directory para realizar solicitudes de usuario o trabajos en segundo plano. Entre los ejemplos de cargas de trabajo de Exchange Online se incluyen Outlook en la web, Exchange ActiveSync, migración de buzones de correo y asistentes de buzones. Los administradores de inquilinos pueden administrar la configuración de limitación de la carga de trabajo de Exchange para los usuarios con el shell de administración de Exchange. Hay varias formas de limitación que se han implementado dentro de Exchange Online, como PowerShell, servicios web Exchange y POP e IMAP, Exchange ActiveSync, conexiones para dispositivos móviles, destinatarios y mucho más. Aunque los administradores de las implementaciones de Exchange locales pueden configurar las directivas de limitación, los administradores no pueden configurar directivas de limitación para Exchange Online.

El desencadenador más común para la limitación en SharePoint Online es el código del modelo de objetos de cliente (CSOM) que realiza demasiadas acciones en una frecuencia demasiado alta. Con CSOM, se pueden realizar muchas acciones con una única solicitud, que puede exceder los límites de uso y causar una limitación por usuario.

Independientemente de la actividad que pueda dar como resultado la limitación, cuando un usuario supere los límites de uso, SharePoint Online acelerará las solicitudes posteriores de esa cuenta de usuario, normalmente durante un breve período. Mientras una limitación de usuarios está en vigor, todas las acciones de ese usuario se limitan hasta que expira el acelerador, según los siguientes criterios:
- Para las solicitudes realizadas por el usuario directamente en un explorador, SharePoint Online redirige a una página de información de limitación y las solicitudes producen un error.
- Para todas las demás solicitudes, incluidas las llamadas CSOM, SharePoint Online devuelve el código de Estado HTTP 429 ("demasiadas solicitudes") y las solicitudes producen un error.

Si el proceso problemático sigue superando los límites de uso, SharePoint Online puede bloquear completamente el proceso y devolver el código de Estado HTTP 503 ("servicio no disponible").

## <a name="vulnerability-and-penetration-testing"></a>Vulnerabilidad y pruebas de penetración
Microsoft usa muchas [tecnologías y prácticas de seguridad](https://www.microsoft.com/trustcenter/security/threatmanagement) para [proteger su infraestructura en la nube](https://blogs.technet.microsoft.com/hybridcloud/2015/05/05/protecting-your-datacenter-and-cloud-from-emerging-threats/) y las redes locales contra amenazas modernas y sofisticadas, como el uso de componentes y servicios antimalware para servicios en la nube, máquinas virtuales (VM) y otros sistemas. Advanced Threat Analytics, que supervisa los patrones de uso normales para redes, sistemas y usuarios, y emplea el aprendizaje de la máquina para marcar cualquier comportamiento que esté fuera de las pruebas de penetración ordinarias y normales.

Además de realizar nuestras propias pruebas de penetración y ofrecer a nuestros clientes un [programa de pruebas de penetración unificada en la nube de Microsoft](https://technet.microsoft.com/mt784683), también nos animamos con los profesionales de la seguridad de terceros que realizan valoraciones regulares de vulnerabilidad y pruebas de penetración en nuestros servicios en la nube. Los informes de estas evaluaciones de vulnerabilidad de terceros están disponibles para su descarga desde los portales de [confianza de servicio](https://aka.ms/STP) y de [seguridad del servicio](https://aka.ms/ServiceAssurance) .