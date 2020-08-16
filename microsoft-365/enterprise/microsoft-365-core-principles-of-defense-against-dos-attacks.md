---
title: Principios básicos de Microsoft 365 sobre la defensa contra ataques por denegación de servicio
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
description: Modo en que Microsoft usa los principios principales de absorción, detección y mitigación en su defensa contra ataques por denegación de servicio (DoS).
ms.openlocfilehash: b04ec717f7c97e44c6ed4011156666e8c27f06c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693827"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a>Principios básicos de la defensa contra ataques por denegación de servicio

Los tres principios básicos para defenderse contra los ataques DoS basados en la red son la absorción, la detección y la mitigación. La absorción se produce antes de la detección y la detección se produce antes de la mitigación. La absorción es la mejor protección contra un ataque DoS. Si el ataque no se puede detectar, no se puede mitigar. Pero, incluso si no se puede absorber el ataque a DoS más pequeño, los servicios no se mantendrán durante el tiempo suficiente para que se detecte el ataque.

La mayoría de las organizaciones no son viables económicamente para adquirir la capacidad excesiva para absorber ataques de DoS, ya que esto requiere una gran inversión en la tecnología y las habilidades técnicas. Esto destaca una de las ventajas de seguridad de usar los servicios en la nube de Microsoft. La gran escala de los servicios de Microsoft proporciona una sólida protección de red a los clientes de la nube de una manera rentable. Pero incluso a gran escala, debe haber un equilibrio entre la absorción, la detección y la mitigación. Para encontrar ese saldo, Microsoft estudia las tasas de crecimiento de los ataques para calcular la cantidad que necesita absorber Microsoft.

La detección es un juego de gato y de mouse. Debe buscar constantemente nuevas formas de que los usuarios sean atacados e intenten derrotar a sus sistemas. Detect-> mitigate-> detecte-> mitigate, etc., es un estado persistente permanente que sigue indefinidamente.

## <a name="defending-against-dos-attacks"></a>Defensa contra ataques DoS

Para defenderse correctamente contra un ataque DoS, la detección temprana es esencial. Al detectar un ataque antes de que el sistema esté saturado, los defensores pueden ejecutar un plan de respuesta.

La siguiente fórmula ayuda a aproximar el tiempo de impacto de un ataque DoS:

   **Capacidad máxima (en bytes/seg.)/velocidad de crecimiento (en bytes/seg.) = tiempo de impacto (en segundos)**

Si el tiempo de detección se produce después del tiempo de impacto, es probable que el ataque de DoS se realice correctamente. Si el tiempo de detección se produce antes del tiempo de impacto, los servicios atacados deben permanecer en línea y ser accesibles si se usan estrategias de mitigación. Por lo tanto, solo se pueden hacer dos cosas para defenderse contra ataques DoS:

- Aumente la capacidad para aumentar el límite máximo de capacidad (lo que, a su vez, proporciona más tiempo para detectar un ataque); o
- Reducir el tiempo de detección.

El aumento de la capacidad tiene un impacto fiscal directo. Microsoft recomienda que los clientes desarrollen una capacidad de absorción básica mínima para garantizar que pueden sobrevivir a algún ataque de DoS niveles. La capacidad de absorción real varía de un cliente a un cliente, ya que cada cliente tiene sus propios umbrales para la exposición, el riesgo y la inversión financiera. Por motivos económicos, las inversiones en investigación y tiempo para reducir el tiempo de detección suelen ser la defensa más rentable.