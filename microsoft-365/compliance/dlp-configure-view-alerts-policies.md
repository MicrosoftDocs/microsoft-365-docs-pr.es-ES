---
title: Configurar y ver alertas para directivas de prevención de pérdida de datos
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo definir y administrar alertas para directivas de prevención de pérdida de datos.
ms.openlocfilehash: ee04f6080edcde86dc39c7f4aa43130223fee8bf
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750042"
---
# <a name="configure-and-view-alerts-for-data-loss-prevention-polices"></a>Configurar y ver alertas para las directivas de prevención de pérdida de datos

Las directivas de prevención de pérdida de datos (DLP) pueden tomar medidas de protección para evitar el uso compartido involuntario de elementos confidenciales. Cuando se hace una acción en un elemento confidencial, se le puede notificar configurando alertas para DLP. En este artículo se muestra cómo definir directivas de alerta enriquecciones vinculadas a las directivas de prevención de pérdida de datos (DLP). Verá cómo usar el nuevo panel de administración de alertas DLP en el centro de cumplimiento de [Microsoft 365](https://compliance.microsoft.com/) para ver alertas, eventos y metadatos asociados para infracciones de directivas DLP.

<!-- LEFT OFF HERE-->

## <a name="features"></a>Características

Las siguientes características forman parte de esto:

-   **Panel de administración de alertas DLP:** en el centro [de Microsoft 365](https://compliance.microsoft.com/)cumplimiento, este panel muestra alertas de directivas DLP que se aplican en las siguientes cargas de trabajo:

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   Dispositivos
-   **Opciones de configuración de alerta avanzada:** estas opciones forman parte del flujo de creación de directivas DLP. Úsenlos para crear configuraciones de alerta enriquecciones. Puede crear una alerta de un solo evento o una alerta agregada, según el número de eventos o el tamaño de los datos filtrados.

## <a name="before-you-begin"></a>Antes de empezar

Antes de comenzar, asegúrese de que tiene los requisitos previos necesarios:

-   Licencias para el panel de administración de alertas DLP
-   Licencias para opciones de configuración de alertas
-   Funciones

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Licencias para el panel de administración de alertas DLP

Todos los inquilinos elegibles para Office 365 DLP pueden acceder al nuevo panel de administración de alertas DLP. Para empezar, debes ser elegible para dlp Office 365 para Exchange Online, SharePoint Online y OneDrive para la Empresa. Para obtener más información acerca de los requisitos de licencia para Office 365 DLP, vea ¿Qué licencias proporcionan los derechos para que un usuario se beneficie [del servicio?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

Los clientes que usan [DLP](endpoint-dlp-learn-about.md) de extremo que son elegibles para [Teams DLP](dlp-microsoft-teams.md) verán sus alertas de directiva DLP de punto de conexión y Teams de directivas DLP en el panel de administración de alertas dlp.

### <a name="licensing-for-alert-configuration-options"></a>Licencias para opciones de configuración de alertas

-   Configuración de alerta de evento **único:** las organizaciones que tienen una suscripción A1, F1 o G1 o una suscripción A3 o G3 solo pueden crear directivas de alerta cuando se desencadena una alerta cada vez que se produce una actividad.
-   **Configuración de alerta agregada:** para configurar directivas de alerta agregadas basadas en un umbral, debe tener una de las siguientes configuraciones:
    -   Una suscripción A5 o G5
    -   Una suscripción E1, F1 o G1 o una suscripción A3 o G3 que incluye una de las siguientes características:
        -   Protección contra amenazas avanzada de Office 365 (plan 2)
        -   Cumplimiento de Microsoft 365 E5
        -   Microsoft 365 de complementos de eDiscovery y Audit

### <a name="roles"></a>Funciones

Si desea ver el panel de administración de alertas DLP o editar las opciones de configuración de alertas en una directiva DLP, debe ser miembro de uno de estos grupos de roles:

-   Administrador de cumplimiento
-   Administrador de datos de cumplimiento
-   Administrador de seguridad
-   Operador de seguridad
-   Lector de seguridad

Para obtener acceso al panel de administración de alertas DLP, necesita el rol Administrar alertas y cualquiera de los siguientes roles:

-   Administración de cumplimiento de DLP
-   View-Only de cumplimiento dlp

## <a name="alert-configuration-experience"></a>Experiencia de configuración de alertas

Si es elegible para opciones de configuración de alerta [agregadas,](#licensing-for-alert-configuration-options)verá las siguientes opciones en línea en la experiencia de creación de directivas DLP.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Captura de pantalla que muestra las opciones de los informes de incidentes para los usuarios que son aptos para opciones de configuración de alerta agregadas." border="false":::

Puede usar estas opciones de configuración de alertas para configurar una configuración que defina la frecuencia con la que se puede producir una coincidencia de reglas DLP antes de que se desencadene una alerta. Esta configuración permite configurar una directiva para generar una alerta cada vez que una actividad coincide con las condiciones de la directiva o cuando se supera un umbral determinado, en función del número de actividades o en función del volumen de datos exfiltrados.

Si es elegible para las [opciones](#licensing-for-alert-configuration-options)de configuración de alertas de un solo evento, verá la siguiente opción de configuración de alertas en la experiencia de creación de directivas DLP. Use esta opción para crear una alerta que se genera cada vez que se produce una coincidencia de regla DLP debido a una actividad del usuario.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Captura de pantalla que muestra las opciones de los informes de incidentes para los usuarios que son aptos para opciones de configuración de alertas de un solo evento." border="false":::

## <a name="dlp-alert-management-dashboard"></a>Panel de administración de alertas DLP

Para trabajar con el panel de administración de alertas DLP:

1.  En el [centro Microsoft 365 cumplimiento,](https://www.compliance.microsoft.com)vaya a **Prevención de pérdida de datos**.

2.  Seleccione la **pestaña Alertas** para ver el panel de alertas dlp.

    -   Elija filtros para refinar la lista de alertas. Elija **Personalizar columnas** para enumerar las propiedades que desea ver. También puede elegir ordenar las alertas en orden ascendente o descendente en cualquier columna.
    -   Seleccione una alerta para ver los detalles:

        :::image type="content" source="../media/alert-details.png" alt-text="Captura de pantalla que muestra detalles de alertas en el panel de administración de alertas DLP." border="false":::

1.  Seleccione la **pestaña Eventos** para ver todos los eventos asociados con la alerta. Puede elegir un evento en particular para ver sus detalles.
    En la tabla siguiente se muestran algunos de los detalles del evento.
    
    | Categoría          | Nombre de propiedad                 | Descripción                                                                | Tipos de eventos aplicables                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*Detalles del evento*||
    |      | Id                            | Identificador único asociado al evento                                        | Todos los eventos                               |
    |                   | Ubicación                      | Carga de trabajo donde se detectó el evento                                      | Todos los eventos                               |
    |                   | Tiempo de actividad              | Hora de la actividad del usuario que provocó la infracción de DLP                    | Todos los eventos                               |
    |*Entidades afectadas*||
    |  | Usuario                          | Usuario que causó la infracción de DLP                                          | Todos los eventos                               |
    |                   | Nombre de host                      | Nombre de host del equipo donde se detectó la infracción de DLP              | Eventos de dispositivos                           |
    |                   | Dirección IP                    | Dirección IP del equipo                                                  | Eventos de dispositivos                           |
    |                   | Ruta de acceso de archivo                     | Ruta absoluta del archivo implicado en la infracción                        | SharePoint, eventos OneDrive y Dispositivos |
    |                   | Destinatarios de correo electrónico              | Destinatarios del correo electrónico que infringió la directiva DLP                       | Exchange eventos                          |
    |                   | Asunto del correo electrónico                 | Asunto del correo electrónico que infringió la directiva DLP                          | Exchange eventos                          |
    |                   | Datos adjuntos de correo electrónico             | Nombres de los datos adjuntos del correo electrónico que infringió la directiva DLP         | Exchange eventos                          |
    |                   | Propietario del sitio                    | Nombre del propietario del sitio                                                     | SharePoint y OneDrive eventos           |
    |                   | Dirección URL del sitio                      | Dirección URL completa del SharePoint o OneDrive sitio                                | SharePoint y OneDrive eventos           |
    |                   | Archivo creado                  | Hora de creación de archivos                                                      | SharePoint y OneDrive eventos           |
    |                   | Archivo modificado por última vez            | Hora de la última modificación del archivo                                  | SharePoint y OneDrive eventos           |
    |                   | Tamaño de archivos                     | Tamaño del archivo                                                           | SharePoint y OneDrive eventos           |
    |                   | Propietario del archivo                    | Propietario del archivo                                                          | SharePoint y OneDrive eventos           |
    |*Detalles de la directiva*||
    |     | Directiva DLP coincidente            | Nombre de la directiva DLP coincidente                                    | Todos los eventos                               |
    |                   | Regla coincidente                  | Nombre de la regla DLP en la directiva DLP coincidente                    | Todos los eventos                               |
    |                   | Tipos de información confidencial detectados | Tipos de información confidencial que se detectaron como parte de la directiva DLP | Todos los eventos                               |
    |                   | Acciones realizadas                 | Acciones realizadas como parte de la directiva DLP coincidente                          | Todos los eventos                               |
    |                   | Directiva de sobresalto de usuario          | Si el usuario superó la directiva a través de la sugerencia de directiva                | Todos los eventos                               |
    |                   | Invalidar texto de justificación   | Justificación proporcionada para invalidar la sugerencia de directiva                          | Todos los eventos                               |
    
1.  Seleccione la **pestaña Tipos de información** confidencial para ver detalles sobre los tipos de información confidencial detectados en el contenido. Los detalles incluyen confianza y recuento.

2.  Después de investigar la alerta, elija **Administrar alerta** para cambiar el estado (**Active**, **Investigating**, **Dismissed** o **Resolved**). También puede agregar comentarios y asignar la alerta a alguien de su organización.

    -   Para ver el historial de administración de flujos de trabajo, elija **Registro de administración**.
    -   Después de realizar la acción necesaria para la alerta, establezca el estado de la alerta en **Resuelto**.