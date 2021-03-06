---
title: Administración de registros en Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Con la administración de registros de Microsoft 365, puede aplicar programaciones de retención en un plan de archivos para administrar la retención, la declaración de registros y la eliminación.
ms.openlocfilehash: 1af3ff5fac9a95afb15f680f8f46e8d0de0b4567
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226052"
---
# <a name="learn-about-records-management-in-microsoft-365"></a>Aprenda sobre la administración de registros en Microsoft 365

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Las organizaciones de todo tipo requieren una solución de administración de registros para administrar los registros reglamentarios, legales y críticos para el negocio en sus datos corporativos. La administración de registros de Microsoft 365 ayuda a las organizaciones a administrar sus obligaciones legales, ofrece la posibilidad de demostrar el cumplimiento de las normativas y aumenta la eficiencia con la eliminación regular de elementos que ya no se necesitan retener, no son de gran valor o ya no son necesarios para fines empresariales.

Use las siguientes funciones para dar soporte a la solución de administración de registros en Microsoft 365:

- **Etiquetar contenido como un registro**. Cree y configure etiquetas de retención para marcar el contenido como un [registro](#records) que pueden ser aplicadas por los usuarios o aplicadas automáticamente al identificar palabras clave, tipos de contenido o información confidencial.

- **Migrar y administrar los requisitos de retención con el plan de archivos**. Si usa un [plan de archivo](file-plan-manager.md), puede agregar un plan de retención existente a Microsoft 365 o crear uno nuevo para las funciones de administración mejoradas.

- **Configure las opciones de retención y eliminación con etiquetas de retención**. Configure [etiquetas de retención](retention.md#retention-labels) con los períodos de retención y las acciones en función de varios factores que incluyan la fecha de la última modificación o creación.

- **Inicie diferentes períodos de retención cuando se produzca un evento** con la [retención basada en eventos](event-driven-retention.md).

- **Revisar y validar la eliminación** con [la revisión de eliminación](disposition.md#disposition-reviews) y la prueba de [eliminación de registros](disposition.md#disposition-of-records).

- **Exportar la información sobre todos los elementos que se han eliminado** con la [opción exportar](disposition.md#filter-and-export-the-views).

- **Configurar permisos específicos** para las funciones del administrador de registros en su organización para [tener el acceso correcto](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

Con estas funciones, puede incorporar los requisitos y las programaciones de retención de su organización en una solución de administración de registros para administrar la retención, la declaración de registros y la eliminación para dar soporte a todo el ciclo de vida del contenido.

Además de la documentación en línea, es posible que le resulte útil escuchar la [grabación del seminario web](https://aka.ms/MIPC/Video-RecordsManagementWebinar) para la administración de registros y descargar la [presentación acompañante con preguntas más frecuentes](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).

## <a name="records"></a>Registros

Cuando el contenido se declara como registro:

- Se colocan restricciones en los elementos relativas a qué [acciones se permiten o se bloquean](#compare-restrictions-for-what-actions-are-allowed-or-blocked).

- Se registran otras actividades sobre el elemento.

- Tendrá la prueba de la eliminación cuando se eliminen los elementos al final de su período de retención.

Usted utiliza las [etiquetas de retención](retention.md#retention-labels) para marcar contenido como un **registro** o un **registro normativo**. La diferencia entre estas dos etiquetas se explica en la siguiente sección. Puede publicar esas etiquetas de modo que los usuarios y administradores puedan aplicarlas manualmente al contenido o aplicarlas automáticamente al contenido que desee marcar como registro o como registro normativo.

Al usar las etiquetas de retención para declarar registros, puede implementar una sola estrategia de administración de registros uniforme en todo el entorno de Microsoft 365.

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>Comparar restricciones de acciones permitidas o bloqueadas

Use la tabla siguiente para identificar qué restricciones se colocan en el contenido como resultado de aplicar una etiqueta de retención estándar y conocer las etiquetas de retención que marcan el contenido como un registro o un registro normativo.

Una etiqueta de retención estándar tiene opciones de retención y acciones, pero no marca el contenido como un registro o un registro normativo.

> [!NOTE]
> Por motivos de integridad, la tabla contiene columnas para un registro bloqueado y desbloqueado, lo que se aplica a SharePoint y OneDrive, pero no a Exchange. La capacidad de bloquear y desbloquear un registro usa el [control de versiones de registros](record-versioning.md) que no es compatible con los elementos de Exchange. Por lo tanto, para todos los elementos de Exchange que estén marcados como un registro, el comportamiento que se asigna a la columna **registro bloqueado** y a la columna **registro desbloqueado** no es relevante.


|Acción| Etiqueta de retención |Registro: bloqueado| Registro: desbloqueado| Registro normativo |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Editar contenidos|Permitido | **Bloqueado** | Permitido | **Bloqueado**|
|Editar propiedades, incluido cambiar nombre|Permitido |Permitido | Permitido| **Bloqueado**|
|Eliminar|Permitido<sup>1</sup> |**Bloqueado** |**Bloqueado**| **Bloqueado**|
|Copiar|Permitido |Permitido | Permitido| Permitido|
|Moverse dentro del contenedor<sup>2</sup>|Permitido |Permitido | Permitido| Permitido|
|Moverse entre contenedores<sup>2</sup>|Permitido |Permitido si nunca se desbloquea | **Bloqueado** | **Bloqueado**|
|Abrir y leer|Permitido |Permitido | Permitido| Permitido|
|Cambiar etiqueta|Permitido |Permitido: solo administradores del contenedor | Permitido: solo administradores del contenedor| **Bloqueado**
|Quitar etiqueta|Permitido |Permitido: solo administradores del contenedor | Permitido: solo administradores del contenedor| **Bloqueado**

Notas al pie:

<sup>1</sup> Compatible con OneDrive y Exchange reteniendo una copia en una ubicación segura, pero bloqueado por SharePoint.

Cuando se aplica una etiqueta de retención a un elemento de lista que tiene datos adjuntos de documento, ese documento no hereda la configuración de retención y se puede eliminar del elemento de lista. En cambio, si se declara un registro con una etiqueta de retención, los datos adjuntos del documento heredarán la configuración de retención y no se podrán eliminar.

<sup>2</sup> Los contenedores incluyen librerías de documentos de SharePoint, cuentas de OneDrive y buzones de Exchange.

> [!IMPORTANT]
> La diferencia más importante que supone un registro normativo es que, una vez que se aplica al contenido, nadie, ni siquiera un administrador global, puede quitar la etiqueta.
>
> Las etiquetas de retención configuradas para los registros normativos también tienen las siguientes restricciones de administrador:
>
> - El período de retención no se puede reducir después de guardar la etiqueta, solo se puede extender.
> - Estas etiquetas no son compatibles con las directivas de etiquetado automático y deben aplicarse mediante [directivas de etiqueta de retención](create-apply-retention-labels.md).
>
> Además, no se puede aplicar una etiqueta normativa a un documento que está desprotegido en SharePoint.
>
> Dado que se trata de acciones irreversibles y restricciones, asegúrese de que realmente necesita usar registros normativos antes de seleccionar esta opción para las etiquetas de retención. Para evitar la configuración accidental, esta opción no está disponible de forma predeterminada, sino que primero se debe habilitar con PowerShell. Las instrucciones se incluyen en [Declarar registros mediante etiquetas de retención](declare-records.md).

## <a name="configuration-guidance"></a>Instrucciones de configuración

Consulte [Introducción a la administración de registros](get-started-with-records-management.md). Este artículo contiene información sobre suscripciones, permisos y vínculos a instrucciones de configuración de un extremo a otro para escenarios de administración de registros.