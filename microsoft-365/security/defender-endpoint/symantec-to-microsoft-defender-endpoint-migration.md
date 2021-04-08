---
title: Migrar de Symantec a Microsoft Defender para endpoint
description: Obtenga información general sobre cómo cambiar de Symantec a Microsoft Defender para endpoint
keywords: migración, protección contra amenazas avanzada de Windows Defender, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-symantecmigrate
- m365solution-overview
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 6517359c805bb449d075e401283a79a791461630
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218803"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a>Migrar de Symantec a Microsoft Defender para endpoint
Si planea cambiar de Symantec Endpoint Protection (Symantec) a [Microsoft Defender para Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender para Endpoint), está en el lugar correcto. Use este artículo como guía.

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

:::image type="content" source="images/symantec-mde-migration.png" alt-text="Información general sobre la migración de Symantec a Defender para endpoint":::

Al cambiar de Symantec a Defender para endpoint, comienza con la solución de Symantec en modo activo, configura Defender para Endpoint en modo pasivo, se incorpora a Defender para endpoint y, a continuación, establece Defender for Endpoint en modo activo y quita Symantec.

## <a name="the-migration-process"></a>Proceso de migración

Al cambiar de Symantec a Microsoft Defender para Endpoint, se sigue un proceso que se puede dividir en tres fases, tal como se describe en la tabla siguiente:

![Fases de migración: preparar, configurar, incorporar](images/phase-diagrams/migration-phases.png)

|Fase |Descripción |
|--|--|
|[Preparar la migración](symantec-to-microsoft-defender-atp-prepare.md) |Durante la **fase de** preparación, obtienes Microsoft Defender para Endpoint, planeas tus roles y permisos y concedes acceso al Centro de seguridad de Microsoft Defender. También configuras el proxy de dispositivo y la configuración de Internet para habilitar la comunicación entre los dispositivos de la organización y Microsoft Defender para endpoint. |
|[Configurar Microsoft Defender para endpoint](symantec-to-microsoft-defender-atp-setup.md) |Durante la **fase de** configuración, se configuran las opciones y exclusiones para Antivirus de Microsoft Defender, Microsoft Defender para endpoints y Symantec Endpoint Protection. También creas grupos de dispositivos, colecciones y unidades organizativas. Por último, se configuran las directivas antimalware y la configuración de protección en tiempo real.|
|[Incorporación a Microsoft Defender para endpoint](symantec-to-microsoft-defender-atp-onboard.md) |Durante la **fase de** incorporación, incorporas los dispositivos a Microsoft Defender para endpoint y compruebas que dichos dispositivos se comunican con Microsoft Defender para Endpoint. Por último, desinstala Symantec y asegúrate de que la protección a través de Microsoft Defender para Endpoint esté en modo activo. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>¿Qué se incluye en Microsoft Defender para endpoint?

En esta guía de [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) migración, nos [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) centramos en la protección de última generación y las capacidades de detección y respuesta de puntos de conexión como punto de partida para pasar a Microsoft Defender para endpoint. Sin embargo, Microsoft Defender para endpoint incluye mucho más que antivirus y protección de puntos de conexión. Microsoft Defender para punto de conexión es una plataforma unificada para la protección preventiva, la detección posterior a la vulneración y la respuesta e investigación automatizadas. En la tabla siguiente se resumen las características y capacidades de Microsoft Defender para endpoint. 

| Característica/funcionalidad | Descripción |
|---|---|
| [Administración & vulnerabilidades de amenazas](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | Las & de administración de vulnerabilidades ayudan a identificar, evaluar y corregir puntos débiles en los puntos de conexión (como dispositivos). |
| [Reducción de la superficie expuesta a ataques](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | Las reglas de reducción de superficie de ataque ayudan a proteger los dispositivos y aplicaciones de la organización de ciberamenazas y ataques. |
| [Protección de última generación](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | La protección de última generación incluye Antivirus de Microsoft Defender para ayudar a bloquear amenazas y malware. |
| [Detección y respuesta de puntos de conexión.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | Las capacidades de detección y respuesta de puntos de conexión detectan, investigan y responden a intentos de intrusión e infracciones activas.  |
| [Búsqueda avanzada](advanced-hunting-overview.md) | Las capacidades avanzadas de búsqueda permiten al equipo de operaciones de seguridad localizar indicadores y entidades de amenazas conocidas o potenciales. |
| [Bloqueo y contención del comportamiento](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | Las capacidades de bloqueo y contención del comportamiento ayudan a identificar y detener las amenazas, en función de sus comportamientos y de los árboles de proceso incluso cuando la amenaza ha comenzado a ejecutarse. |
| [Investigación y corrección automatizadas](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | Las capacidades automatizadas de investigación y respuesta examinan las alertas y toman medidas de corrección inmediatas para resolver infracciones. |
| [Servicio de búsqueda de amenazas](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Expertos en amenazas de Microsoft) | Los servicios de búsqueda de amenazas proporcionan a los equipos de operaciones de seguridad supervisión y análisis de nivel de expertos, y para ayudar a garantizar que no se pierden las amenazas críticas. |

**¿Desea obtener más información? Consulta [Microsoft Defender para Endpoint](https://docs.microsoft.com/windows/security/threat-protection).**

## <a name="next-step"></a>Paso siguiente

- Continúe con [Prepare for your migration](symantec-to-microsoft-defender-atp-prepare.md).