---
title: Exportar evaluación de inventario de software por dispositivo
description: Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.
keywords: api, apis, evaluación de exportación, evaluación por dispositivo, informe de evaluación de vulnerabilidad, evaluación de vulnerabilidad de dispositivo, informe de vulnerabilidad de dispositivo, evaluación de configuración segura, informe de configuración segura, evaluación de vulnerabilidades de software, informe de vulnerabilidades de software, informe de vulnerabilidad por máquina,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: ecfeaa10eda6b3832b7196c0598d6584783bb5ff
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653681"
---
# <a name="export-software-inventory-assessment-per-device"></a><span data-ttu-id="72fa6-104">Exportar evaluación de inventario de software por dispositivo</span><span class="sxs-lookup"><span data-stu-id="72fa6-104">Export software inventory assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="72fa6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="72fa6-105">**Applies to:**</span></span>

- [<span data-ttu-id="72fa6-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="72fa6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="72fa6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72fa6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="72fa6-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="72fa6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="72fa6-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="72fa6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="72fa6-110">Hay diferentes llamadas API para obtener diferentes tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="72fa6-110">There are different API calls to get different types of data.</span></span> <span data-ttu-id="72fa6-111">Dado que la cantidad de datos puede ser muy grande, hay dos formas de recuperarlos:</span><span class="sxs-lookup"><span data-stu-id="72fa6-111">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="72fa6-112">**OData**  La API extrae todos los datos de la organización como respuestas Json, siguiendo el protocolo OData.</span><span class="sxs-lookup"><span data-stu-id="72fa6-112">**OData**  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="72fa6-113">Este método es el mejor para _organizaciones pequeñas con dispositivos de menos de 100 K._</span><span class="sxs-lookup"><span data-stu-id="72fa6-113">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="72fa6-114">La respuesta se pagina, por lo que puede usar el campo odata.nextLink de la respuesta \@ para obtener los siguientes resultados.</span><span class="sxs-lookup"><span data-stu-id="72fa6-114">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="72fa6-115">**a través de archivos** Esta solución de API permite extraer grandes cantidades de datos de forma más rápida y confiable.</span><span class="sxs-lookup"><span data-stu-id="72fa6-115">**via files** This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="72fa6-116">Por lo tanto, se recomienda para organizaciones grandes, con más de 100 K dispositivos.</span><span class="sxs-lookup"><span data-stu-id="72fa6-116">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="72fa6-117">Esta API extrae todos los datos de la organización como archivos de descarga.</span><span class="sxs-lookup"><span data-stu-id="72fa6-117">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="72fa6-118">La respuesta contiene direcciones URL para descargar todos los datos de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="72fa6-118">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="72fa6-119">Esta API le permite descargar todos los datos de Azure Storage de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="72fa6-119">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="72fa6-120">Llama a la API para obtener una lista de direcciones URL de descarga con todos los datos de la organización.</span><span class="sxs-lookup"><span data-stu-id="72fa6-120">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="72fa6-121">Descargue todos los archivos con las direcciones URL de descarga y procese los datos como quiera.</span><span class="sxs-lookup"><span data-stu-id="72fa6-121">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="72fa6-122">Los datos recopilados (para _OData_ o _a_ través de archivos) son la instantánea actual del estado actual y no contienen datos históricos.</span><span class="sxs-lookup"><span data-stu-id="72fa6-122">The data that is collected (for either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="72fa6-123">Para recopilar datos históricos, los clientes deben guardar los datos en sus propios almacenamientos de datos.</span><span class="sxs-lookup"><span data-stu-id="72fa6-123">In order to collect historic data, customers must save the data in their own data storages.</span></span>

<span data-ttu-id="72fa6-124">A menos que se indique lo \*\*\*\* contrario, todos los métodos de evaluación de exportación enumerados son exportación completa y por **_dispositivo_** (también **_denominados por dispositivo_**).</span><span class="sxs-lookup"><span data-stu-id="72fa6-124">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-inventory-assessment-odata"></a><span data-ttu-id="72fa6-125">1. Exportar evaluación de inventario de software (OData)</span><span class="sxs-lookup"><span data-stu-id="72fa6-125">1. Export software inventory assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="72fa6-126">Descripción del método de api 1.1</span><span class="sxs-lookup"><span data-stu-id="72fa6-126">1.1 API method description</span></span>

<span data-ttu-id="72fa6-127">Esta respuesta de la API contiene todos los datos del software instalado por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="72fa6-127">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="72fa6-128">Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span><span class="sxs-lookup"><span data-stu-id="72fa6-128">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="limitations"></a><span data-ttu-id="72fa6-129">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="72fa6-129">Limitations</span></span>

- <span data-ttu-id="72fa6-130">El tamaño máximo de página es 200 000.</span><span class="sxs-lookup"><span data-stu-id="72fa6-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="72fa6-131">Las limitaciones de velocidad para esta API son 30 llamadas por minuto y 1000 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="72fa6-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="72fa6-132">1.2 Permisos</span><span class="sxs-lookup"><span data-stu-id="72fa6-132">1.2 Permissions</span></span>

<span data-ttu-id="72fa6-133">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="72fa6-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="72fa6-134">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="72fa6-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="72fa6-135">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="72fa6-135">Permission type</span></span> | <span data-ttu-id="72fa6-136">Permiso</span><span class="sxs-lookup"><span data-stu-id="72fa6-136">Permission</span></span> | <span data-ttu-id="72fa6-137">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="72fa6-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="72fa6-138">Aplicación</span><span class="sxs-lookup"><span data-stu-id="72fa6-138">Application</span></span> | <span data-ttu-id="72fa6-139">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="72fa6-139">Software.Read.All</span></span> | <span data-ttu-id="72fa6-140">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="72fa6-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="72fa6-141">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="72fa6-141">Delegated (work or school account)</span></span> | <span data-ttu-id="72fa6-142">Software.Read</span><span class="sxs-lookup"><span data-stu-id="72fa6-142">Software.Read</span></span> | <span data-ttu-id="72fa6-143">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="72fa6-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="72fa6-144">DIRECCIÓN URL 1.3</span><span class="sxs-lookup"><span data-stu-id="72fa6-144">1.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="72fa6-145">1.4 Parámetros</span><span class="sxs-lookup"><span data-stu-id="72fa6-145">1.4 Parameters</span></span>

- <span data-ttu-id="72fa6-146">pageSize (valor predeterminado = 50.000): número de resultados en respuesta.</span><span class="sxs-lookup"><span data-stu-id="72fa6-146">pageSize (default = 50,000) – number of results in response.</span></span>

- <span data-ttu-id="72fa6-147">$top: número de resultados que se devolverán (no devuelve @odata.nextLink y, por lo tanto, no extrae todos los datos)</span><span class="sxs-lookup"><span data-stu-id="72fa6-147">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="72fa6-148">1.5 Propiedades</span><span class="sxs-lookup"><span data-stu-id="72fa6-148">1.5 Properties</span></span>

>[!NOTE]
>
><span data-ttu-id="72fa6-149">-Cada registro tiene aproximadamente 0,5 KB de datos.</span><span class="sxs-lookup"><span data-stu-id="72fa6-149">-Each record is approximately 0.5KB of data.</span></span> <span data-ttu-id="72fa6-150">Debe tener esto en cuenta al elegir el parámetro pageSize correcto.</span><span class="sxs-lookup"><span data-stu-id="72fa6-150">You should take this into account when choosing the correct pageSize parameter for you.</span></span>

><span data-ttu-id="72fa6-151">-Las propiedades definidas en la tabla siguiente se enumeran alfanuméricamente, por identificador de propiedad.</span><span class="sxs-lookup"><span data-stu-id="72fa6-151">-The properties defined in the following table are listed alphanumerically, by property ID.</span></span> <span data-ttu-id="72fa6-152">Al ejecutar esta API, el resultado resultante no se devolverá necesariamente en el mismo orden enumerado en estas tablas.</span><span class="sxs-lookup"><span data-stu-id="72fa6-152">When running this API, the resulting output will not necessarily be returned in the same order listed in these tables.</span></span>
>
><span data-ttu-id="72fa6-153">-Es posible que se devuelvan algunas columnas adicionales en la respuesta.</span><span class="sxs-lookup"><span data-stu-id="72fa6-153">-Some additional columns might be returned in the response.</span></span> <span data-ttu-id="72fa6-154">Estas columnas son temporales y pueden quitarse, use solo las columnas documentadas.</span><span class="sxs-lookup"><span data-stu-id="72fa6-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>

<span data-ttu-id="72fa6-155">Propiedad (id)</span><span class="sxs-lookup"><span data-stu-id="72fa6-155">Property (id)</span></span> | <span data-ttu-id="72fa6-156">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="72fa6-156">Data type</span></span> | <span data-ttu-id="72fa6-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="72fa6-157">Description</span></span> | <span data-ttu-id="72fa6-158">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="72fa6-158">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="72fa6-159">DeviceId</span><span class="sxs-lookup"><span data-stu-id="72fa6-159">DeviceId</span></span> | <span data-ttu-id="72fa6-160">string</span><span class="sxs-lookup"><span data-stu-id="72fa6-160">string</span></span> | <span data-ttu-id="72fa6-161">Identificador único del dispositivo en el servicio.</span><span class="sxs-lookup"><span data-stu-id="72fa6-161">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="72fa6-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="72fa6-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="72fa6-163">DeviceName</span><span class="sxs-lookup"><span data-stu-id="72fa6-163">DeviceName</span></span> | <span data-ttu-id="72fa6-164">string</span><span class="sxs-lookup"><span data-stu-id="72fa6-164">string</span></span> | <span data-ttu-id="72fa6-165">Nombre de dominio completo (FQDN) del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="72fa6-165">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="72fa6-166">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="72fa6-166">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="72fa6-167">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="72fa6-167">DiskPaths</span></span> | <span data-ttu-id="72fa6-168">Array[string]</span><span class="sxs-lookup"><span data-stu-id="72fa6-168">Array[string]</span></span>  | <span data-ttu-id="72fa6-169">Prueba en disco de que el producto está instalado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="72fa6-169">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="72fa6-170">[ "C: \\ Archivos de programa (x86) \\ Microsoft \\ Silverlight \\ Application \\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="72fa6-170">[ "C:\\Program Files (x86)\\Microsoft\\Silverlight\\Application\\silverlight.exe" ]</span></span>
<span data-ttu-id="72fa6-171">EndOfSupportDate</span><span class="sxs-lookup"><span data-stu-id="72fa6-171">EndOfSupportDate</span></span> | <span data-ttu-id="72fa6-172">string</span><span class="sxs-lookup"><span data-stu-id="72fa6-172">string</span></span> | <span data-ttu-id="72fa6-173">La fecha en la que la compatibilidad con este software tiene o finalizará.</span><span class="sxs-lookup"><span data-stu-id="72fa6-173">The date in which support for this software has or will end.</span></span> | <span data-ttu-id="72fa6-174">2020-12-30</span><span class="sxs-lookup"><span data-stu-id="72fa6-174">2020-12-30</span></span>
<span data-ttu-id="72fa6-175">EndOfSupportStatus</span><span class="sxs-lookup"><span data-stu-id="72fa6-175">EndOfSupportStatus</span></span> | <span data-ttu-id="72fa6-176">string</span><span class="sxs-lookup"><span data-stu-id="72fa6-176">string</span></span> | <span data-ttu-id="72fa6-177">Estado de finalización de la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="72fa6-177">End of support status.</span></span> <span data-ttu-id="72fa6-178">Puede contener estos valores posibles: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span><span class="sxs-lookup"><span data-stu-id="72fa6-178">Can contain these possible values: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span></span> | <span data-ttu-id="72fa6-179">Próximos EOS</span><span class="sxs-lookup"><span data-stu-id="72fa6-179">Upcoming EOS</span></span>
<span data-ttu-id="72fa6-180">Id</span><span class="sxs-lookup"><span data-stu-id="72fa6-180">Id</span></span> | <span data-ttu-id="72fa6-181">string</span><span class="sxs-lookup"><span data-stu-id="72fa6-181">string</span></span> | <span data-ttu-id="72fa6-182">Identificador único del registro.</span><span class="sxs-lookup"><span data-stu-id="72fa6-182">Unique identifier for the record.</span></span> | <span data-ttu-id="72fa6-183">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="72fa6-183">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="72fa6-184">NumberOfWeaknesses</span><span class="sxs-lookup"><span data-stu-id="72fa6-184">NumberOfWeaknesses</span></span> | <span data-ttu-id="72fa6-185">Entero</span><span class="sxs-lookup"><span data-stu-id="72fa6-185">int</span></span> | <span data-ttu-id="72fa6-186">Número de debilidades de este software en este dispositivo</span><span class="sxs-lookup"><span data-stu-id="72fa6-186">Number of weaknesses on this software on this device</span></span> | <span data-ttu-id="72fa6-187">3</span><span class="sxs-lookup"><span data-stu-id="72fa6-187">3</span></span>
<span data-ttu-id="72fa6-188">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="72fa6-188">OSPlatform</span></span> | <span data-ttu-id="72fa6-189">string</span><span class="sxs-lookup"><span data-stu-id="72fa6-189">string</span></span> | <span data-ttu-id="72fa6-190">Plataforma del sistema operativo que se ejecuta en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="72fa6-190">Platform of the operating system running on the device.</span></span> <span data-ttu-id="72fa6-191">Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="72fa6-191">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="72fa6-192">Consulta sistemas operativos y plataformas compatibles con tvm para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="72fa6-192">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="72fa6-193">Windows10</span><span class="sxs-lookup"><span data-stu-id="72fa6-193">Windows10</span></span>
<span data-ttu-id="72fa6-194">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="72fa6-194">RbacGroupName</span></span> | <span data-ttu-id="72fa6-195">string</span><span class="sxs-lookup"><span data-stu-id="72fa6-195">string</span></span> | <span data-ttu-id="72fa6-196">Grupo de control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="72fa6-196">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="72fa6-197">Si este dispositivo no está asignado a ningún grupo RBAC, el valor será "Unassigned".</span><span class="sxs-lookup"><span data-stu-id="72fa6-197">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="72fa6-198">Si la organización no contiene ningún grupo RBAC, el valor será "None".</span><span class="sxs-lookup"><span data-stu-id="72fa6-198">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="72fa6-199">Servidores</span><span class="sxs-lookup"><span data-stu-id="72fa6-199">Servers</span></span>
<span data-ttu-id="72fa6-200">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="72fa6-200">RegistryPaths</span></span> | <span data-ttu-id="72fa6-201">Array[string]</span><span class="sxs-lookup"><span data-stu-id="72fa6-201">Array[string]</span></span> | <span data-ttu-id="72fa6-202">El Registro evidencia que el producto está instalado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="72fa6-202">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="72fa6-203">[ "HKEY_LOCAL_MACHINE \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion Uninstall Microsoft \\ \\ Silverlight" ]</span><span class="sxs-lookup"><span data-stu-id="72fa6-203">[ "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Silverlight" ]</span></span>
<span data-ttu-id="72fa6-204">SoftwareFirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="72fa6-204">SoftwareFirstSeenTimestamp</span></span> | <span data-ttu-id="72fa6-205">string</span><span class="sxs-lookup"><span data-stu-id="72fa6-205">string</span></span> | <span data-ttu-id="72fa6-206">La primera vez que se vio este software en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="72fa6-206">The first time this software was seen on the device.</span></span> | <span data-ttu-id="72fa6-207">2019-04-07 02:06:47</span><span class="sxs-lookup"><span data-stu-id="72fa6-207">2019-04-07 02:06:47</span></span>
<span data-ttu-id="72fa6-208">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="72fa6-208">SoftwareName</span></span> | <span data-ttu-id="72fa6-209">string</span><span class="sxs-lookup"><span data-stu-id="72fa6-209">string</span></span> | <span data-ttu-id="72fa6-210">Nombre del producto de software.</span><span class="sxs-lookup"><span data-stu-id="72fa6-210">Name of the software product.</span></span> | <span data-ttu-id="72fa6-211">Silverlight</span><span class="sxs-lookup"><span data-stu-id="72fa6-211">Silverlight</span></span>
<span data-ttu-id="72fa6-212">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="72fa6-212">SoftwareVendor</span></span> | <span data-ttu-id="72fa6-213">string</span><span class="sxs-lookup"><span data-stu-id="72fa6-213">string</span></span> | <span data-ttu-id="72fa6-214">Nombre del proveedor de software.</span><span class="sxs-lookup"><span data-stu-id="72fa6-214">Name of the software vendor.</span></span> | <span data-ttu-id="72fa6-215">microsoft</span><span class="sxs-lookup"><span data-stu-id="72fa6-215">microsoft</span></span>
<span data-ttu-id="72fa6-216">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="72fa6-216">SoftwareVersion</span></span> | <span data-ttu-id="72fa6-217">string</span><span class="sxs-lookup"><span data-stu-id="72fa6-217">string</span></span> | <span data-ttu-id="72fa6-218">Número de versión del producto de software.</span><span class="sxs-lookup"><span data-stu-id="72fa6-218">Version number of the software product.</span></span> | <span data-ttu-id="72fa6-219">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="72fa6-219">81.0.4044.138</span></span>

### <a name="16-examples"></a><span data-ttu-id="72fa6-220">1.6 Ejemplos</span><span class="sxs-lookup"><span data-stu-id="72fa6-220">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="72fa6-221">1.6.1 Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="72fa6-221">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a><span data-ttu-id="72fa6-222">Ejemplo de respuesta 1.6.2</span><span class="sxs-lookup"><span data-stu-id="72fa6-222">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a><span data-ttu-id="72fa6-223">2. Exportar la evaluación del inventario de software (a través de archivos)</span><span class="sxs-lookup"><span data-stu-id="72fa6-223">2. Export software inventory assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="72fa6-224">Descripción del método api 2.1</span><span class="sxs-lookup"><span data-stu-id="72fa6-224">2.1 API method description</span></span>

<span data-ttu-id="72fa6-225">Esta respuesta de la API contiene todos los datos del software instalado por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="72fa6-225">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="72fa6-226">Devuelve una tabla con una entrada para cada combinación única de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span><span class="sxs-lookup"><span data-stu-id="72fa6-226">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="211-limitations"></a><span data-ttu-id="72fa6-227">2.1.1 Limitaciones</span><span class="sxs-lookup"><span data-stu-id="72fa6-227">2.1.1 Limitations</span></span>

<span data-ttu-id="72fa6-228">Las limitaciones de velocidad para esta API son 5 llamadas por minuto y 20 llamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="72fa6-228">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="72fa6-229">2.2 Permisos</span><span class="sxs-lookup"><span data-stu-id="72fa6-229">2.2 Permissions</span></span>

<span data-ttu-id="72fa6-230">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="72fa6-230">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="72fa6-231">Para obtener más información, incluido cómo elegir permisos, consulte [Use Microsoft Defender for Endpoint API para obtener más información.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="72fa6-231">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="72fa6-232">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="72fa6-232">Permission type</span></span> | <span data-ttu-id="72fa6-233">Permiso</span><span class="sxs-lookup"><span data-stu-id="72fa6-233">Permission</span></span> | <span data-ttu-id="72fa6-234">Nombre para mostrar de permisos</span><span class="sxs-lookup"><span data-stu-id="72fa6-234">Permission display name</span></span>
---|---|---
<span data-ttu-id="72fa6-235">Aplicación</span><span class="sxs-lookup"><span data-stu-id="72fa6-235">Application</span></span> | <span data-ttu-id="72fa6-236">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="72fa6-236">Software.Read.All</span></span> | <span data-ttu-id="72fa6-237">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="72fa6-237">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="72fa6-238">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="72fa6-238">Delegated (work or school account)</span></span> | <span data-ttu-id="72fa6-239">Software.Read</span><span class="sxs-lookup"><span data-stu-id="72fa6-239">Software.Read</span></span> | <span data-ttu-id="72fa6-240">\'Leer información sobre vulnerabilidades de administración de amenazas y vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="72fa6-240">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="72fa6-241">DIRECCIÓN URL 2.3</span><span class="sxs-lookup"><span data-stu-id="72fa6-241">2.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a><span data-ttu-id="72fa6-242">Parameters</span><span class="sxs-lookup"><span data-stu-id="72fa6-242">Parameters</span></span>

- <span data-ttu-id="72fa6-243">sasValidHours: el número de horas durante las que las direcciones URL de descarga serán válidas (máximo 24 horas)</span><span class="sxs-lookup"><span data-stu-id="72fa6-243">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="72fa6-244">2.5 Propiedades</span><span class="sxs-lookup"><span data-stu-id="72fa6-244">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="72fa6-245">Los archivos son archivos comprimidos de gzip & en formato Json de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="72fa6-245">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="72fa6-246">Las direcciones URL de descarga solo son válidas durante 3 horas.</span><span class="sxs-lookup"><span data-stu-id="72fa6-246">The download URLs are only valid for 3 hours.</span></span> <span data-ttu-id="72fa6-247">De lo contrario, puede usar el parámetro.</span><span class="sxs-lookup"><span data-stu-id="72fa6-247">Otherwise you can use the parameter.</span></span>
>
><span data-ttu-id="72fa6-248">_ Para obtener la velocidad máxima de descarga de los datos, puede asegurarse de que está descargando desde la misma región de Azure en la que residen los datos.</span><span class="sxs-lookup"><span data-stu-id="72fa6-248">_ For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>
<span data-ttu-id="72fa6-249">Propiedad (id)</span><span class="sxs-lookup"><span data-stu-id="72fa6-249">Property (id)</span></span> | <span data-ttu-id="72fa6-250">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="72fa6-250">Data type</span></span> | <span data-ttu-id="72fa6-251">Descripción</span><span class="sxs-lookup"><span data-stu-id="72fa6-251">Description</span></span> | <span data-ttu-id="72fa6-252">Ejemplo de un valor devuelto</span><span class="sxs-lookup"><span data-stu-id="72fa6-252">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="72fa6-253">Exportar archivos</span><span class="sxs-lookup"><span data-stu-id="72fa6-253">Export files</span></span> | <span data-ttu-id="72fa6-254">cadena de \[ matriz\]</span><span class="sxs-lookup"><span data-stu-id="72fa6-254">array\[string\]</span></span> | <span data-ttu-id="72fa6-255">Una lista de direcciones URL de descarga de archivos que contiene la instantánea actual de la organización</span><span class="sxs-lookup"><span data-stu-id="72fa6-255">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="72fa6-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="72fa6-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="72fa6-257">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="72fa6-257">GeneratedTime</span></span> | <span data-ttu-id="72fa6-258">string</span><span class="sxs-lookup"><span data-stu-id="72fa6-258">string</span></span> | <span data-ttu-id="72fa6-259">Hora en que se generó la exportación.</span><span class="sxs-lookup"><span data-stu-id="72fa6-259">The time that the export was generated.</span></span> | <span data-ttu-id="72fa6-260">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="72fa6-260">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="72fa6-261">2.6 Ejemplos</span><span class="sxs-lookup"><span data-stu-id="72fa6-261">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="72fa6-262">2.6.1 Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="72fa6-262">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a><span data-ttu-id="72fa6-263">Ejemplo de respuesta 2.6.2</span><span class="sxs-lookup"><span data-stu-id="72fa6-263">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="72fa6-264">Vea también</span><span class="sxs-lookup"><span data-stu-id="72fa6-264">See also</span></span>

- [<span data-ttu-id="72fa6-265">Exportar métodos de evaluación y propiedades por dispositivo</span><span class="sxs-lookup"><span data-stu-id="72fa6-265">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="72fa6-266">Exportar evaluación de configuración segura por dispositivo</span><span class="sxs-lookup"><span data-stu-id="72fa6-266">Export secure configuration assessment per device</span></span>](get-assessmnt-secure-cfg.md)

- [<span data-ttu-id="72fa6-267">Evaluación de vulnerabilidades de software de exportación por dispositivo</span><span class="sxs-lookup"><span data-stu-id="72fa6-267">Export software vulnerabilities assessment per device</span></span>](get-assessmnt-software-vulnerabilities.md)

<span data-ttu-id="72fa6-268">Otros relacionados</span><span class="sxs-lookup"><span data-stu-id="72fa6-268">Other related</span></span>

- [<span data-ttu-id="72fa6-269">Amenazas basadas en riesgos & administración de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="72fa6-269">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="72fa6-270">Vulnerabilidades de la organización</span><span class="sxs-lookup"><span data-stu-id="72fa6-270">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)