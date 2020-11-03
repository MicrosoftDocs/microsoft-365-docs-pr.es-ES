---
title: Dispositivos de Windows 10 incorporados que usan un script local
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Use un script local para implementar el paquete de configuración en dispositivos para que estén integrados en el servicio.
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769516"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="aa725-103">Dispositivos de Windows 10 incorporados que usan un script local</span><span class="sxs-lookup"><span data-stu-id="aa725-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="aa725-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="aa725-104">**Applies to:**</span></span>

- [<span data-ttu-id="aa725-105">Prevención de pérdida de datos (DLP) de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aa725-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="aa725-106">También puede incorporar dispositivos individuales de forma manual a la prevención de pérdida de datos de extremos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aa725-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="aa725-107">Es posible que desee hacerlo primero al probar el servicio antes de comprometerse a incorporar todos los dispositivos de la red.</span><span class="sxs-lookup"><span data-stu-id="aa725-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa725-108">Este script se ha optimizado para su uso en un máximo de 10 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="aa725-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="aa725-109">Para implementar a escala, use [otras opciones de implementación](dlp-configure-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="aa725-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="aa725-110">Por ejemplo, puede implementar un script de incorporación a más de 10 dispositivos en producción con el script disponible en dispositivos de [Windows 10 incorporados mediante la Directiva de grupo](dlp-configure-endpoints-gp.md).</span><span class="sxs-lookup"><span data-stu-id="aa725-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="aa725-111">Dispositivos integrados</span><span class="sxs-lookup"><span data-stu-id="aa725-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="aa725-112">Abra el archivo package. zip de configuración de GP ( *DeviceComplianceOnboardingPackage.zip* ) que ha descargado desde el Asistente de incorporación de servicios.</span><span class="sxs-lookup"><span data-stu-id="aa725-112">Open the GP configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="aa725-113">También puede obtener el paquete del [centro de cumplimiento de Microsoft](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="aa725-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="aa725-114">En el panel de navegación, seleccione incorporación de dispositivos de **configuración**  >  **Device onboarding** .</span><span class="sxs-lookup"><span data-stu-id="aa725-114">In the navigation pane, select **Settings** > **Device onboarding** .</span></span>

3. <span data-ttu-id="aa725-115">En el campo **método de implementación** , seleccione **script local** .</span><span class="sxs-lookup"><span data-stu-id="aa725-115">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="aa725-116">Haga clic en **Descargar paquete** y guarde el archivo. zip.</span><span class="sxs-lookup"><span data-stu-id="aa725-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="aa725-117">Extraiga el contenido del paquete de configuración en una ubicación del dispositivo que desee incorporar (por ejemplo, el escritorio).</span><span class="sxs-lookup"><span data-stu-id="aa725-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="aa725-118">Debe tener un archivo denominado *DeviceOnboardingScript. cmd* .</span><span class="sxs-lookup"><span data-stu-id="aa725-118">You should have a file named *DeviceOnboardingScript.cmd* .</span></span>

6.  <span data-ttu-id="aa725-119">Abra un mensaje de la línea de comandos con privilegios elevados en el dispositivo y ejecute el script:</span><span class="sxs-lookup"><span data-stu-id="aa725-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="aa725-120">Vaya a **Inicio** y escriba **cmd** .</span><span class="sxs-lookup"><span data-stu-id="aa725-120">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="aa725-121">Haga clic con el botón secundario en **símbolo del sistema** y seleccione **Ejecutar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="aa725-121">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![Menú de inicio de ventana que apunta a ejecutar como administrador](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="aa725-123">Escriba la ubicación del archivo de script.</span><span class="sxs-lookup"><span data-stu-id="aa725-123">Type the location of the script file.</span></span> <span data-ttu-id="aa725-124">Si copió el archivo en el escritorio, escriba: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="aa725-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="aa725-125">Presione la tecla **entrar** o haga clic en **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="aa725-125">Press the **Enter** key or click **OK** .</span></span>

<span data-ttu-id="aa725-126">Para obtener información sobre cómo validar manualmente que el dispositivo es compatible y notifica correctamente los datos de los sensores, consulte [solucionar problemas de incorporación de la protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span><span class="sxs-lookup"><span data-stu-id="aa725-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="aa725-127">Dispositivos desincorpora con un script local</span><span class="sxs-lookup"><span data-stu-id="aa725-127">Offboard devices using a local script</span></span>
<span data-ttu-id="aa725-128">Por motivos de seguridad, el paquete que se usa para desincorpora dispositivos expirará 30 días después de la fecha en que se descargó.</span><span class="sxs-lookup"><span data-stu-id="aa725-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="aa725-129">Los paquetes de retirada expirados enviados a un dispositivo se rechazarán.</span><span class="sxs-lookup"><span data-stu-id="aa725-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="aa725-130">Al descargar un paquete de descarga, recibirá una notificación de la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="aa725-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="aa725-131">Las directivas de incorporación y retirada no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario se producirán colisiones impredecibles.</span><span class="sxs-lookup"><span data-stu-id="aa725-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="aa725-132">Obtener el paquete de descarga del [centro de cumplimiento de Microsoft](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="aa725-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="aa725-133">En el panel de navegación, seleccione **configuración**  >  **dispositivo de descarga** .</span><span class="sxs-lookup"><span data-stu-id="aa725-133">In the navigation pane, select **Settings** > **Device offboarding** .</span></span>

3. <span data-ttu-id="aa725-134">En el campo **método de implementación** , seleccione **script local** .</span><span class="sxs-lookup"><span data-stu-id="aa725-134">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="aa725-135">Haga clic en **Descargar paquete** y guarde el archivo. zip.</span><span class="sxs-lookup"><span data-stu-id="aa725-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="aa725-136">Extraiga el contenido del archivo. zip en una ubicación compartida de solo lectura a la que puedan tener acceso los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="aa725-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="aa725-137">Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .</span><span class="sxs-lookup"><span data-stu-id="aa725-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

6.  <span data-ttu-id="aa725-138">Abra un mensaje de la línea de comandos con privilegios elevados en el dispositivo y ejecute el script:</span><span class="sxs-lookup"><span data-stu-id="aa725-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="aa725-139">Vaya a **Inicio** y escriba **cmd** .</span><span class="sxs-lookup"><span data-stu-id="aa725-139">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="aa725-140">Haga clic con el botón secundario en **símbolo del sistema** y seleccione **Ejecutar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="aa725-140">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![Menú de inicio de ventana que apunta a ejecutar como administrador](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="aa725-142">Escriba la ubicación del archivo de script.</span><span class="sxs-lookup"><span data-stu-id="aa725-142">Type the location of the script file.</span></span> <span data-ttu-id="aa725-143">Si copió el archivo en el escritorio, escriba: *%userprofile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-mm-dd. cmd*</span><span class="sxs-lookup"><span data-stu-id="aa725-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="aa725-144">Presione la tecla **entrar** o haga clic en **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="aa725-144">Press the **Enter** key or click **OK** .</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa725-145">La descarga hace que el dispositivo deje de enviar datos del sensor al portal.</span><span class="sxs-lookup"><span data-stu-id="aa725-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="aa725-146">Supervisar la configuración del dispositivo</span><span class="sxs-lookup"><span data-stu-id="aa725-146">Monitor device configuration</span></span>
<span data-ttu-id="aa725-147">Puede seguir los diferentes pasos de comprobación de [solucionar problemas de incorporación] ( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) para comprobar que el script se completó correctamente y que el agente se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="aa725-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="aa725-148">La supervisión también puede realizarse directamente en el portal o mediante las distintas herramientas de implementación.</span><span class="sxs-lookup"><span data-stu-id="aa725-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="aa725-149">Supervisar dispositivos con el portal</span><span class="sxs-lookup"><span data-stu-id="aa725-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="aa725-150">Vaya al [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="aa725-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="aa725-151">Elija los dispositivos de incorporación de dispositivos de **configuración**  >  **Device onboarding**  >  **Devices** .</span><span class="sxs-lookup"><span data-stu-id="aa725-151">Choose **Settings** > **Device onboarding** > **Devices** .</span></span>

3. <span data-ttu-id="aa725-152">Compruebe que aparecen dispositivos.</span><span class="sxs-lookup"><span data-stu-id="aa725-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="aa725-153">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="aa725-153">Related topics</span></span>
- [<span data-ttu-id="aa725-154">Dispositivos de Windows 10 incorporados mediante la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="aa725-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="aa725-155">Dispositivos con Windows 10 en placa mediante el administrador de configuración de Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="aa725-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="aa725-156">Dispositivos de Windows 10 en placa con herramientas de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="aa725-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="aa725-157">Dispositivos de infraestructura de escritorio virtual (VDI) no persistentes incorporados</span><span class="sxs-lookup"><span data-stu-id="aa725-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="aa725-158">Ejecutar una prueba de detección en un dispositivo ATP de Microsoft defender recién integrado</span><span class="sxs-lookup"><span data-stu-id="aa725-158">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="aa725-159">Solucionar problemas de incorporación de la protección contra amenazas avanzada de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="aa725-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)