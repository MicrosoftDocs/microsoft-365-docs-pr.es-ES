---
title: Gobernanza de aplicaciones en Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Implemente funcionalidades de gobernanza de aplicaciones de Microsoft para controlar sus aplicaciones.
ms.openlocfilehash: 63bd6684bc041c3c82ba6b8ddcc28c2600182b26
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430701"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a>Complemento de gobernanza de aplicaciones para Microsoft Cloud App Security (en versión preliminar)

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Los ciberataques se han vuelto cada vez más sofisticados en las formas en que aprovechan las aplicaciones que ha implementado en sus infraestructuras locales y en la nube, estableciendo un punto de partida para la elevación de privilegios, el movimiento lateral y la filtración de los datos. Para comprender los posibles riesgos y detener estos tipos de ataques, debe obtener una visibilidad clara de la posición de cumplimiento de aplicaciones de su organización para identificar rápidamente cuándo una aplicación muestra comportamientos anómalos y responder cuando estos comportamientos presentan riesgos para su entorno, datos y usuarios.

La característica de complemento de gobernanza de aplicaciones para Microsoft Cloud App Security es una funcionalidad de administración de directivas y seguridad diseñada para aplicaciones habilitadas para OAuth que acceden a datos de Microsoft 365 a través de Microsoft Graph APIs. La gobernanza de aplicaciones ofrece visibilidad, corrección y gobernanza completas sobre cómo estas aplicaciones y sus usuarios acceden, usan y comparten sus datos confidenciales almacenados en Microsoft 365 a través de información útil, y alertas y acciones de directivas automatizadas.

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

La gobernanza de aplicaciones le proporciona una solución completa:

- **Información**: consulte una vista de todas las aplicaciones de terceros para la plataforma de Microsoft 365 en su usuario en un único panel. Puede ver todos los estados de las aplicaciones y las actividades de alerta, y reaccionar o responder a ellas.
- **Gobernanza**: cree directivas proactivas o reactivas para patrones y comportamientos de aplicaciones y usuarios, y proteja a los usuarios contra el uso de aplicaciones no compatibles o malintencionadas limitando el acceso de aplicaciones de riesgo a sus datos.
- **Detección**: reciba alertas y notificaciones cuando haya anomalías en la actividad de la aplicación y cuando se usen aplicaciones no compatibles, malintencionadas o de riesgo.
- **Corrección**: junto con las capacidades de corrección automática, use controles de corrección de manera oportuna para responder a las detecciones de actividad anómala en las aplicaciones.

La gobernanza de aplicaciones es una solución basada en una plataforma que forma parte integral del ecosistema de aplicaciones de Microsoft 365. La gobernanza de aplicaciones supervisa y controla las aplicaciones habilitadas para OAuth que están registradas con Azure Active Directory (Azure AD) y acceden a los datos a través de la API de Microsoft Graph. La gobernanza de aplicaciones proporciona controles de comportamiento de la aplicación para ayudar a reforzar la posición de seguridad y cumplimiento de su infraestructura de TI.

<!--
Unlike other application governance products in the marketplace, MAPG is a platform-based solution that is an integral part of the Microsoft 365 application ecosystem. MAPG's initial focus is on OAuth-enabled apps published to the Microsoft 365 platform that are registered with Azure AD and access data through the Graph API. For the initial release, MAPG does not support other, non-OAuth-enabled M365 apps, add-ins (such as PowerBI), or other app vendor ecosystems such as Google, Facebook, Amazon Web Services, Workplace, and Salesforce. MAPG’s focus is on third-party published apps for the Microsoft 365 application platform.

Microsoft allows developers to build cloud applications using Azure Active Directory (Azure AD), Microsoft’s cloud identity platform, and other resources and access to tenant data through the Microsoft Graph. Because of MAPG's visibility, insights, and control capabilities, app developers have the incentive to comply with publisher verification, self-attestation, and Microsoft certification, and can build high-quality productivity apps that are secure and compliant.
-->

## <a name="a-first-glimpse-at-app-governance"></a>Primer vistazo a la gobernanza de aplicaciones

Para ver el panel de gobernanza de aplicaciones, diríjase a [https://aka.ms/appgovernance](https://aka.ms/appgovernance). Tenga en cuenta que su cuenta de inicio de sesión debe tener uno de los [roles de administrador](app-governance-get-started.md#administrator-roles) para ver cualquier dato de gobernanza de aplicaciones.

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a>Integración de gobernanza de aplicaciones con Azure AD y Microsoft Cloud App Security

La gobernanza de aplicaciones, Azure AD y Microsoft Cloud App Security recopilan y proporcionan diferentes conjuntos de datos:

- La gobernanza de aplicaciones proporciona información detallada sobre la actividad de una aplicación en el nivel de API.
- Azure AD proporciona metadatos de aplicaciones fundamentales e información detallada sobre los inicios de sesión en las aplicaciones.
- Microsoft Cloud App Security proporciona información de riesgo de la aplicación.

Al compartir información entre el gobierno de aplicaciones, Azure AD y Microsoft Cloud App Security, puede mostrar información agregada en un portal y vincular fácilmente a otro portal para obtener más información. Aquí hay unos ejemplos:

- Información de inicio de sesión de la aplicación en la gobernanza de aplicaciones:

  Desde el portal de gobernanza de aplicaciones, puede ver la actividad de inicio de sesión agregada de cada aplicación y volver a vincularla al centro de administración de Azure Active Directory para obtener los detalles de los eventos de inicio de sesión.

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- Información del uso de la API en el portal de Microsoft Cloud App Security:

  Desde el portal de Microsoft Cloud App Security, puede visualizar el nivel de uso de la API, la transferencia de datos agregados y el vínculo al portal de gobernanza de aplicaciones para obtener los detalles.

Este es un resumen de la integración.

![La Integración de gobernanza de aplicaciones con Azure AD y Microsoft Cloud App Security](..\media\manage-app-protection-governance\mapg-integration.png)

Además, la gobernanza de aplicaciones envía sus alertas como señales a Microsoft Cloud App Security y Microsoft 365 Defender, y la gobernanza de aplicaciones recibe alertas de Microsoft Cloud App Security para permitir un análisis más detallado de los incidentes de seguridad basados en aplicaciones.

<!--
Integration of alerts with MCAS and M365 Defender
Azure AD IP detections in progress to surface in M365 Defender

## Integration with Azure AD

**Feedback from Anand:** We should add some details on how MAPG works with M365 Defender (previously MTP). Also, we should highlight the integration with MCAS and AAD.

Key cross-reference resources:

- [What is application management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-application-management)
- [Common application management scenarios for Azure Active Directory (especially scenarios 3-4)](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Azure Active Directory Identity Governance documentation](https://docs.microsoft.com/azure/active-directory/governance/)
- [Managing access to apps using Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management)

## Integration with Microsoft Cloud App Security

Key cross-reference resources:

- [Cloud App Security anomaly detection alerts investigation guide](https://docs.microsoft.com/cloud-app-security/investigate-anomaly-alerts#unusual-addition-of-credentials-to-an-oauth-app)
- [Monitor alerts raised in Cloud App Security](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Control which third-party cloud OAuth apps get permissions](https://docs.microsoft.com/cloud-app-security/manage-app-permissions)

-->

## <a name="using-app-governance"></a>Uso de la gobernanza de aplicaciones

El uso de la gobernanza de aplicaciones para proteger su usuario y sus datos de aplicaciones potencialmente malignas o malintencionadas se divide en estas tres funcionalidades principales:

| Funcionalidad | Descripción |
|:-------|:-----|
| [Visibilidad e información de la aplicación](app-governance-visibility-insights-overview.md) | Obtenga una vista de 360° sobre el tráfico y la actividad de las aplicaciones de Microsoft 365 en su usuario. |
| [Directivas de aplicación para una gobernanza sólida](app-governance-app-policies-overview.md) | Cree directivas de aplicaciones proactivas o reactivas, lo cual le permitirá aplicar la gobernanza para sus aplicaciones de Microsoft 365. |
| [Detección y correcciones](app-governance-detect-remediate-overview.md) | En función de las alertas de detección de plataforma o las alertas de detección generadas por directivas, supervise sus aplicaciones en busca de comportamientos anómalos de aplicaciones y corríjalas, ya sea automáticamente en función de la configuración de la directiva de la aplicación o manualmente. |
|||
