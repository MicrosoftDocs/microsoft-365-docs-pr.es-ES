---
title: Control de dispositivo extraíble de Microsoft Defender para endpoint Storage control de acceso
description: Una información general sobre Microsoft Defender para endpoint
keywords: medios de almacenamiento extraíbles
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 46ea74d11f9c54cd1d967058433a74ef4c1ead19
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300239"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="8f0d0-104">Control de dispositivo extraíble de Microsoft Defender para endpoint Storage control de acceso</span><span class="sxs-lookup"><span data-stu-id="8f0d0-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="8f0d0-105">Microsoft Defender para endpoint device control removable Storage Access Control permite realizar la siguiente tarea:</span><span class="sxs-lookup"><span data-stu-id="8f0d0-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="8f0d0-106">auditar, permitir o impedir el acceso de lectura, escritura o ejecución al almacenamiento extraíble con o sin exclusión</span><span class="sxs-lookup"><span data-stu-id="8f0d0-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="8f0d0-107">Privilegio</span><span class="sxs-lookup"><span data-stu-id="8f0d0-107">Privilege</span></span> |<span data-ttu-id="8f0d0-108">Permiso</span><span class="sxs-lookup"><span data-stu-id="8f0d0-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="8f0d0-109">Access</span><span class="sxs-lookup"><span data-stu-id="8f0d0-109">Access</span></span>    |  <span data-ttu-id="8f0d0-110">Lectura, Escritura, Ejecución</span><span class="sxs-lookup"><span data-stu-id="8f0d0-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="8f0d0-111">Modo de acción</span><span class="sxs-lookup"><span data-stu-id="8f0d0-111">Action Mode</span></span>    |    <span data-ttu-id="8f0d0-112">Auditoría, Permitir, Impedir</span><span class="sxs-lookup"><span data-stu-id="8f0d0-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="8f0d0-113">Compatibilidad con CSP</span><span class="sxs-lookup"><span data-stu-id="8f0d0-113">CSP Support</span></span>   |   <span data-ttu-id="8f0d0-114">Sí</span><span class="sxs-lookup"><span data-stu-id="8f0d0-114">Yes</span></span>      |
|<span data-ttu-id="8f0d0-115">Compatibilidad con GPO</span><span class="sxs-lookup"><span data-stu-id="8f0d0-115">GPO Support</span></span>    |   <span data-ttu-id="8f0d0-116">Sí</span><span class="sxs-lookup"><span data-stu-id="8f0d0-116">Yes</span></span>      |
|<span data-ttu-id="8f0d0-117">Soporte técnico basado en usuarios</span><span class="sxs-lookup"><span data-stu-id="8f0d0-117">User-based Support</span></span>     |   <span data-ttu-id="8f0d0-118">Sí</span><span class="sxs-lookup"><span data-stu-id="8f0d0-118">Yes</span></span>      |
|<span data-ttu-id="8f0d0-119">Compatibilidad basada en máquina</span><span class="sxs-lookup"><span data-stu-id="8f0d0-119">Machine-based Support</span></span>    |    <span data-ttu-id="8f0d0-120">Sí</span><span class="sxs-lookup"><span data-stu-id="8f0d0-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="8f0d0-121">Preparar los puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="8f0d0-121">Prepare your endpoints</span></span>

<span data-ttu-id="8f0d0-122">Implemente el control Storage de acceso extraíble en dispositivos Windows 10 que tengan la versión de cliente antimalware **4.18.2103.3 o posterior.**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-122">Deploy Removable Storage Access Control on Windows 10 devices that have Anti-malware Client Version **4.18.2103.3 or later**.</span></span>
1. <span data-ttu-id="8f0d0-123">**4.18.2104 o** posterior: Agregar SerialNumberId, VID_PID, compatibilidad con GPO basada en filepath</span><span class="sxs-lookup"><span data-stu-id="8f0d0-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support</span></span>

2. <span data-ttu-id="8f0d0-124">**4.18.2105** o posterior: Agregar compatibilidad con caracteres comodín para HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, la combinación de usuario específico en una máquina específica, SSD extraíble (un SSD extremo de SanDisk)/compatibilidad con SCSI conectada a USB (UAS)</span><span class="sxs-lookup"><span data-stu-id="8f0d0-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="La interfaz de PowerShell":::

## <a name="policy-properties"></a><span data-ttu-id="8f0d0-126">Propiedades de la directiva</span><span class="sxs-lookup"><span data-stu-id="8f0d0-126">Policy properties</span></span>

<span data-ttu-id="8f0d0-127">Puede usar las siguientes propiedades para crear un grupo de almacenamiento extraíble:</span><span class="sxs-lookup"><span data-stu-id="8f0d0-127">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="8f0d0-128">**Nombre de la propiedad: Id. de grupo**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-128">**Property name: Group ID**</span></span>

1. <span data-ttu-id="8f0d0-129">Descripción: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un identificador único, representa el grupo y se usará en la directiva.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-129">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="8f0d0-130">**Nombre de la propiedad: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-130">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="8f0d0-131">Descripción: enumera las propiedades del dispositivo que quieres usar para cubrir en el grupo.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-131">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="8f0d0-132">Enumera las propiedades del dispositivo que quieres usar para cubrir en el grupo.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-132">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="8f0d0-133">Para cada propiedad de dispositivo, consulta **la sección Propiedades del** dispositivo anterior para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-133">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="8f0d0-134">Opciones:</span><span class="sxs-lookup"><span data-stu-id="8f0d0-134">Options:</span></span>
    - <span data-ttu-id="8f0d0-135">Id. principal</span><span class="sxs-lookup"><span data-stu-id="8f0d0-135">Primary ID</span></span>
        - <span data-ttu-id="8f0d0-136">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="8f0d0-136">RemovableMediaDevices</span></span>
        - <span data-ttu-id="8f0d0-137">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="8f0d0-137">CdRomDevices</span></span>
    - <span data-ttu-id="8f0d0-138">DeviceId</span><span class="sxs-lookup"><span data-stu-id="8f0d0-138">DeviceId</span></span>
    - <span data-ttu-id="8f0d0-139">HardwareId</span><span class="sxs-lookup"><span data-stu-id="8f0d0-139">HardwareId</span></span>
    - <span data-ttu-id="8f0d0-140">InstancePathId</span><span class="sxs-lookup"><span data-stu-id="8f0d0-140">InstancePathId</span></span>
    - <span data-ttu-id="8f0d0-141">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="8f0d0-141">FriendlyNameId</span></span>
    - <span data-ttu-id="8f0d0-142">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="8f0d0-142">SerialNumberId</span></span>
    - <span data-ttu-id="8f0d0-143">VID</span><span class="sxs-lookup"><span data-stu-id="8f0d0-143">VID</span></span>
    - <span data-ttu-id="8f0d0-144">PID</span><span class="sxs-lookup"><span data-stu-id="8f0d0-144">PID</span></span>
    - <span data-ttu-id="8f0d0-145">VID_PID</span><span class="sxs-lookup"><span data-stu-id="8f0d0-145">VID_PID</span></span>
        - <span data-ttu-id="8f0d0-146">0751_55E0: coincide con este par VID/PID exacto</span><span class="sxs-lookup"><span data-stu-id="8f0d0-146">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="8f0d0-147">_55E0: hacer coincidir cualquier medio con PID=55E0</span><span class="sxs-lookup"><span data-stu-id="8f0d0-147">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="8f0d0-148">0751_: hacer coincidir cualquier medio con VID=0751</span><span class="sxs-lookup"><span data-stu-id="8f0d0-148">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="8f0d0-149">**Nombre de la propiedad: MatchType**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-149">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="8f0d0-150">Descripción: cuando se usan varias propiedades de dispositivo en descriptorIDList, MatchType define la relación.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-150">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="8f0d0-151">Opciones:</span><span class="sxs-lookup"><span data-stu-id="8f0d0-151">Options:</span></span>
    - <span data-ttu-id="8f0d0-152">MatchAll: cualquier atributo bajo descriptorIdList será **relación And;** por ejemplo, si el administrador pone DeviceID e InstancePathID, por cada USB conectado, el sistema comprobará si el USB cumple ambos valores.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-152">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>

    - <span data-ttu-id="8f0d0-153">MatchAny: los atributos de descriptorIdList serán **o** relación; por ejemplo, si el administrador pone DeviceID e InstancePathID, por cada USB conectado, el sistema hará la aplicación siempre que el USB tenga un valor **DeviceID** o **InstanceID** idéntico.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-153">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="8f0d0-154">Las siguientes son las propiedades de la directiva de control de acceso:</span><span class="sxs-lookup"><span data-stu-id="8f0d0-154">Following are the access control policy properties:</span></span>

<span data-ttu-id="8f0d0-155">**Nombre de la propiedad: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-155">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="8f0d0-156">Descripción: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un identificador único, representa la directiva y se usará en los informes y la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-156">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="8f0d0-157">**Nombre de la propiedad: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-157">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="8f0d0-158">Descripción: los grupos a los que se aplicará la directiva.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-158">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="8f0d0-159">Si se agregan varios grupos, la directiva se aplicará a cualquier medio de todos esos grupos.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-159">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

1. <span data-ttu-id="8f0d0-160">Opciones: El IDENTIFICADOR de grupo/GUID debe usarse en esta instancia.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-160">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="8f0d0-161">En el ejemplo siguiente se muestra el uso de GroupID:</span><span class="sxs-lookup"><span data-stu-id="8f0d0-161">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="8f0d0-162">**Nombre de la propiedad: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-162">**Property name: ExcludedIDList**</span></span>

1. <span data-ttu-id="8f0d0-163">Descripción: los grupos a los que no se aplicará la directiva.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-163">Description: The group(s) that the policy will not be applied to.</span></span>
1. <span data-ttu-id="8f0d0-164">Opciones: El IDENTIFICADOR de grupo/GUID debe usarse en esta instancia.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-164">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="8f0d0-165">**Nombre de la propiedad: Id. de entrada**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-165">**Property name: Entry ID**</span></span>

1. <span data-ttu-id="8f0d0-166">Descripción: One PolicyRule puede tener varias entradas; cada entrada con un GUID único indica al Control de dispositivos una restricción.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-166">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="8f0d0-167">**Nombre de la propiedad: Type**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-167">**Property name: Type**</span></span>

1. <span data-ttu-id="8f0d0-168">Descripción: define la acción de los grupos de almacenamiento extraíbles en IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-168">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="8f0d0-169">Aplicación: Permitir o denegar</span><span class="sxs-lookup"><span data-stu-id="8f0d0-169">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="8f0d0-170">Auditoría: AuditAllowed o AuditDenied</span><span class="sxs-lookup"><span data-stu-id="8f0d0-170">Audit: AuditAllowed or AuditDenied</span></span> 
1. <span data-ttu-id="8f0d0-171">Opciones:</span><span class="sxs-lookup"><span data-stu-id="8f0d0-171">Options:</span></span>
    - <span data-ttu-id="8f0d0-172">Permitir</span><span class="sxs-lookup"><span data-stu-id="8f0d0-172">Allow</span></span>
    - <span data-ttu-id="8f0d0-173">Denegar</span><span class="sxs-lookup"><span data-stu-id="8f0d0-173">Deny</span></span>
    - <span data-ttu-id="8f0d0-174">AuditAllowed: define la notificación y el evento cuando se permite el acceso</span><span class="sxs-lookup"><span data-stu-id="8f0d0-174">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="8f0d0-175">AuditDenied: define la notificación y el evento cuando se deniega el acceso; tiene que trabajar junto con **la entrada Denegar.**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-175">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="8f0d0-176">Cuando haya tipos de conflicto para el mismo medio, el sistema aplicará el primero de la directiva.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-176">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="8f0d0-177">Un ejemplo de tipo de conflicto **es Allow** y **Deny**.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-177">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="8f0d0-178">**Nombre de la propiedad: Opciones**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-178">**Property name: Options**</span></span>

1. <span data-ttu-id="8f0d0-179">Descripción: define si se va a mostrar la notificación o no.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-179">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="La pantalla en la que se puede ver el estado del dispositivo":::

1. <span data-ttu-id="8f0d0-181">Opciones: 0-4.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-181">Options: 0-4.</span></span> <span data-ttu-id="8f0d0-182">Cuando el tipo Permitir o Denegar está seleccionado:</span><span class="sxs-lookup"><span data-stu-id="8f0d0-182">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="8f0d0-183">0: nada</span><span class="sxs-lookup"><span data-stu-id="8f0d0-183">0: nothing</span></span>
   - <span data-ttu-id="8f0d0-184">4: deshabilitar **AuditAllowed** y **AuditDenied** para esta entrada.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-184">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="8f0d0-185">Incluso si **se produce** block y la **configuración auditDenied** está configurada, el sistema no mostrará la notificación.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-185">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="8f0d0-186">Cuando se **selecciona Tipo AuditAllowed** **o AuditDenied:**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-186">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="8f0d0-187">0: nada</span><span class="sxs-lookup"><span data-stu-id="8f0d0-187">0: nothing</span></span>
   - <span data-ttu-id="8f0d0-188">1: mostrar notificación</span><span class="sxs-lookup"><span data-stu-id="8f0d0-188">1: show notification</span></span>
   - <span data-ttu-id="8f0d0-189">2: evento send</span><span class="sxs-lookup"><span data-stu-id="8f0d0-189">2: send event</span></span>
   - <span data-ttu-id="8f0d0-190">3: mostrar notificación y enviar evento</span><span class="sxs-lookup"><span data-stu-id="8f0d0-190">3: show notification and send event</span></span>

<span data-ttu-id="8f0d0-191">**Nombre de la propiedad: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-191">**Property name: AccessMask**</span></span>

1. <span data-ttu-id="8f0d0-192">Descripción: define el acceso.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-192">Description: Defines the access.</span></span>

1. <span data-ttu-id="8f0d0-193">Opciones: 1-7:</span><span class="sxs-lookup"><span data-stu-id="8f0d0-193">Options: 1-7:</span></span>
    - <span data-ttu-id="8f0d0-194">1: Leer</span><span class="sxs-lookup"><span data-stu-id="8f0d0-194">1: Read</span></span>
    - <span data-ttu-id="8f0d0-195">2: Escribir</span><span class="sxs-lookup"><span data-stu-id="8f0d0-195">2: Write</span></span>
    - <span data-ttu-id="8f0d0-196">3: Lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="8f0d0-196">3: Read and Write</span></span>
    - <span data-ttu-id="8f0d0-197">4: Ejecutar</span><span class="sxs-lookup"><span data-stu-id="8f0d0-197">4: Execute</span></span>
    - <span data-ttu-id="8f0d0-198">5: Leer y ejecutar</span><span class="sxs-lookup"><span data-stu-id="8f0d0-198">5: Read and Execute</span></span>
    - <span data-ttu-id="8f0d0-199">6: Escribir y ejecutar</span><span class="sxs-lookup"><span data-stu-id="8f0d0-199">6: Write and Execute</span></span>
    - <span data-ttu-id="8f0d0-200">7: Lectura y escritura y ejecución</span><span class="sxs-lookup"><span data-stu-id="8f0d0-200">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="8f0d0-201">Escenarios comunes Storage control de acceso extraíble</span><span class="sxs-lookup"><span data-stu-id="8f0d0-201">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="8f0d0-202">Para ayudarle a familiarizarse con Microsoft Defender para Endpoint Removable Storage Access Control, hemos reunido algunos escenarios comunes que puede seguir.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-202">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="8f0d0-203">Escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir usbs aprobados específicos</span><span class="sxs-lookup"><span data-stu-id="8f0d0-203">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="8f0d0-204">Crear grupos</span><span class="sxs-lookup"><span data-stu-id="8f0d0-204">Create groups</span></span>
    1. <span data-ttu-id="8f0d0-205">Grupo 1: Cualquier almacenamiento extraíble y CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-205">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="8f0d0-206">Un ejemplo de almacenamiento extraíble y CD/DVD es: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** en el ejemplo [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-206">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="8f0d0-207">Grupo 2: USB aprobados en función de las propiedades del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-207">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="8f0d0-208">Un ejemplo para este caso de uso es: Id. de instancia: grupo **65fa649a-a111-4912-9294-fb6337a25038** en el archivo [usbs aprobados Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-208">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8f0d0-209">Debe reemplazar por `&` en `&amp;` el valor.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-209">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="8f0d0-210">Crear directiva</span><span class="sxs-lookup"><span data-stu-id="8f0d0-210">Create policy</span></span>
    1. <span data-ttu-id="8f0d0-211">Directiva 1: Bloquear el acceso de escritura y ejecución, pero permitir los USB aprobados.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-211">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="8f0d0-212">Un ejemplo para este caso de uso es: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** en el ejemplo Escenario 1 Block Write and Execute Access, pero permite a los [USB aprobados .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) archivo.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-212">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="8f0d0-213">Directiva 2: Auditar el acceso de escritura y ejecución a los USB permitidos.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-213">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="8f0d0-214">Un ejemplo para este caso de uso es: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** en el ejemplo [Escenario 1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Audit Write and Execute access to approved USBs.xmlfile.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-214">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="8f0d0-215">Escenario 2: Auditar el acceso de escritura y ejecución a todos los USB no aprobados específicos, pero bloqueados</span><span class="sxs-lookup"><span data-stu-id="8f0d0-215">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="8f0d0-216">Crear grupos</span><span class="sxs-lookup"><span data-stu-id="8f0d0-216">Create groups</span></span>
    1. <span data-ttu-id="8f0d0-217">Grupo 1: Cualquier almacenamiento extraíble y CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-217">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="8f0d0-218">Un ejemplo para este caso de uso es: Grupo **9b28fae8-72f7-4267-a1a5-685f747a7146** en el ejemplo Cualquier archivo de Storage extraíble y [CD-DVD Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="8f0d0-218">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="8f0d0-219">Grupo 2: USB no aprobados en función de las propiedades del dispositivo, por ejemplo, Id. de proveedor/Id. de producto, Nombre descriptivo : Grupo **65fa649a-a111-4912-9294-fb6337a25038** en el archivo [usbs](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) no aprobados Group.xmlejemplo.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-219">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="8f0d0-220">Debe reemplazar por `&` en `&amp;` el valor.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-220">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="8f0d0-221">Crear directiva</span><span class="sxs-lookup"><span data-stu-id="8f0d0-221">Create policy</span></span>
    1. <span data-ttu-id="8f0d0-222">Directiva 1: Bloquear el acceso de escritura y ejecución a todos los USB no aprobados específicos, pero bloqueados.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-222">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="8f0d0-223">Un ejemplo de este caso de uso es: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** en el ejemplo [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-223">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="8f0d0-224">Directiva 2: Auditar el acceso de escritura y ejecución a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-224">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="8f0d0-225">Un ejemplo de este caso de uso es: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** en el ejemplo [Escenario 2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Audit write and Execute access to others.xmlfile.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-225">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="8f0d0-226">Implementación y administración de directivas mediante directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="8f0d0-226">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="8f0d0-227">La característica Storage control de acceso extraíble te permite aplicar directivas a través de la directiva de grupo a usuarios o dispositivos, o a ambos.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-227">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="8f0d0-228">Licencias</span><span class="sxs-lookup"><span data-stu-id="8f0d0-228">Licensing</span></span>

<span data-ttu-id="8f0d0-229">Antes de empezar con Removable Storage Access Control, debe confirmar su [Microsoft 365 suscripción](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span><span class="sxs-lookup"><span data-stu-id="8f0d0-229">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="8f0d0-230">Para obtener acceso y usar el control Storage de acceso extraíble, debe tener Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-230">To access and use Removable Storage Access Control, you must have Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="8f0d0-231">Implementación de directivas mediante directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="8f0d0-231">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="8f0d0-232">Combine todos los grupos `<Groups>` `</Groups>` en un archivo xml.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-232">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="8f0d0-233">En la siguiente imagen se muestra el ejemplo del escenario 1: Impedir el acceso de escritura y ejecución a todos los usuarios, pero permitir [usbs aprobados específicos.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)</span><span class="sxs-lookup"><span data-stu-id="8f0d0-233">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Pantalla que muestra las opciones de configuración que permiten usbs aprobados específicos en dispositivos":::
    
2. <span data-ttu-id="8f0d0-235">Combine todas las reglas `<PolicyRules>` `</PolicyRules>` dentro de un archivo xml.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-235">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="8f0d0-236">Si desea restringir un usuario específico, use la propiedad SID en entry.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-236">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="8f0d0-237">Si no hay ningún SID en la directiva Entry, la entrada se aplicará a todas las instancias de inicio de sesión del equipo.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-237">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="8f0d0-238">La siguiente imagen ilustra el uso de la propiedad SID y un ejemplo de Escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir [usbs aprobados específicos](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span><span class="sxs-lookup"><span data-stu-id="8f0d0-238">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Pantalla que muestra un código que indica el uso del atributo de propiedad SID":::

3. <span data-ttu-id="8f0d0-240">Guarde los archivos XML de regla y grupo en la carpeta de recurso compartido de red y coloque la ruta de acceso de carpeta de recurso compartido de red en la configuración de directiva de grupo: Configuración del equipo -> Plantillas administrativas -> Windows Componentes **-> Antivirus de Microsoft Defender -> Control de dispositivos: 'Definir** grupos de directivas de control de dispositivos' y 'Definir reglas de directiva de control de dispositivos'.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-240">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="8f0d0-241">El equipo de destino debe poder tener acceso al recurso compartido de red para tener la directiva.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-241">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="8f0d0-242">Sin embargo, una vez que se lee la directiva, la conexión de recurso compartido de red ya no es necesaria, incluso después del reinicio de la máquina.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-242">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="Pantalla Control de dispositivos":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="8f0d0-244">Implementación y administración de directivas a través de Intune OMA-URI</span><span class="sxs-lookup"><span data-stu-id="8f0d0-244">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="8f0d0-245">La característica Storage control de acceso extraíble permite aplicar directivas a través de OMA-URI a usuarios o dispositivos, o a ambos.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-245">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="8f0d0-246">Licencias</span><span class="sxs-lookup"><span data-stu-id="8f0d0-246">Licensing</span></span>

<span data-ttu-id="8f0d0-247">Antes de empezar con Removable Storage Access Control, debe confirmar su [Microsoft 365 suscripción](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span><span class="sxs-lookup"><span data-stu-id="8f0d0-247">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="8f0d0-248">Para obtener acceso y usar el control Storage de acceso extraíble, debe tener Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-248">To access and use Removable Storage Access Control, you must have Microsoft 365 E3.</span></span>

### <a name="permission"></a><span data-ttu-id="8f0d0-249">Permiso</span><span class="sxs-lookup"><span data-stu-id="8f0d0-249">Permission</span></span>

<span data-ttu-id="8f0d0-250">Para la implementación de directivas en Intune, la cuenta debe tener permisos para crear, editar, actualizar o eliminar perfiles de configuración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-250">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="8f0d0-251">Puede crear roles personalizados o usar cualquiera de los roles integrados con estos permisos.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-251">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="8f0d0-252">Rol Administrador de directivas y perfiles</span><span class="sxs-lookup"><span data-stu-id="8f0d0-252">Policy and profile Manager role</span></span>
- <span data-ttu-id="8f0d0-253">Rol personalizado con permisos Create/Edit/Update/Read/Delete/View Reports activados para perfiles de configuración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="8f0d0-253">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="8f0d0-254">Administrador global</span><span class="sxs-lookup"><span data-stu-id="8f0d0-254">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="8f0d0-255">Implementación de directivas mediante OMA-URI</span><span class="sxs-lookup"><span data-stu-id="8f0d0-255">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="8f0d0-256">**Microsoft Endpoint Manager de administración ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-256">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="8f0d0-257">Para cada grupo, cree una regla OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="8f0d0-257">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="8f0d0-258">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="8f0d0-258">OMA-URI:</span></span>

      <span data-ttu-id="8f0d0-259">/Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="8f0d0-259">/Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="8f0d0-260">Por ejemplo, para cualquier almacenamiento extraíble y un grupo **de CD/DVD** en el ejemplo, el vínculo debe ser:</span><span class="sxs-lookup"><span data-stu-id="8f0d0-260">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="8f0d0-261">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="8f0d0-261">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="8f0d0-262">Tipo de datos: String (archivo XML)</span><span class="sxs-lookup"><span data-stu-id="8f0d0-262">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="El archivo xml para el tipo de datos STRING":::

2. <span data-ttu-id="8f0d0-264">Para cada directiva, también cree un OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="8f0d0-264">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="8f0d0-265">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="8f0d0-265">OMA-URI:</span></span>

      <span data-ttu-id="8f0d0-266">/Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="8f0d0-266">/Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="8f0d0-267">Por ejemplo, para la regla Bloquear escritura y ejecutar acceso, pero permitir **usbs aprobados** en el ejemplo, el vínculo debe ser:</span><span class="sxs-lookup"><span data-stu-id="8f0d0-267">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="8f0d0-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="8f0d0-269">Tipo de datos: String (archivo XML)</span><span class="sxs-lookup"><span data-stu-id="8f0d0-269">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" alt-text="Visualización del archivo XML para el tipo de datos STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="8f0d0-271">Implementación y administración de directivas mediante la interfaz de usuario de Intune</span><span class="sxs-lookup"><span data-stu-id="8f0d0-271">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="8f0d0-272">Esta funcionalidad aún no está disponible.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-272">This capability is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8f0d0-273">Ver datos extraíbles Storage control de acceso en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="8f0d0-273">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="8f0d0-274">El Microsoft 365 de seguridad muestra el almacenamiento extraíble bloqueado por el control de dispositivo extraíble Storage control de acceso.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-274">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="8f0d0-275">Para obtener acceso a Microsoft 365 seguridad, debe tener la siguiente suscripción:</span><span class="sxs-lookup"><span data-stu-id="8f0d0-275">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="8f0d0-276">Microsoft 365 para informes E5</span><span class="sxs-lookup"><span data-stu-id="8f0d0-276">Microsoft 365 for E5 reporting</span></span>

```
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="La pantalla que muestra el bloqueo del almacenamiento extraíble":::