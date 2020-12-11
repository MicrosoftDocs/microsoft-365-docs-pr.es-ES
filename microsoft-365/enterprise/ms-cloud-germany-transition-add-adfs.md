---
title: Pasos de migración de AD FS para la migración desde la nube de Microsoft Alemania
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumen: pasos para la migración de los servicios de Federación de Active Directory (AD FS) para la migración desde la nube de Microsoft Alemania.'
ms.openlocfilehash: 175734851c2838eb2e224a9afb57a600d4ed9523
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "49554815"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="3749e-103">Pasos de migración de AD FS para la migración desde la nube de Microsoft Alemania</span><span class="sxs-lookup"><span data-stu-id="3749e-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="3749e-104">Para migrar la granja de servidores de servicios de Federación de Active Directory (AD FS) desde la nube de Microsoft Alemania:</span><span class="sxs-lookup"><span data-stu-id="3749e-104">To migrate your Active Directory Federation Services (AD FS) farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="3749e-105">Realice una copia de seguridad de la configuración de AD FS, incluida la información de confianza FF, con [estos pasos](#backup).</span><span class="sxs-lookup"><span data-stu-id="3749e-105">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="3749e-106">Denomine a la copia de seguridad de la **nube de microsoft Deutschland_Only** para indicar que solo tiene la información de inquilino Alemania de la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3749e-106">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="3749e-107">Probar la restauración mediante la copia de seguridad de Microsoft Cloud Deutschland_Only, la granja de AD FS debe seguir funcionando solo como Alemania de nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3749e-107">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>
3. <span data-ttu-id="3749e-108">Cree una nueva relación de confianza para usuario autenticado de **AD FS > servicios de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="3749e-108">Create a new Relying Party trust from **AD FS >  Office 365 services**.</span></span>
4. <span data-ttu-id="3749e-109">En **relaciones de confianza para usuario autenticado** en la consola de administración de AD FS, seleccione **Agregar relación de confianza para usuario autenticado**.</span><span class="sxs-lookup"><span data-stu-id="3749e-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span></span>
5. <span data-ttu-id="3749e-110">Seleccione **siguiente** en la página de **bienvenida** del Asistente para agregar relaciones de confianza para usuario autenticado.</span><span class="sxs-lookup"><span data-stu-id="3749e-110">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
6. <span data-ttu-id="3749e-111">En la página **Seleccionar origen de datos** , seleccione **importar datos sobre el usuario de confianza publicado en línea o en una red local**.</span><span class="sxs-lookup"><span data-stu-id="3749e-111">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="3749e-112">El valor de la **dirección de metadatos de Federación (nombre de host o dirección URL)** se establece en `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="3749e-112">The **Federation metadata address (host name or URL)** value is set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="3749e-113">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3749e-113">Click **Next**.</span></span>
7. <span data-ttu-id="3749e-114">En la página **Seleccionar origen de datos** , escriba el nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="3749e-114">On the **Select Data Source** page, type the display name.</span></span> <span data-ttu-id="3749e-115">Microsoft recomienda la **plataforma de identidad de Microsoft Office 365 en todo el mundo**.</span><span class="sxs-lookup"><span data-stu-id="3749e-115">Microsoft recommends **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="3749e-116">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3749e-116">Click **Next**.</span></span>
8. <span data-ttu-id="3749e-117">Haga clic en **siguiente** en la página **¿configurar la autenticación multifactor ahora?**, **Elija reglas de autorización de emisión** y **listas para agregar páginas de confianza** .</span><span class="sxs-lookup"><span data-stu-id="3749e-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and **Ready to Add Trust** pages.</span></span>
9. <span data-ttu-id="3749e-118">Haga clic en **cerrar** en la página **Finalizar** .</span><span class="sxs-lookup"><span data-stu-id="3749e-118">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="3749e-119">Al cerrar el asistente, se establece la relación de confianza para usuario autenticado con los servicios de Office 365 eSTS.</span><span class="sxs-lookup"><span data-stu-id="3749e-119">By closing the wizard, the Relying Party Trust to the Office 365 services eSTS is established.</span></span> <span data-ttu-id="3749e-120">Sin embargo, no se establecen reglas de transformación de emisión.</span><span class="sxs-lookup"><span data-stu-id="3749e-120">However, no Issuance Transform rules are established.</span></span>

<span data-ttu-id="3749e-121">Puede usar la [ayuda de AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) para generar las reglas de transformación de emisión correctas.</span><span class="sxs-lookup"><span data-stu-id="3749e-121">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="3749e-122">Las reglas de notificaciones generadas creadas con la ayuda de AD FS pueden agregarse manualmente a través de la consola de administración de AD FS o con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3749e-122">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="3749e-123">La ayuda de AD FS generará los scripts de PowerShell necesarios que se deben ejecutar.</span><span class="sxs-lookup"><span data-stu-id="3749e-123">AD FS Help will generate the necessary PowerShell scripts that need to be run.</span></span>  

1. <span data-ttu-id="3749e-124">Ejecute **generar notificaciones** en la ayuda de AD FS y copie el script de transformación de notificaciones de PowerShell con la opción de **copia** situada en la esquina superior derecha del script.</span><span class="sxs-lookup"><span data-stu-id="3749e-124">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="3749e-125">Pegue el PowerShell generado en lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3749e-125">Paste the generated PowerShell into the following:</span></span>

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  <span data-ttu-id="3749e-126">Ejecute el script completado.</span><span class="sxs-lookup"><span data-stu-id="3749e-126">Execute the completed script.</span></span>
4.  <span data-ttu-id="3749e-127">Compruebe que hay dos relaciones de confianza para usuario autenticado presentes; uno para el mundo y otro para BF.</span><span class="sxs-lookup"><span data-stu-id="3749e-127">Verify that two Relying Party trusts are present; one for worldwide and one for BF.</span></span>
5.  <span data-ttu-id="3749e-128">Realice una copia de seguridad de las confianzas mediante [estos pasos](#backup).</span><span class="sxs-lookup"><span data-stu-id="3749e-128">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="3749e-129">Guárdelo con el nombre **FFAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="3749e-129">Save it with the name **FFAndWorldwide**.</span></span>
6.  <span data-ttu-id="3749e-130">Complete la migración del back-end y compruebe que AD FS sigue funcionando durante el proceso de migración.</span><span class="sxs-lookup"><span data-stu-id="3749e-130">Complete your backend migration and verify that AD FS still works during migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="3749e-131">Recuperación ante desastres de AD FS (base de datos WID)</span><span class="sxs-lookup"><span data-stu-id="3749e-131">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="3749e-132">Para restaurar la granja de AD FS, es necesario aprovechar la [herramienta de restauración rápida de AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) ante desastres.</span><span class="sxs-lookup"><span data-stu-id="3749e-132">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="3749e-133">Por lo tanto, la herramienta debe descargarse y antes de iniciar la migración, se debe crear una copia de seguridad y almacenarla de forma segura.</span><span class="sxs-lookup"><span data-stu-id="3749e-133">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="3749e-134">En este ejemplo (entornos TAT) se han ejecutado los siguientes comandos para hacer una copia de seguridad de la granja de servidores:</span><span class="sxs-lookup"><span data-stu-id="3749e-134">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="3749e-135">Copia de seguridad de una granja de AD FS</span><span class="sxs-lookup"><span data-stu-id="3749e-135">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="3749e-136">Instale la herramienta de restauración rápida de AD FS en el servidor principal de AD FS.</span><span class="sxs-lookup"><span data-stu-id="3749e-136">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="3749e-137">Importe el módulo en una sesión de PowerShell con este comando.</span><span class="sxs-lookup"><span data-stu-id="3749e-137">Import the module in a PowerShell session with this command.</span></span>

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. <span data-ttu-id="3749e-138">Ejecute el comando de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="3749e-138">Run the backup command:</span></span>

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. <span data-ttu-id="3749e-139">Almacene la copia de seguridad de forma segura en un destino deseado.</span><span class="sxs-lookup"><span data-stu-id="3749e-139">Store the backup safely on a desired destination.</span></span> 

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="3749e-140">Restauración de una granja de AD FS</span><span class="sxs-lookup"><span data-stu-id="3749e-140">Restore an AD FS Farm</span></span>

<span data-ttu-id="3749e-141">Si la granja de servidores falló completamente y no hay forma de volver a la granja de servidores anterior, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3749e-141">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="3749e-142">Mueva la copia de seguridad previamente generada y almacenada al nuevo servidor principal de AD FS.</span><span class="sxs-lookup"><span data-stu-id="3749e-142">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="3749e-143">Ejecute el siguiente `Restore-ADFS` comando de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3749e-143">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="3749e-144">Si es necesario, importe de antemano el certificado SSL de AD FS.</span><span class="sxs-lookup"><span data-stu-id="3749e-144">If necessary, import the AD FS SSL certificate beforehand.</span></span>

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. <span data-ttu-id="3749e-145">Apunte sus nuevos registros DNS o un equilibrador de carga a los nuevos servidores de AD FS.</span><span class="sxs-lookup"><span data-stu-id="3749e-145">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="3749e-146">Más información</span><span class="sxs-lookup"><span data-stu-id="3749e-146">More information</span></span>

<span data-ttu-id="3749e-147">Introducción:</span><span class="sxs-lookup"><span data-stu-id="3749e-147">Getting started:</span></span>

- [<span data-ttu-id="3749e-148">Migración desde Microsoft Cloud Alemania a Office 365 Services en las nuevas regiones del centro de administración de Office en alemán</span><span class="sxs-lookup"><span data-stu-id="3749e-148">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="3749e-149">Asistencia para la migración a Microsoft Cloud Alemania</span><span class="sxs-lookup"><span data-stu-id="3749e-149">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="3749e-150">Cómo participar en la migración</span><span class="sxs-lookup"><span data-stu-id="3749e-150">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="3749e-151">Experiencia del cliente durante la migración</span><span class="sxs-lookup"><span data-stu-id="3749e-151">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="3749e-152">Desplazarse por la transición:</span><span class="sxs-lookup"><span data-stu-id="3749e-152">Moving through the transition:</span></span>

- [<span data-ttu-id="3749e-153">Impacto y acciones de las fases de migración</span><span class="sxs-lookup"><span data-stu-id="3749e-153">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="3749e-154">Pre-trabajo adicional</span><span class="sxs-lookup"><span data-stu-id="3749e-154">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="3749e-155">Información adicional para [servicios](ms-cloud-germany-transition-add-general.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="3749e-155">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="3749e-156">Aplicaciones en la nube:</span><span class="sxs-lookup"><span data-stu-id="3749e-156">Cloud apps:</span></span>

- [<span data-ttu-id="3749e-157">Información del programa de migración de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3749e-157">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="3749e-158">Información del programa de migración de Power BI</span><span class="sxs-lookup"><span data-stu-id="3749e-158">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="3749e-159">Introducción a su actualización de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3749e-159">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)