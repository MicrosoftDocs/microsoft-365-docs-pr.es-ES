---
title: Contención y bloqueo de comportamiento del cliente
description: El bloqueo de comportamiento del cliente forma parte de las capacidades de contención y bloqueo de comportamiento en Microsoft Defender para endpoint
keywords: bloqueo de comportamiento, protección rápida, comportamiento del cliente, Microsoft Defender para endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 83f269a13a54ee38b7e7a464d794d87ddbd7b520
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289936"
---
# <a name="client-behavioral-blocking"></a>Contención y bloqueo de comportamiento del cliente

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Información general

El bloqueo de comportamiento del cliente es un componente de las capacidades de [contención](behavioral-blocking-containment.md) y bloqueo de comportamiento en Defender para endpoint. A medida que se detectan comportamientos sospechosos en dispositivos (también denominados clientes o extremos), los artefactos (como archivos o aplicaciones) se bloquean, comprueban y corrigen automáticamente. 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Protección de cliente y nube":::

La protección antivirus funciona mejor cuando se combina con la protección en la nube.

## <a name="how-client-behavioral-blocking-works"></a>Cómo funciona el bloqueo de comportamiento del cliente

[Antivirus de Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md) detectar comportamientos sospechosos, código malintencionado, ataques sin archivos y en memoria, y mucho más en un dispositivo. Cuando se detectan comportamientos sospechosos, Antivirus de Microsoft Defender supervisa y envía esos comportamientos sospechosos y sus árboles de proceso al servicio de protección en la nube. El aprendizaje automático diferencia entre aplicaciones malintencionadas y comportamientos buenos en milisegundos y clasifica cada artefacto. En tiempo casi real, tan pronto como se encuentra que un artefacto es malintencionado, se bloquea en el dispositivo. 

Cada vez que se [](alerts-queue.md) detecta un comportamiento sospechoso, se genera una alerta y está visible en el [portal](microsoft-defender-security-center.md) de Microsoft 365 Defender (anteriormente el Centro de seguridad de Microsoft Defender).

El bloqueo de comportamiento del cliente es eficaz porque no solo ayuda a evitar que se inicie un ataque, sino que puede ayudar a detener un ataque que se ha comenzado a ejecutar. Además, con el [bloqueo de bucle de comentarios](feedback-loop-blocking.md) (otra capacidad de bloqueo y contención del comportamiento), se evitan ataques en otros dispositivos de la organización.

## <a name="behavior-based-detections"></a>Detecciones basadas en comportamiento

Las detecciones basadas en comportamiento se denominan según la [matriz de CK&MITRE ATT para Enterprise](https://attack.mitre.org/matrices/enterprise). La convención de nomenclatura ayuda a identificar la fase de ataque donde se observó el comportamiento malintencionado:

|Táctica | Nombre de la amenaza de detección |
|----|----|
|Acceso inicial | `Behavior:Win32/InitialAccess.*!ml` |
|Ejecución | `Behavior:Win32/Execution.*!ml` |
|Persistencia | `Behavior:Win32/Persistence.*!ml` |
|Escalamiento de privilegios | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|Evasión de defensa | `Behavior:Win32/DefenseEvasion.*!ml` |
|Acceso a credenciales | `Behavior:Win32/CredentialAccess.*!ml` |
|Descubrimiento | `Behavior:Win32/Discovery.*!ml` |
|Movimiento lateral | `Behavior:Win32/LateralMovement.*!ml` |
|Colección | `Behavior:Win32/Collection.*!ml` |
|Comando y control | `Behavior:Win32/CommandAndControl.*!ml` |
|Exfiltración | `Behavior:Win32/Exfiltration.*!ml` |
|Impacto | `Behavior:Win32/Impact.*!ml` |
|Sin categorizar | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> Para obtener más información acerca de las amenazas específicas, **[vea actividad de amenazas globales recientes](https://www.microsoft.com/wdsi/threats)**.

## <a name="configuring-client-behavioral-blocking"></a>Configuración del bloqueo de comportamiento del cliente

Si su organización usa Defender para endpoint, el bloqueo de comportamiento del cliente está habilitado de forma predeterminada. Sin embargo, para beneficiarse de todas las capacidades de Defender for Endpoint, incluido el bloqueo y la contención del [comportamiento,](behavioral-blocking-containment.md)asegúrese de que las siguientes características y capacidades de Defender para endpoint están habilitadas y configuradas:

- [Defender for Endpoint baselines](configure-machines-security-baseline.md)

- [Dispositivos incorporados a Defender para endpoint](onboard-configure.md)

- [EDR en modo bloqueo](edr-in-block-mode.md)

- [Reducción de la superficie expuesta a ataques](attack-surface-reduction.md)

- [Protección de última generación](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware y otras funcionalidades de protección contra amenazas)
