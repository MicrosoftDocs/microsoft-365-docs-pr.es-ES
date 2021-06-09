---
title: Administrar el proceso de implementación gradual para actualizaciones de Microsoft Defender
description: Obtenga información sobre el proceso de actualización gradual y los controles
keywords: actualización, proceso de actualización, controles, versión
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 435a77432caa9d7335a22993f85cae69eff6cd38
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841767"
---
#  <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a><span data-ttu-id="2e615-104">Administrar el proceso de implementación gradual para actualizaciones de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2e615-104">Manage the gradual rollout process for Microsoft Defender updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2e615-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2e615-105">**Applies to:**</span></span>

- [<span data-ttu-id="2e615-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2e615-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


<span data-ttu-id="2e615-107">Es importante asegurarse de que los componentes del cliente estén actualizados para ofrecer capacidades de protección críticas y evitar ataques.</span><span class="sxs-lookup"><span data-stu-id="2e615-107">It is important to ensure that client components are up-to-date to deliver critical protection capabilities and prevent attacks.</span></span>

<span data-ttu-id="2e615-108">Las funcionalidades se proporcionan a través de varios componentes:</span><span class="sxs-lookup"><span data-stu-id="2e615-108">Capabilities are provided through several components:</span></span> 

- [<span data-ttu-id="2e615-109">Respuesta de detección & extremo</span><span class="sxs-lookup"><span data-stu-id="2e615-109">Endpoint Detection & Response</span></span>](overview-endpoint-detection-response.md) 
- <span data-ttu-id="2e615-110">[Protección de última generación](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection) con [protección entregada en la nube](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="2e615-110">[Next-generation protection](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection) with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md)</span></span> 
- [<span data-ttu-id="2e615-111">Reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="2e615-111">Attack Surface Reduction</span></span>](overview-attack-surface-reduction.md)

<span data-ttu-id="2e615-112">Las actualizaciones se lanzan mensualmente mediante un proceso de lanzamiento gradual.</span><span class="sxs-lookup"><span data-stu-id="2e615-112">Updates are released monthly using a gradual release process.</span></span> <span data-ttu-id="2e615-113">Este proceso ayuda a habilitar la detección temprana de errores para detectar el impacto a medida que se produce y solucionarlo rápidamente antes de una implementación más grande.</span><span class="sxs-lookup"><span data-stu-id="2e615-113">This process helps to enable early failure detection to catch impact as it occurs and address it quickly before a larger rollout.</span></span> 

> [!NOTE]
> <span data-ttu-id="2e615-114">Para obtener más información sobre cómo controlar las actualizaciones de definiciones diarias, vea Programar Antivirus de Microsoft Defender de definición: Windows [seguridad | Microsoft Docs](manage-protection-update-schedule-microsoft-defender-antivirus.md). Las actualizaciones de definiciones garantizan que la protección de última generación pueda defenderse de las nuevas amenazas, incluso si la protección entregada en la nube no está disponible para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="2e615-114">For more information on how to control daily definition updates, see [Schedule Microsoft Defender Antivirus definition updates - Windows security | Microsoft Docs](manage-protection-update-schedule-microsoft-defender-antivirus.md). Definition updates ensure that next-generation protection can defend against new threats, even if cloud-delivered protection is not available to the endpoint.</span></span>

## <a name="microsoft-gradual-rollout-model"></a><span data-ttu-id="2e615-115">Modelo de lanzamiento gradual de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2e615-115">Microsoft gradual rollout model</span></span>

<span data-ttu-id="2e615-116">Se sigue el siguiente modelo de implementación gradual:</span><span class="sxs-lookup"><span data-stu-id="2e615-116">The following gradual rollout model is followed:</span></span>

1. <span data-ttu-id="2e615-117">La primera versión se publica a los suscriptores del canal beta.</span><span class="sxs-lookup"><span data-stu-id="2e615-117">The first release goes out to Beta channel subscribers.</span></span>
2. <span data-ttu-id="2e615-118">Después de la validación, los comentarios y las correcciones, iniciamos el proceso de implementación gradual de una manera limitada y a Los suscriptores del canal de vista previa primero.</span><span class="sxs-lookup"><span data-stu-id="2e615-118">After validation, feedback, and fixes, we start the gradual rollout process in a throttled way and to Preview channel subscribers first.</span></span>
3. <span data-ttu-id="2e615-119">A continuación, procedemos a liberar la actualización al resto de la población global, escalando de 10 a 100 %.</span><span class="sxs-lookup"><span data-stu-id="2e615-119">We then proceed to release the update to the rest of the global population, scaling out from 10-100%.</span></span>

<span data-ttu-id="2e615-120">Nuestros ingenieros supervisan continuamente el impacto y escalan los problemas para crear una solución según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2e615-120">Our engineers continuously monitor impact and escalate any issues to create a fix as needed.</span></span>

## <a name="how-to-customize-your-internal-deployment-process"></a><span data-ttu-id="2e615-121">Cómo personalizar el proceso de implementación interna</span><span class="sxs-lookup"><span data-stu-id="2e615-121">How to customize your internal deployment process</span></span>

<span data-ttu-id="2e615-122">Si las máquinas reciben actualizaciones de Defender de Windows Update, el proceso de implementación gradual puede provocar que algunas de las máquinas reciban actualizaciones de Defender antes que otras.</span><span class="sxs-lookup"><span data-stu-id="2e615-122">If your machines are receiving Defender updates from Windows Update, the gradual rollout process may result in some of your machines receiving Defender updates sooner than others.</span></span> <span data-ttu-id="2e615-123">En la siguiente sección se explica cómo definir una estrategia que permita que las actualizaciones automáticas fluyan de forma diferente a grupos específicos de dispositivos aprovechando la configuración del canal de actualización.</span><span class="sxs-lookup"><span data-stu-id="2e615-123">The following section explains how to define a strategy that will allow automatic updates to flow differently to specific groups of devices by leveraging update channel configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="2e615-124">Al planear tu propia versión gradual, asegúrate de tener siempre una selección de dispositivos suscritos a los canales de vista previa y por fases.</span><span class="sxs-lookup"><span data-stu-id="2e615-124">When planning for your own gradual release, please make sure to always have a selection of devices subscribed to the preview and staged channels.</span></span> <span data-ttu-id="2e615-125">Esto proporcionará a su organización y a Microsoft la oportunidad de evitar o encontrar y solucionar problemas específicos de su entorno.</span><span class="sxs-lookup"><span data-stu-id="2e615-125">This will provide your organization as well as Microsoft the opportunity to prevent or find and fix issues specific to your environment.</span></span>

<span data-ttu-id="2e615-126">Para las máquinas que reciben actualizaciones a través de, por ejemplo, Windows Server Update Services (WSUS) o Microsoft Endpoint Configuration Manager (MECM), hay más opciones disponibles para todas las actualizaciones de Windows, incluidas las opciones de Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2e615-126">For machines receiving updates through, for example, Windows Server Update Services (WSUS) or Microsoft Endpoint Configuration Manager (MECM), more options are available to all Windows updates, including options  for Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="2e615-127">Obtenga más información sobre cómo usar una solución como WSUS, MECM para administrar la distribución y aplicación de actualizaciones en [Manage Antivirus de Microsoft Defender updates and apply baselines - Windows security | Microsoft Docs](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates).</span><span class="sxs-lookup"><span data-stu-id="2e615-127">Read more about how to use a solution like WSUS, MECM to manage the distribution and application of updates at [Manage Microsoft Defender Antivirus updates and apply baselines - Windows security | Microsoft Docs](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates).</span></span>

## <a name="update-channels-for-monthly-updates"></a><span data-ttu-id="2e615-128">Actualizar canales para actualizaciones mensuales</span><span class="sxs-lookup"><span data-stu-id="2e615-128">Update channels for monthly updates</span></span>

<span data-ttu-id="2e615-129">Puede asignar una máquina a un canal de actualización para definir la cadencia en la que una máquina recibe actualizaciones mensuales del motor y la plataforma.</span><span class="sxs-lookup"><span data-stu-id="2e615-129">You can assign a machine to an update channel to define the cadence in which a machine receives monthly engine and platform updates.</span></span>

<span data-ttu-id="2e615-130">Para obtener más información sobre cómo configurar actualizaciones, vea [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).</span><span class="sxs-lookup"><span data-stu-id="2e615-130">For more information on how to configure updates, see [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).</span></span>

<span data-ttu-id="2e615-131">Los siguientes canales de actualización están disponibles:</span><span class="sxs-lookup"><span data-stu-id="2e615-131">The following update channels are available:</span></span>

| <span data-ttu-id="2e615-132">Nombre del canal</span><span class="sxs-lookup"><span data-stu-id="2e615-132">Channel name</span></span>  | <span data-ttu-id="2e615-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e615-133">Description</span></span>  | <span data-ttu-id="2e615-134">Aplicación</span><span class="sxs-lookup"><span data-stu-id="2e615-134">Application</span></span>  |
|-|-|-|
| <span data-ttu-id="2e615-135">Canal beta: versión preliminar</span><span class="sxs-lookup"><span data-stu-id="2e615-135">Beta Channel - Prerelease</span></span>  | <span data-ttu-id="2e615-136">Probar actualizaciones antes que otras</span><span class="sxs-lookup"><span data-stu-id="2e615-136">Test updates before others</span></span>  | <span data-ttu-id="2e615-137">Los dispositivos establecidos en este canal serán los primeros en recibir nuevas actualizaciones mensuales.</span><span class="sxs-lookup"><span data-stu-id="2e615-137">Devices set to this channel will be the first to receive new monthly updates.</span></span> <span data-ttu-id="2e615-138">Seleccione Canal beta para participar en la identificación y la presentación de informes de problemas a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2e615-138">Select Beta Channel to participate in identifying and reporting issues to Microsoft.</span></span> <span data-ttu-id="2e615-139">Los dispositivos del Windows Insider Program se suscriben a este canal de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2e615-139">Devices in the Windows Insider Program are subscribed to this channel by default.</span></span> <span data-ttu-id="2e615-140">Solo para su uso en entornos de prueba.</span><span class="sxs-lookup"><span data-stu-id="2e615-140">For use in test environments only.</span></span>  |
| <span data-ttu-id="2e615-141">Canal actual (vista previa)</span><span class="sxs-lookup"><span data-stu-id="2e615-141">Current Channel (Preview)</span></span>  | <span data-ttu-id="2e615-142">Obtener actualizaciones del canal actual **antes** durante la versión gradual</span><span class="sxs-lookup"><span data-stu-id="2e615-142">Get Current Channel updates **earlier** during gradual release</span></span>  | <span data-ttu-id="2e615-143">Los dispositivos establecidos en este canal recibirán actualizaciones lo antes posible durante el ciclo de lanzamiento gradual.</span><span class="sxs-lookup"><span data-stu-id="2e615-143">Devices set to this channel will be offered updates earliest during the gradual release cycle.</span></span> <span data-ttu-id="2e615-144">Sugerido para entornos de preproducción/validación.</span><span class="sxs-lookup"><span data-stu-id="2e615-144">Suggested for pre-production/validation environments.</span></span>  |
| <span data-ttu-id="2e615-145">Canal actual (por fases)</span><span class="sxs-lookup"><span data-stu-id="2e615-145">Current Channel (Staged)</span></span>  | <span data-ttu-id="2e615-146">Obtener actualizaciones del canal actual más adelante durante la versión gradual</span><span class="sxs-lookup"><span data-stu-id="2e615-146">Get Current Channel updates later during gradual release</span></span>  | <span data-ttu-id="2e615-147">Los dispositivos se ofrecerán actualizaciones más adelante durante el ciclo de lanzamiento gradual.</span><span class="sxs-lookup"><span data-stu-id="2e615-147">Devices will be offered updates later during the gradual release cycle.</span></span> <span data-ttu-id="2e615-148">Se sugiere aplicar a una parte pequeña y representativa de la población de dispositivos (~10%).</span><span class="sxs-lookup"><span data-stu-id="2e615-148">Suggested to apply to a small, representative part of your device population (~10%).</span></span>  |
| <span data-ttu-id="2e615-149">Canal actual (ancho)</span><span class="sxs-lookup"><span data-stu-id="2e615-149">Current Channel (Broad)</span></span> | <span data-ttu-id="2e615-150">Obtener actualizaciones al final de la versión gradual</span><span class="sxs-lookup"><span data-stu-id="2e615-150">Get updates at the end of gradual release</span></span>  | <span data-ttu-id="2e615-151">Solo se ofrecerán actualizaciones a los dispositivos una vez completado el ciclo de lanzamiento gradual.</span><span class="sxs-lookup"><span data-stu-id="2e615-151">Devices will be offered updates only after the gradual release cycle completes.</span></span> <span data-ttu-id="2e615-152">Se recomienda aplicar a un amplio conjunto de dispositivos de la población de producción (~10-100%).</span><span class="sxs-lookup"><span data-stu-id="2e615-152">Suggested to apply to a broad set of devices in your production population (~10-100%).</span></span>  |
| <span data-ttu-id="2e615-153">(valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="2e615-153">(default)</span></span>  |   | <span data-ttu-id="2e615-154">Si deshabilitas o no configuras esta directiva, el dispositivo permanecerá en Canal actual (predeterminado): mantenerse actualizado automáticamente durante el ciclo de lanzamiento gradual.</span><span class="sxs-lookup"><span data-stu-id="2e615-154">If you disable or do not configure this policy, the device will remain in Current Channel (Default): Stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="2e615-155">Adecuado para la mayoría de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2e615-155">Suitable for most devices.</span></span>  |

### <a name="update-channels-for-daily-definition-updates"></a><span data-ttu-id="2e615-156">Actualizar canales para actualizaciones de definiciones diarias</span><span class="sxs-lookup"><span data-stu-id="2e615-156">Update channels for daily definition updates</span></span>

<span data-ttu-id="2e615-157">Puede asignar una máquina a un canal de actualización para definir la cadencia en la que una máquina recibe actualizaciones de definiciones diarias.</span><span class="sxs-lookup"><span data-stu-id="2e615-157">You can assign a machine to an update channel to define the cadence in which a machine receives daily definition updates.</span></span>
  
| <span data-ttu-id="2e615-158">Nombre del canal</span><span class="sxs-lookup"><span data-stu-id="2e615-158">Channel name</span></span>  | <span data-ttu-id="2e615-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e615-159">Description</span></span>  | <span data-ttu-id="2e615-160">Aplicación</span><span class="sxs-lookup"><span data-stu-id="2e615-160">Application</span></span>  |
|-|-|-|
| <span data-ttu-id="2e615-161">Canal actual (por fases)</span><span class="sxs-lookup"><span data-stu-id="2e615-161">Current Channel (Staged)</span></span>  | <span data-ttu-id="2e615-162">Obtener actualizaciones del canal actual más adelante durante la versión gradual</span><span class="sxs-lookup"><span data-stu-id="2e615-162">Get Current Channel updates later during gradual release</span></span>  | <span data-ttu-id="2e615-163">Los dispositivos se ofrecerán actualizaciones más adelante durante el ciclo de lanzamiento gradual.</span><span class="sxs-lookup"><span data-stu-id="2e615-163">Devices will be offered updates later during the gradual release cycle.</span></span> <span data-ttu-id="2e615-164">Se sugiere aplicar a una parte pequeña y representativa de la población de dispositivos (~10%).</span><span class="sxs-lookup"><span data-stu-id="2e615-164">Suggested to apply to a small, representative part of your device population (~10%).</span></span>  |
| <span data-ttu-id="2e615-165">Canal actual (ancho)</span><span class="sxs-lookup"><span data-stu-id="2e615-165">Current Channel (Broad)</span></span> | <span data-ttu-id="2e615-166">Obtener actualizaciones al final de la versión gradual</span><span class="sxs-lookup"><span data-stu-id="2e615-166">Get updates at the end of gradual release</span></span>  | <span data-ttu-id="2e615-167">Los dispositivos se ofrecerán actualizaciones después del ciclo de lanzamiento gradual.</span><span class="sxs-lookup"><span data-stu-id="2e615-167">Devices will be offered updates after the gradual release cycle.</span></span> <span data-ttu-id="2e615-168">Ideal para máquinas de centros de datos que solo reciben actualizaciones limitadas.</span><span class="sxs-lookup"><span data-stu-id="2e615-168">Best for datacenter machines that only receive limited updates.</span></span> <span data-ttu-id="2e615-169">Nota: esta configuración se aplica a todas las actualizaciones de Defender.</span><span class="sxs-lookup"><span data-stu-id="2e615-169">Note: this setting applies to all Defender updates.</span></span>  |
| <span data-ttu-id="2e615-170">(valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="2e615-170">(default)</span></span>  |   | <span data-ttu-id="2e615-171">Si deshabilitas o no configuras esta directiva, el dispositivo permanecerá en Canal actual (predeterminado): mantenerse actualizado automáticamente durante el ciclo de lanzamiento gradual.</span><span class="sxs-lookup"><span data-stu-id="2e615-171">If you disable or do not configure this policy, the device will remain in Current Channel (Default): Stay up to date automatically during the gradual release cycle.</span></span> <span data-ttu-id="2e615-172">Adecuado para la mayoría de los dispositivos</span><span class="sxs-lookup"><span data-stu-id="2e615-172">Suitable for most devices</span></span>  |

> [!NOTE]
> <span data-ttu-id="2e615-173">En caso de que desee forzar una actualización a la firma más reciente en lugar de aprovechar el retraso de tiempo, primero tendrá que quitar esta directiva.</span><span class="sxs-lookup"><span data-stu-id="2e615-173">In case you wish to force an update to the newest signature instead of leveraging the time delay, you will need to remove this policy first.</span></span>

## <a name="update-guidance"></a><span data-ttu-id="2e615-174">Instrucciones de actualización</span><span class="sxs-lookup"><span data-stu-id="2e615-174">Update guidance</span></span>

<span data-ttu-id="2e615-175">En la mayoría de los casos, la configuración recomendada al usar Windows Update es permitir que los puntos de conexión reciban y apliquen actualizaciones mensuales de Defender a medida que llegan.</span><span class="sxs-lookup"><span data-stu-id="2e615-175">In most cases, the recommended configuration when using Windows Update is to allow endpoints to receive and apply monthly Defender updates as they arrive.</span></span> <span data-ttu-id="2e615-176">Esto proporciona el mejor equilibrio entre la protección y el posible impacto asociado con los cambios que pueden introducir.</span><span class="sxs-lookup"><span data-stu-id="2e615-176">This provides the best balance between protection and possible impact associated with the changes they can introduce.</span></span>

<span data-ttu-id="2e615-177">Para entornos en los que es necesario un lanzamiento gradual más controlado de actualizaciones automáticas de Defender, considere un enfoque con grupos de implementación:</span><span class="sxs-lookup"><span data-stu-id="2e615-177">For environments where there is a need for a more controlled gradual rollout of automatic Defender updates, consider an approach with deployment groups:</span></span>

1. <span data-ttu-id="2e615-178">Participa en el Windows Insider o asigna un grupo de dispositivos al canal beta.</span><span class="sxs-lookup"><span data-stu-id="2e615-178">Participate in the Windows Insider program or assign a group of devices to the Beta Channel.</span></span>
2. <span data-ttu-id="2e615-179">Designe un grupo piloto que opte por el Canal de vista previa, normalmente entornos de validación, para recibir actualizaciones nuevas antes de tiempo.</span><span class="sxs-lookup"><span data-stu-id="2e615-179">Designate a pilot group that opts-in to Preview Channel, typically validation environments, to receive new updates early.</span></span>
3. <span data-ttu-id="2e615-180">Designe un grupo de máquinas que reciban actualizaciones más adelante durante el lanzamiento gradual desde el canal por fases.</span><span class="sxs-lookup"><span data-stu-id="2e615-180">Designate a group of machines that receive updates later during the gradual rollout from Staged channel.</span></span> <span data-ttu-id="2e615-181">Normalmente, esto sería un representante ~10% de la población.</span><span class="sxs-lookup"><span data-stu-id="2e615-181">Typically, this would be a representative ~10% of the population.</span></span>
4. <span data-ttu-id="2e615-182">Designe un grupo de máquinas que reciban actualizaciones una vez completado el ciclo de lanzamiento gradual.</span><span class="sxs-lookup"><span data-stu-id="2e615-182">Designate a group of machines that receive updates after the gradual release cycle completes.</span></span> <span data-ttu-id="2e615-183">Por lo general, se trata de sistemas de producción importantes.</span><span class="sxs-lookup"><span data-stu-id="2e615-183">These are typically important production systems.</span></span>

<span data-ttu-id="2e615-184">Para el resto de dispositivos, la configuración predeterminada es recibir nuevas actualizaciones a medida que llegan durante el proceso de implementación gradual de Microsoft y no se requiere ninguna configuración adicional.</span><span class="sxs-lookup"><span data-stu-id="2e615-184">For the remainder of devices, the default setting is to receive new updates as they arrive during the Microsoft gradual rollout process and no further configuration is required.</span></span> 

<span data-ttu-id="2e615-185">Adoptar este modelo:</span><span class="sxs-lookup"><span data-stu-id="2e615-185">Adopting this model:</span></span>
- <span data-ttu-id="2e615-186">Permite probar las versiones anticipadas antes de que lleguen a un entorno de producción</span><span class="sxs-lookup"><span data-stu-id="2e615-186">Allows you to test early releases before they reach a production environment</span></span> 
- <span data-ttu-id="2e615-187">Asegúrese de que el entorno de producción sigue recibindo actualizaciones periódicas y de garantizar la protección contra amenazas críticas.</span><span class="sxs-lookup"><span data-stu-id="2e615-187">Ensure the production environment still receives regular updates and ensure protection against critical threats.</span></span>

## <a name="management-tools"></a><span data-ttu-id="2e615-188">Herramientas de administración</span><span class="sxs-lookup"><span data-stu-id="2e615-188">Management tools</span></span>
<span data-ttu-id="2e615-189">Para crear su propio proceso de implementación gradual personalizado para actualizaciones mensuales, puede usar las siguientes herramientas:</span><span class="sxs-lookup"><span data-stu-id="2e615-189">To create your own custom gradual rollout process for monthly updates, you can use the following tools:</span></span>

- <span data-ttu-id="2e615-190">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="2e615-190">Group policy</span></span>
- <span data-ttu-id="2e615-191">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="2e615-191">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="2e615-192">PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e615-192">PowerShell</span></span>

<span data-ttu-id="2e615-193">Para obtener información detallada sobre cómo usar estas herramientas, consulte [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).</span><span class="sxs-lookup"><span data-stu-id="2e615-193">For details on how to use these tools, see [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).</span></span>