---
title: Características de vista previa en Microsoft 365 Defender
description: Conozca las nuevas características de la seguridad de Microsoft 365
keywords: Versión preliminar, novedades, seguridad m365, seguridad, 365, funciones
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 088dbd16c3667331843ff934c80f85aa8d3a837f
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430821"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender de vista previa

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

El Microsoft 365 Defender se actualiza constantemente para incluir nuevas mejoras y capacidades de características.

Obtenga información sobre las nuevas características de Microsoft 365 Defender versión preliminar y sea uno de los primeros en probar las próximas características al activar la experiencia de vista previa.

Para obtener más información sobre las nuevas funcionalidades que están disponibles en general, vea [Novedades de Microsoft 365 Defender](whats-new.md).

 ## <a name="what-you-need-to-know"></a>Lo que necesita saber

Al trabajar con características en versión preliminar pública, estas características:

- Puede que tenga funciones restringidas o limitadas. Por ejemplo, la característica solo puede aplicarse a una plataforma.
- Normalmente, pasan por los cambios de características antes de que estén generalmente disponibles (GA).
- Son totalmente compatibles con Microsoft.
- Solo puede estar disponible en regiones geográficas seleccionadas o entornos en la nube. Por ejemplo, es posible que la característica no exista en la nube del gobierno.
- Las características individuales de la versión preliminar pueden tener más restricciones de uso y compatibilidad. Si es así, esta información se indica normalmente en la documentación de características.
- Las versiones preliminares se proporcionan con un nivel de soporte estándar y se pueden usar para entornos de producción. 



## <a name="required-permissions"></a>Permisos necesarios

Las cuentas asignadas a Azure Active Directory (Azure AD) pueden activar las Microsoft 365 Defender vista previa:

- Administrador global
- Administrador de seguridad
- Operador de seguridad

## <a name="turn-on-preview-features"></a>Activar la versión preliminar de las características

Tendrás acceso a las próximas características sobre las que puedes proporcionar comentarios para mejorar la experiencia general antes de que las características estén disponibles en general.

Active la configuración de la experiencia de la versión preliminar para estar entre los primeros en probar las próximas características.

1. En el panel de navegación, seleccione **Configuración**.
2. Seleccione **Microsoft 365 Defender**.
3. Seleccione **Versión preliminar de las características** > **Activar la versión preliminar de las características**. 
4. Seleccione **Guardar**.

Sabrá que tiene activada la versión preliminar de las características cuando vea que la casilla **Activar versión preliminar de las características** está seleccionada. 

## <a name="preview-features"></a>Versión preliminar de las características

Las siguientes características y mejoras están disponibles actualmente en la versión preliminar:

- **[Ver informes por etiquetas de amenazas:](threat-analytics.md#view-reports-per-threat-tags)** las etiquetas de amenazas le ayudan a centrarse en categorías de amenazas específicas y revisar los informes más relevantes.
- **[API de](../defender-endpoint/raw-data-export.md)** streaming: Microsoft 365 Defender permite transmitir todos los eventos disponibles a través de búsqueda avanzada a un centro de eventos o una cuenta de Almacenamiento de Azure.
- **[Microsoft 365 Defender API:](api-overview.md)** las API de nivel superior Microsoft 365 Defender le permitirán automatizar flujos de trabajo basados en las tablas de búsqueda avanzadas y de incidentes compartidos. 
- **[Tomar medidas en la búsqueda avanzada:](advanced-hunting-take-action.md)** contiene rápidamente amenazas o aborda los activos comprometidos que encuentras en la [búsqueda avanzada.](advanced-hunting-overview.md)
- **[Referencia de esquema en el portal:](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** obtenga información sobre las tablas de esquema de búsqueda avanzada directamente en el centro de seguridad. Además de las descripciones de tabla y columna, esta referencia incluye tipos de eventos admitidos `ActionType` (valores) y consultas de ejemplo.
- **[Función DeviceFromIP():](advanced-hunting-devicefromip-function.md)** obtenga información sobre los dispositivos a los que se ha asignado una dirección IP específica o direcciones en un intervalo de tiempo determinado.
