---
title: Configuración de seguridad de la protección con protección contra alteraciones
ms.reviewer: pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Usa la protección contra manipulaciones para evitar que las aplicaciones malintencionadas cambien la configuración de seguridad importante.
keywords: malware, defender, antivirus, protección contra manipulaciones
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 06/23/2021
ms.openlocfilehash: 2e0724900de30629292cdcdc055d3ad3a1867b20
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105421"
---
# <a name="protect-security-settings-with-tamper-protection"></a>Configuración de seguridad de la protección con protección contra alteraciones

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

La protección contra alteraciones está disponible para dispositivos que ejecutan una de las siguientes versiones de Windows:

- Windows 10
- Windows Server 2019
- Windows Servidor, versión 1803 o posterior
- Windows Server 2016

## <a name="overview"></a>Información general

Durante algunos tipos de ataques cibernéticos, los actores malos intentan deshabilitar las características de seguridad, como la protección antivirus, en las máquinas. A los actores malintencionados les gusta deshabilitar las características de seguridad para obtener un acceso más fácil a los datos, para instalar malware o para aprovechar sus datos, identidades y dispositivos. La protección contra alteraciones ayuda a evitar que se produzcan este tipo de cosas.

Con la protección contra manipulaciones, las aplicaciones malintencionadas no pueden realizar acciones como:

- Deshabilitar la protección contra virus y amenazas
- Deshabilitar la protección en tiempo real
- Desactivar la supervisión del comportamiento
- Deshabilitar antivirus (como IOfficeAntivirus (IOAV))
- Deshabilitar la protección entregada en la nube
- Eliminación de actualizaciones de inteligencia de seguridad

### <a name="how-it-works"></a>Cómo funciona

La protección contra alteraciones bloquea Antivirus de Microsoft Defender sus valores seguros y predeterminados e impide que la configuración de seguridad se cambie a través de aplicaciones y métodos como:

- Configuración de la configuración en el Editor del Registro en el Windows dispositivo
- Cambiar la configuración mediante cmdlets de PowerShell
- Edición o eliminación de la configuración de seguridad a través de la directiva de grupo

La protección contra alteraciones no le impide ver la configuración de seguridad. Además, la protección contra alteraciones no afecta a la forma en que las aplicaciones antivirus de terceros se registran con la Seguridad de Windows aplicación. Si su organización usa Windows 10 Enterprise E5, los usuarios individuales no pueden cambiar la configuración de protección contra alteraciones; en esos casos, la protección contra alteraciones la administra el equipo de seguridad.

### <a name="what-do-you-want-to-do"></a>¿Qué quiere hacer?

| Para realizar esta tarea... | Vea esta sección... |
|:---|:---|
| Administrar la protección contra alteraciones en el espacio empresarial <p>Use el Centro de seguridad de Microsoft Defender para activar o desactivar la protección contra manipulaciones | [Administrar la protección contra alteraciones de la organización mediante el Centro de seguridad de Microsoft Defender](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) |
| Ajustar la configuración de protección contra alteraciones en la organización <p>Usa Intune (Microsoft Endpoint Manager) para activar o desactivar la protección contra alteraciones. Puede configurar la protección contra manipulaciones para algunos o todos los usuarios con este método. | [Administrar la protección contra alteraciones de la organización con Intune](#manage-tamper-protection-for-your-organization-using-intune) |
| Activar o desactivar la protección contra alteraciones para su organización con Configuration Manager | [Administrar la protección contra alteraciones de la organización mediante la conexión de inquilinos con Configuration Manager, versión 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006) |
| Activar (o desactivar) la protección contra manipulaciones para un dispositivo individual | [Administrar la protección contra alteraciones en un dispositivo individual](#manage-tamper-protection-on-an-individual-device) |
| Ver detalles sobre intentos de manipulación en dispositivos | [Ver información sobre intentos de manipulación](#view-information-about-tampering-attempts) |
| Revisar las recomendaciones de seguridad | [Revisar recomendaciones de seguridad](#review-your-security-recommendations) |
| Revisar la lista de preguntas más frecuentes (preguntas frecuentes) | [Examinar las preguntas frecuentes](#view-information-about-tampering-attempts) |

Según el método o la herramienta de administración que use para habilitar la protección contra manipulaciones, puede haber una dependencia de la protección entregada en la nube. 

En la tabla siguiente se proporcionan detalles sobre los métodos, herramientas y dependencias.

| Cómo se habilita la protección contra manipulaciones  | Dependencia de la protección entregada en la nube (MAPS)    |
|:----|:----|
| Microsoft Intune  | No |
| Microsoft Endpoint Configuration Manager + agregado de inquilino  |     No  |
| Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )    |     Sí |
| Microsoft 365 Defender portal ( [https://security.microsoft.com](https://security.microsoft.com) )  |     Sí  |

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center"></a>Administrar la protección contra alteraciones de la organización mediante el Centro de seguridad de Microsoft Defender

La protección contra alteraciones puede estar activada o desactivada para el inquilino mediante el Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). Estos son algunos puntos a tener en cuenta:

- Actualmente, la opción para administrar la protección contra alteraciones en el Centro de seguridad de Microsoft Defender está activa de forma predeterminada para las nuevas implementaciones. Para las implementaciones existentes, la protección contra alteraciones está disponible de forma opt-in, con planes para optar por el método predeterminado en un futuro próximo. (Para participar, en el Centro de seguridad de Microsoft Defender, elija **Configuración**  >  **Características avanzadas**  >  **Protección contra alteraciones**.) 

- Cuando usa el Centro de seguridad de Microsoft Defender para administrar la protección contra alteraciones, no tiene que usar Intune ni el método de adjuntar inquilino.

- Al administrar la protección contra alteraciones en el Centro de seguridad de Microsoft Defender, la configuración se aplica en todo el espacio empresarial, lo que afecta a todos los dispositivos que ejecutan Windows 10, Windows Server 2016 o Windows Server 2019. Para ajustar la protección contra manipulaciones (por ejemplo, tener la protección contra manipulaciones en algunos dispositivos, pero desactivada para otros), use [Intune](#manage-tamper-protection-for-your-organization-using-intune) o Configuration Manager con el inquilino [adjuntado](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006).

- Si tienes un entorno híbrido, las opciones de protección contra alteraciones configuradas en Intune tienen prioridad sobre las opciones configuradas en el Centro de seguridad de Microsoft Defender. 

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-defender-security-center"></a>Requisitos para administrar la protección contra alteraciones en el Centro de seguridad de Microsoft Defender

- Debe tener los permisos [adecuados,](/microsoft-365/security/defender-endpoint/assign-portal-access)como el administrador global, el administrador de seguridad o las operaciones de seguridad.

- Los dispositivos Windows deben ejecutar una de las siguientes versiones de Windows:

   - Windows 10
   - [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
   - Windows Servidor, versión [1803](/windows/release-health/status-windows-10-1803) o posterior
   - [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
   - Para obtener más información acerca de las [versiones, vea Windows 10 información de la versión](/windows/release-health/release-information).

- Los dispositivos deben [incorporarse a Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint/onboarding).

- Los dispositivos deben usar la versión 4.18.2010.7 (o superior) de la plataforma antimalware y el motor antimalware versión 1.1.17600.5 (o superior). ([Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md).)

- [La protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) debe estar activada.

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-defender-security-center"></a>Active (o desactive) la protección contra manipulaciones en el Centro de seguridad de Microsoft Defender 

![Activar la protección contra alteraciones en el Centro de seguridad de Microsoft Defender](images/mde-turn-tamperprotect-on.png)

1. Vaya al Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e inicie sesión.

2. Elija **Configuración**.

3. Vaya a **Características**  >  **avanzadas generales** y, a continuación, active la protección contra manipulaciones.

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a>Administrar la protección contra alteraciones de la organización con Intune

Si forma parte del equipo de seguridad de su organización y la suscripción incluye [Intune,](/intune/fundamentals/what-is-intune)puede activar (o desactivar) la protección contra manipulaciones de su organización en el Centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ). Usa Intune cuando quieras ajustar la configuración de protección contra alteraciones. Por ejemplo, si quieres habilitar la protección contra manipulaciones en algunos dispositivos, pero no todos, usa Intune.

### <a name="requirements-for-managing-tamper-protection-in-intune"></a>Requisitos para administrar la protección contra alteraciones en Intune

- Debe tener los permisos [adecuados,](/microsoft-365/security/defender-endpoint/assign-portal-access)como el administrador global, el administrador de seguridad o las operaciones de seguridad.

- Su organización usa [Intune para administrar dispositivos](/intune/fundamentals/what-is-device-management). ([Las licencias de Intune](/intune/fundamentals/licenses) son necesarias; Intune se incluye en Microsoft 365 E5).)

- Los dispositivos Windows deben ejecutarse Windows 10 sistema operativo [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) o posterior. (Para obtener más información acerca de las versiones, [vea Windows 10 información de la versión](/windows/release-health/release-information)).)

- Debe usar la seguridad Windows con inteligencia de seguridad [actualizada](https://www.microsoft.com/wdsi/definitions) a la versión 1.287.60.0 (o superior).

- Los dispositivos deben usar la versión 4.18.1906.3 (o superior) de la plataforma antimalware y el motor antimalware versión 1.1.15500.X (o posterior). ([Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md).)

### <a name="turn-tamper-protection-on-or-off-in-intune"></a>Activar o desactivar la protección contra manipulaciones en Intune

![Activar la protección contra alteraciones con Intune](images/turnontamperprotect-MEM.png)

1. Vaya al Centro [Microsoft Endpoint Manager administración](https://endpoint.microsoft.com) e inicie sesión con su cuenta laboral o educativa.

2. Seleccione   >  **Perfiles de configuración de dispositivos**.

3. Cree un perfil que incluya la siguiente configuración:

    - **Plataforma: Windows 10 y versiones posteriores**
    - **Tipo de perfil: Protección de puntos de conexión**
    - **Categoría: Centro de seguridad de Microsoft Defender**
    - **Protección contra alteraciones: habilitada**

4. Asigne el perfil a uno o varios grupos.

### <a name="are-you-using-windows-server-2016-or-windows-version-1709-1803-or-1809"></a>¿Está usando Windows Server 2016 o Windows versión 1709, 1803 o 1809?

Si usas Windows Server 2016, Windows 10 versión 1709, 1803 o [1809,](/windows/release-health/status-windows-10-1809-and-windows-server-2019)no verás  protección contra alteraciones en la Seguridad de Windows aplicación. En su lugar, puede usar PowerShell para determinar si la protección contra manipulaciones está habilitada. 
   
Al Windows Server 2016, la Configuración no reflejará con precisión el estado de la protección en tiempo real cuando se habilita la protección contra alteraciones.
   
#### <a name="use-powershell-to-determine-whether-tamper-protection-andor-real-time-protection-are-turned-on"></a>Usar PowerShell para determinar si la protección contra alteraciones o la protección en tiempo real están activadas

1. Abre la Windows PowerShell aplicación.

2. Use el cmdlet [De PowerShell Get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps)

3. En la lista de resultados, busque `IsTamperProtected` o `RealTimeProtectionEnabled` . (Un valor de *true significa* que la protección contra manipulaciones está habilitada).

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a>Administrar la protección contra alteraciones de su organización con Configuration Manager, versión 2006

Si usa la versión [2006](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)de Configuration Manager, puede administrar la configuración de protección contra alteraciones en Windows 10, Windows Server 2016 y Windows Server 2019 mediante un método denominado inquilino *adjunta*. La conexión de inquilino permite sincronizar los dispositivos de Configuration Manager locales en el Centro de administración de Microsoft Endpoint Manager y, a continuación, entregar directivas de configuración de seguridad de puntos de conexión a colecciones locales & dispositivos.

:::image type="content" source="images/win-security- exp-policy-endpt-security.png" alt-text="Seguridad de Windows experiencia en Endpoint Manager":::

> [!NOTE]
> El procedimiento se puede usar para extender la protección contra alteraciones a dispositivos que ejecutan Windows 10 y Windows Server 2019. Asegúrese de revisar los requisitos previos y otra información en los recursos mencionados en este procedimiento.

1. Configurar la conexión de inquilino. Para obtener más información, [consulte Microsoft Endpoint Manager tenant attach: Device sync and device actions](/mem/configmgr/tenant-attach/device-sync-actions).

2. En el [centro Microsoft Endpoint Manager administración,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a Endpoint **security** Antivirus y, a continuación,  >  elija + **Crear directiva.** 

   - En la **lista** Plataforma, **seleccione Windows 10 y Windows Server (ConfigMgr).**  
   - En la **lista Perfil,** **seleccione Seguridad de Windows experiencia (versión preliminar).** <br/>

3. Implemente la directiva en la colección de dispositivos.

### <a name="need-help-with-this-method"></a>¿Necesita ayuda con este método? 

Vea los siguientes recursos:

- [Configuración para el perfil Seguridad de Windows experiencia en Microsoft Intune](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [Blog de Community técnico: Anuncio de protección contra manipulaciones para clientes de conexión de inquilinos de Configuration Manager](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a>Administrar la protección contra alteraciones en un dispositivo individual

> [!NOTE]
> La protección contra alteraciones bloquea los intentos de modificar Antivirus de Microsoft Defender configuración a través del Registro.
>
> Para garantizar que la protección contra alteraciones no interfiera con los productos de seguridad de  terceros o los scripts de instalación empresarial que modifican esta configuración, vaya **a Seguridad de Windows** y actualice la inteligencia de seguridad a la versión 1.287.60.0 o posterior. (Vea [Actualizaciones de inteligencia de seguridad](https://www.microsoft.com/wdsi/definitions).)
>
> Una vez que haya realizado esta actualización, la protección contra alteraciones continúa protegiendo la configuración del Registro y los registros intentan modificarlos sin devolver errores.

Si eres usuario principal o no estás sujeto a la configuración administrada por un equipo de seguridad, puedes usar la aplicación Seguridad de Windows para administrar la protección contra alteraciones. Debes tener permisos de administrador adecuados en el dispositivo para cambiar la configuración de seguridad, como la protección contra alteraciones.

Esto es lo que ves en la Seguridad de Windows aplicación:

![Protección contra alteraciones activada en Windows 10 Home](images/tamperprotectionturnedon.png)

1. Seleccione **Inicio** y empiece a escribir *Seguridad*. En los resultados de búsqueda, **seleccione Seguridad de Windows**.

2. Seleccione **Protección contra & virus y &** de protección contra  >  **amenazas**.

3. Establezca **Protección contra alteraciones** **en On** o **Off**.

## <a name="view-information-about-tampering-attempts"></a>Ver información sobre intentos de manipulación

Los intentos de manipulación suelen indicar ataques cibernéticos más grandes. Los actores no detectados intentan cambiar la configuración de seguridad como una forma de persistir y no detectarse. Si forma parte del equipo de seguridad de su organización, puede ver información sobre estos intentos y, a continuación, realizar las acciones adecuadas para mitigar las amenazas.

Cuando se detecta un intento de manipulación, se genera una alerta en el [Centro de seguridad de Microsoft Defender](/microsoft-365/security/defender-endpoint/portal-overview) ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

![Centro de seguridad de Microsoft Defender](images/tamperattemptalert.png)

Con [detección y respuesta de puntos de conexión](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) y [capacidades avanzadas](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) de búsqueda en Microsoft Defender para endpoint, el equipo de operaciones de seguridad puede investigar y solucionar estos intentos.

## <a name="review-your-security-recommendations"></a>Revisar las recomendaciones de seguridad

La protección contra alteraciones se integra [con las & de administración de vulnerabilidades.](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) [Las recomendaciones de seguridad](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) incluyen asegurarse de que la protección contra manipulaciones está activada. Por ejemplo, puede buscar en *tamper*. En los resultados, puedes seleccionar **Activar protección contra** manipulaciones para obtener más información y activarla.

![Activar la protección contra manipulaciones](images/tamperprotectsecurityrecos.png)

Para obtener más información acerca de la administración & vulnerabilidad de amenazas, vea [Threat & Vulnerability Management en Centro de seguridad de Microsoft Defender](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center).

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="to-which-windows-os-versions-is-configuring-tamper-protection-is-applicable"></a>¿A qué Windows se aplica la protección contra alteraciones en las versiones del sistema operativo?

Windows 10 Sistema operativo [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)o posterior junto con [Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint).

Si usa Configuration Manager, versión 2006, con la conexión de inquilino, la protección contra alteraciones se puede extender a Windows Server 2019. Vea [Tenant attach: Create and deploy endpoint security Antivirus policy from the admin center (preview).](/mem/configmgr/tenant-attach/deploy-antivirus-policy)

### <a name="will-tamper-protection-have-any-impact-on-third-party-antivirus-registration"></a>¿La protección contra alteraciones tendrá algún impacto en el registro de antivirus de terceros?

No. Las ofertas antivirus de terceros se seguirán registrando con la Seguridad de Windows aplicación.

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a>¿Qué sucede si Antivirus de Microsoft Defender está activo en un dispositivo?

Los dispositivos que se incorpore a Microsoft Defender para Endpoint tendrán Antivirus de Microsoft Defender en modo pasivo. La protección contra alteraciones seguirá protegiendo el servicio y sus características. 

### <a name="how-can-i-turn-tamper-protection-onoff"></a>¿Cómo puedo activar y desactivar la protección contra manipulaciones?

Si eres usuario principal, consulta [Administrar la protección contra manipulaciones en un dispositivo individual.](#manage-tamper-protection-on-an-individual-device)

Si es una organización que usa [Microsoft Defender para](/microsoft-365/security/defender-endpoint)endpoint, debería poder administrar la protección contra alteraciones en Intune de forma similar a la forma en que administra otras características de protección de puntos de conexión. Vea las siguientes secciones de este artículo: 

- [Administrar la protección contra alteraciones con Intune](#manage-tamper-protection-for-your-organization-using-intune)
- [Administrar la protección contra alteraciones con Configuration Manager, versión 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [Administrar la protección contra alteraciones mediante el Centro de seguridad de Microsoft Defender](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) 

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-through-my-group-policy"></a>¿Cómo afecta la configuración de la protección contra alteraciones en Intune la forma en que Antivirus de Microsoft Defender a través de mi directiva de grupo?

La directiva de grupo normal no se aplica a la protección contra alteraciones y los cambios en la configuración de Antivirus de Microsoft Defender se omiten cuando la protección contra alteraciones está en. 

### <a name="for-microsoft-defender-for-endpoint-is-configuring-tamper-protection-in-intune-targeted-to-the-entire-organization-only"></a>Para Microsoft Defender para endpoint, ¿la configuración de la protección contra alteraciones en Intune está dirigida únicamente a toda la organización?

La configuración de la protección contra alteraciones en Intune Microsoft Endpoint Manager puede dirigirse a toda la organización y a dispositivos y grupos de usuarios específicos.

### <a name="can-i-configure-tamper-protection-in-microsoft-endpoint-configuration-manager"></a>¿Puedo configurar la protección contra alteraciones en Microsoft Endpoint Configuration Manager?

Si usa la conexión de inquilino, puede usar Microsoft Endpoint Configuration Manager. Vea los siguientes recursos:
- [Administrar la protección contra alteraciones de su organización con Configuration Manager, versión 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [Blog de Community técnico: Anuncio de protección contra alteraciones para clientes de inquilinos de Configuration Manager](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a>Tengo la inscripción Windows E3. ¿Puedo usar la configuración de la protección contra alteraciones en Intune?

Actualmente, la configuración de la protección contra alteraciones en Intune solo está disponible para los clientes que tienen [Microsoft Defender para Endpoint](/microsoft-365/security/defender-endpoint).

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a>¿Qué sucede si intento cambiar la configuración de Microsoft Defender para puntos de conexión en Intune, Microsoft Endpoint Configuration Manager y Windows Management Instrumentation cuando la protección contra alteraciones está habilitada en un dispositivo?

No podrá cambiar las características protegidas por la protección contra manipulaciones; dichas solicitudes de cambio se omiten.

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a>Soy un cliente de empresa. ¿Pueden los administradores locales cambiar la protección contra alteraciones en sus dispositivos?

No. Los administradores locales no pueden cambiar ni modificar la configuración de protección contra alteraciones.

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a>¿Qué sucede si mi dispositivo está incorporado con Microsoft Defender para endpoint y, a continuación, pasa a un estado desaborde?

Si un dispositivo está desactivado de Microsoft Defender para endpoint, la protección contra manipulaciones está activada, que es el estado predeterminado para los dispositivos no administrados. 

### <a name="will-there-be-an-alert-about-tamper-protection-status-changing-in-the-microsoft-defender-security-center"></a>¿Habrá una alerta sobre el cambio del estado de protección contra alteraciones en el Centro de seguridad de Microsoft Defender?

Sí. La alerta se muestra en [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) **Alertas**.

El equipo de operaciones de seguridad también puede usar consultas de búsqueda, como el ejemplo siguiente:

`DeviceAlertEvents | where Title == "Tamper Protection bypass"`

[Ver información sobre intentos de manipulación](#view-information-about-tampering-attempts).

## <a name="see-also"></a>Ver también

[Ayudar a proteger Windows equipos con Endpoint Protection para Microsoft Intune](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[Obtener información general sobre Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint)

[Mejor juntos: Antivirus de Microsoft Defender y Microsoft Defender para punto de conexión](why-use-microsoft-defender-antivirus.md)
