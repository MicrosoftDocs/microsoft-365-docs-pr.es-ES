---
title: Valores de nivel de queja masiva
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre los valores de nivel de queja masiva (BCL) que se usan en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11f884ec6b32795deba09c0f1ba88055a6422e9b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537948"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Nivel de queja masiva (BCL) en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 organizaciones con buzones en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, EOP asigna un nivel de queja masiva (BCL) a los mensajes entrantes de los buzones masivos. El BCL se agrega al mensaje en un encabezado X y es similar al nivel de confianza de correo no deseado [(SCL)](spam-confidence-levels.md) que se usa para identificar mensajes como correo no deseado. Un BCL más alto indica que un mensaje masivo es más probable que genere quejas (y, por lo tanto, es más probable que sea correo no deseado). Microsoft usa orígenes internos y de terceros para identificar el correo masivo y determinar el BCL adecuado.

Los remitentes masivos varían en sus patrones de envío, creación de contenido y prácticas de adquisición de destinatarios. Los buenos carteros masivos envían mensajes deseados con contenido relevante a sus suscriptores. Estos mensajes generan pocas quejas por parte de los destinatarios. Otros troyanos de envío masivo de correo electrónico envían mensajes no solicitados muy similares al correo no deseado y generan muchas quejas por parte de los destinatarios. Los mensajes de un correo masivo se conocen como correo masivo o correo gris.

 El filtrado de  correo no deseado marca los mensajes como correo electrónico masivo en función del umbral BCL (el valor predeterminado o un valor que especifique) y realiza la acción especificada en el mensaje (la acción predeterminada es entregar el mensaje a la carpeta correo no deseado del destinatario). Para obtener más información, vea [Configure anti-spam policies](configure-your-spam-filter-policies.md) y [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)

Puede usar la lista de inquilinos permitidos o bloqueados para configurar excepciones para el filtrado masivo de correo. Los mensajes de remitentes de los dominios especificados no reciben la acción para el veredicto de filtrado de **correo** no deseado masivo en directivas contra correo no deseado. Para obtener más información, vea [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).

Los umbrales BCL se describen en la tabla siguiente.

****

|BCL|Descripción|
|:---:|---|
|0|El mensaje no es de un remitente de correo masivo.|
|1, 2, 3|El mensaje proviene de un remitente de correo masivo que genera pocas quejas.|
|4, 5, 6, 7<sup>\*</sup>|El mensaje proviene de un remitente de correo masivo que genera un número mixto de quejas.|
|8, 9|El mensaje es de un remitente masivo que genera un gran número de quejas.|
|

<sup>\*</sup> Este es el valor de umbral predeterminado que se usa en las directivas contra correo no deseado.
