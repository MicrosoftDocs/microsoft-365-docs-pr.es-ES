---
title: Configurar notificaciones de Antivirus de Microsoft Defender
description: Obtenga información sobre cómo configurar y personalizar notificaciones de Antivirus estándar y adicionales de Microsoft Defender en puntos de conexión.
keywords: notificaciones, defender, antivirus, punto de conexión, administración, administrador
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a91da48f27450d6f4a6fd2b9607aa979458ccf71
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765100"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>Configurar las notificaciones que aparecen en los puntos de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

En Windows 10, las notificaciones de aplicaciones sobre detección y corrección de malware son más sólidas, coherentes y concisos.

Las notificaciones aparecen en los puntos de conexión cuando se desencadenan manualmente y se completan los exámenes programados y se detectan amenazas. Estas notificaciones también aparecen en el **Centro** de notificaciones y aparecen un resumen de exámenes y detecciones de amenazas en intervalos de tiempo regulares.

También puede configurar cómo aparecen las notificaciones estándar en los puntos de conexión, como las notificaciones para el reinicio o cuando se ha detectado y corregido una amenaza.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>Configurar las notificaciones adicionales que aparecen en los puntos de conexión

Puedes configurar la presentación de notificaciones adicionales, como resúmenes recientes de detección de amenazas, en la aplicación Seguridad de [Windows](microsoft-defender-security-center-antivirus.md) y con la directiva de grupo.

> [!NOTE]
> En Windows 10, versión 1607, la característica se llamaba **Notificaciones mejoradas** y se podía configurar en **Windows Settings** Update &  >  **seguridad**  >  **Windows Defender**. En configuración de directiva de grupo en todas las versiones de Windows 10, se denomina **Notificaciones mejoradas.**

> [!IMPORTANT]
> Deshabilitar notificaciones adicionales no deshabilitará las notificaciones críticas, como alertas de detección de amenazas y de corrección.

**Usa la aplicación Seguridad de Windows para deshabilitar notificaciones adicionales:**

1. Abre la aplicación Seguridad de Windows haciendo clic en el icono de escudo de la barra de tareas o buscando en el menú inicio de **Defender**.

2. Haga clic **en el icono Protección contra &** virus (o en el icono de escudo de la barra de menús izquierda) y, a continuación, en la etiqueta & **de** protección contra amenazas:

    ![Captura de pantalla de la etiqueta & de protección contra amenazas de virus en la aplicación Seguridad de Windows](images/defender/wdav-protection-settings-wdsc.png)

3. Desplácese a la **sección Notificaciones** y haga clic en Cambiar configuración **de notificación.**

4. Deslice el conmutador **a Desactivado** o **Encendido para** deshabilitar o habilitar notificaciones adicionales.

**Use la directiva de grupo para deshabilitar notificaciones adicionales:**

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**

3. Haga clic **en Plantillas administrativas**.

4. Expande el árbol a **componentes de Windows > Microsoft Defender Antivirus > Reporting**.

5. Haga doble clic **en Desactivar notificaciones mejoradas** y establezca la opción en **Habilitado**. Haga clic en **Aceptar**. Esto impedirá que aparezcan notificaciones adicionales.

## <a name="configure-standard-notifications-on-endpoints"></a>Configurar notificaciones estándar en puntos de conexión

Puede usar la directiva de grupo para:

- Mostrar texto adicional y personalizado en los puntos de conexión cuando el usuario necesita realizar una acción
- Ocultar todas las notificaciones en puntos de conexión
- Ocultar notificaciones de reinicio en puntos de conexión

Ocultar notificaciones puede ser útil en situaciones en las que no se puede ocultar toda la interfaz antivirus de Microsoft Defender. Consulta [Impedir que los usuarios vean o interactúen con la interfaz](prevent-end-user-interaction-microsoft-defender-antivirus.md) de usuario de Antivirus de Microsoft Defender para obtener más información. 

> [!NOTE]
> Las notificaciones ocultas solo se producirán en los puntos de conexión en los que se ha implementado la directiva. Las notificaciones relacionadas con las acciones que deben realizarse (como un reinicio) seguirán apareciendo en el panel de supervisión e informes de [Microsoft Endpoint Manager Endpoint Protection](/configmgr/protect/deploy-use/monitor-endpoint-protection). 

Consulta [Personalizar la aplicación seguridad de Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) para tu organización para obtener instrucciones para agregar información de contacto personalizada a las notificaciones que los usuarios ven en sus máquinas.

**Use la directiva de grupo para ocultar las notificaciones:**

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo **y** haga clic en **Plantillas administrativas.**

3. Expande el árbol a **componentes de Windows > Microsoft Defender Antivirus > interfaz de cliente.** 

4. Haga doble clic **en Suprimir todas las notificaciones** y establezca la opción en **Habilitado**. Haga clic en **Aceptar**. Esto impedirá que aparezcan notificaciones adicionales.

**Use la directiva de grupo para ocultar las notificaciones de reinicio:**

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**

3. Haga clic **en Plantillas administrativas**.

4. Expande el árbol a **componentes de Windows > Microsoft Defender Antivirus > interfaz de cliente.**

5. Haz doble clic **en Suprimir notificaciones de reinicio** y establece la opción en **Habilitado**. Haga clic en **Aceptar**. Esto impedirá que aparezcan notificaciones adicionales.

## <a name="related-topics"></a>Temas relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Configurar la interacción del usuario final con Antivirus de Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md)