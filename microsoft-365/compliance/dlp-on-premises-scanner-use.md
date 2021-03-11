---
title: Usar el examinador de prevención de pérdida de datos locales de Microsoft 365 (versión preliminar)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Obtenga información sobre cómo usar el examinador local de prevención de pérdida de datos de Microsoft 365 para examinar los datos almacenados e implementar las acciones de protección para los recursos compartidos de archivos locales y las carpetas y bibliotecas de documentos de SharePoint local.
ms.openlocfilehash: 34be93f5c9980a7f8ea8ad31b708af14a8725f73
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "50417393"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a>Usar el examinador de prevención de pérdida de datos locales de Microsoft 365 (versión preliminar)

Para ayudarle a familiarizarse con las características de DLP locales y la forma en la que se muestran en las directivas DLP, hemos recopilado algunos escenarios que puede seguir.

> [!IMPORTANT]
> Estos escenarios DLP locales no son los procedimientos oficiales para crear y optimizar directivas DLP. Consulte los temas siguientes cuando necesite trabajar con directivas DLP en situaciones generales:
>- [Información general sobre la prevención de pérdida de datos](data-loss-prevention-policies.md)
>- [Introducción a la directiva predeterminada de DLP](get-started-with-the-default-dlp-policy.md)
>- [Crear una directiva DLP a partir de una plantilla](create-a-dlp-policy-from-a-template.md)
>- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a>Escenario: Descubrir los archivos que coinciden con las reglas DLP

Los datos del examinador de DLP local aparecen en varias áreas

#### <a name="activity-explorer"></a>Explorador de actividad

 Microsoft DLP para el entorno local detecta coincidencias de reglas DLP e informa de ellas en [Explorador de actividad](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer). 
 
#### <a name="microsoft-365-audit-log"></a>Registro de auditoría de Microsoft 365

Durante la versión preliminar pública, las coincidencias de reglas DLP están disponibles en la interfaz de usuario del registro de auditoría. Vea [Buscar en el registro de auditoría del Centro de cumplimiento](search-the-audit-log-in-security-and-compliance.md) o use [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) en PowerShell.

#### <a name="aip"></a>AIP

Los datos de descubrimiento legal están disponibles en un informe local en formato CSV que se almacena en:

**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.

 Busque las columnas siguientes:
- Modo de DLP
- Estado de DLP
- Comentario de DLP
- Acciones de DLP de nombre de regla DLP
- Propietario
- Permisos NTFS actuales (SDDL)
- Permisos NTFS aplicados (SDDL)
- Tipo de permisos NTFS
 
### <a name="scenario-enforce-dlp-rule"></a>Escenario: exigir regla DLP 

Si quiere exigir las reglas DLP en los archivos examinados, debe habilitarse la obligación de aplicarlas en el trabajo de análisis de contenido en AIP y a nivel de directiva en DLP.


#### <a name="configure-dlp-to-enforce-policy-actions"></a>Configurar DLP para obligar a aplicar acciones de directiva

1. Abra la página [Prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies) y seleccione la directiva DLP dirigida a los repositorios de ubicación locales que haya configurado en AIP. 
2. Edite la directiva.
3. En la página **Probar o habilitar la directiva**, seleccione **Sí, activar inmediatamente**. 

## <a name="see-also"></a>Vea también

- [Obtener información acerca del examinador local DLP (vista previa)](dlp-on-premises-scanner-learn.md)
- [Introducción al examinador local DLP (vista previa)](dlp-on-premises-scanner-get-started.md)
- [Información general sobre la prevención de pérdida de datos](data-loss-prevention-policies.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Introducción al explorador de actividad](data-classification-activity-explorer.md)