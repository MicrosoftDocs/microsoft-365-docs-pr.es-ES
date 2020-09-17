---
title: API de lista de incidentes en protección contra amenazas de Microsoft
description: Obtenga información sobre cómo enumerar la API de incidentes en protección contra amenazas de Microsoft
keywords: lista, incidente, incidentes, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 54f5ba640ecc175e78c7087df8016e9b715f17f7
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775116"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a><span data-ttu-id="a54e6-104">API de lista de incidentes en protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a54e6-104">List incidents API in Microsoft Threat Protection</span></span>

<span data-ttu-id="a54e6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a54e6-105">**Applies to:**</span></span>

- <span data-ttu-id="a54e6-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a54e6-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a54e6-107">Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="a54e6-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a54e6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="a54e6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="a54e6-109">Descripción de la API</span><span class="sxs-lookup"><span data-stu-id="a54e6-109">API description</span></span>

<span data-ttu-id="a54e6-110">La API de incidentes permite ordenar los incidentes para priorizar y crear una respuesta Cybersecurity informada.</span><span class="sxs-lookup"><span data-stu-id="a54e6-110">The Incident API allows you to sort through incidents to prioritize and create an informed cybersecurity response.</span></span> <span data-ttu-id="a54e6-111">Expone una colección de incidentes que se marcaron desde dispositivos, cuentas de correo electrónico y usuarios de la red, dentro del intervalo de tiempo especificado en la Directiva de retención del entorno.</span><span class="sxs-lookup"><span data-stu-id="a54e6-111">It exposes a collection of incidents that were flagged from devices, email accounts, and users in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="a54e6-112">Los incidentes más recientes se muestran en la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="a54e6-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="a54e6-113">Cada incidente contiene una matriz de alertas relacionadas y sus entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="a54e6-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<br><span data-ttu-id="a54e6-114">La API admite los siguientes operadores **OData** :</span><span class="sxs-lookup"><span data-stu-id="a54e6-114">The API supports the following **OData** operators:</span></span>
<br><span data-ttu-id="a54e6-115">```$filter``` on: ```lastUpdateTime``` , ```createdTime``` ```status``` y ```assignedTo``` propiedades.</span><span class="sxs-lookup"><span data-stu-id="a54e6-115">```$filter``` on: ```lastUpdateTime```, ```createdTime```, ```status``` and ```assignedTo``` properties.</span></span>
<br><span data-ttu-id="a54e6-116">```$top``` con valor máximo de **100**</span><span class="sxs-lookup"><span data-stu-id="a54e6-116">```$top``` with max value of **100**</span></span>
<br>```$skip```

## <a name="limitations"></a><span data-ttu-id="a54e6-117">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="a54e6-117">Limitations</span></span>

1. <span data-ttu-id="a54e6-118">El tamaño máximo de página es de **100 incidentes**.</span><span class="sxs-lookup"><span data-stu-id="a54e6-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="a54e6-119">La tasa de solicitudes máxima es de **50 llamadas por minuto** y **1500 de llamadas por hora**.</span><span class="sxs-lookup"><span data-stu-id="a54e6-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="a54e6-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="a54e6-120">Permissions</span></span>

<span data-ttu-id="a54e6-121">Se requiere uno de los siguientes permisos para llamar a esta API.</span><span class="sxs-lookup"><span data-stu-id="a54e6-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a54e6-122">Para obtener más información, incluido cómo elegir permisos, consulte [acceso a las API de Microsoft Threat Protection](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="a54e6-122">To learn more, including how to choose permissions, see [Access Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="a54e6-123">Tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="a54e6-123">Permission type</span></span> |   <span data-ttu-id="a54e6-124">Permiso</span><span class="sxs-lookup"><span data-stu-id="a54e6-124">Permission</span></span>  |   <span data-ttu-id="a54e6-125">Nombre para mostrar del permiso</span><span class="sxs-lookup"><span data-stu-id="a54e6-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a54e6-126">Aplicación</span><span class="sxs-lookup"><span data-stu-id="a54e6-126">Application</span></span> |   <span data-ttu-id="a54e6-127">Incident. Read. All</span><span class="sxs-lookup"><span data-stu-id="a54e6-127">Incident.Read.All</span></span> | <span data-ttu-id="a54e6-128">' Leer todos los incidentes '</span><span class="sxs-lookup"><span data-stu-id="a54e6-128">'Read all incidents'</span></span>
<span data-ttu-id="a54e6-129">Aplicación</span><span class="sxs-lookup"><span data-stu-id="a54e6-129">Application</span></span> |   <span data-ttu-id="a54e6-130">Incident. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="a54e6-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="a54e6-131">' Leer y escribir todos los incidentes '</span><span class="sxs-lookup"><span data-stu-id="a54e6-131">'Read and write all incidents'</span></span>
<span data-ttu-id="a54e6-132">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="a54e6-132">Delegated (work or school account)</span></span> | <span data-ttu-id="a54e6-133">Incident. Read</span><span class="sxs-lookup"><span data-stu-id="a54e6-133">Incident.Read</span></span> | <span data-ttu-id="a54e6-134">' Incidentes de lectura '</span><span class="sxs-lookup"><span data-stu-id="a54e6-134">'Read incidents'</span></span>
<span data-ttu-id="a54e6-135">Delegado (cuenta profesional o educativa)</span><span class="sxs-lookup"><span data-stu-id="a54e6-135">Delegated (work or school account)</span></span> | <span data-ttu-id="a54e6-136">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a54e6-136">Incident.ReadWrite</span></span> | <span data-ttu-id="a54e6-137">' Incidentes de lectura y escritura '</span><span class="sxs-lookup"><span data-stu-id="a54e6-137">'Read and write incidents'</span></span>

> [!Note]
> <span data-ttu-id="a54e6-138">Al obtener un token con credenciales de usuario:</span><span class="sxs-lookup"><span data-stu-id="a54e6-138">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="a54e6-139">El usuario debe tener permiso de visualización para incidentes en el portal.</span><span class="sxs-lookup"><span data-stu-id="a54e6-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="a54e6-140">La respuesta solo incluirá los incidentes a los que el usuario está expuesto.</span><span class="sxs-lookup"><span data-stu-id="a54e6-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="a54e6-141">Solicitud HTTP</span><span class="sxs-lookup"><span data-stu-id="a54e6-141">HTTP request</span></span>

```
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="a54e6-142">Encabezados de solicitud</span><span class="sxs-lookup"><span data-stu-id="a54e6-142">Request headers</span></span>

<span data-ttu-id="a54e6-143">Nombre</span><span class="sxs-lookup"><span data-stu-id="a54e6-143">Name</span></span> | <span data-ttu-id="a54e6-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="a54e6-144">Type</span></span> | <span data-ttu-id="a54e6-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="a54e6-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="a54e6-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="a54e6-146">Authorization</span></span> | <span data-ttu-id="a54e6-147">Cadena</span><span class="sxs-lookup"><span data-stu-id="a54e6-147">String</span></span> | <span data-ttu-id="a54e6-148">{Token} de portador.</span><span class="sxs-lookup"><span data-stu-id="a54e6-148">Bearer {token}.</span></span> <span data-ttu-id="a54e6-149">**Necesario**.</span><span class="sxs-lookup"><span data-stu-id="a54e6-149">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a54e6-150">Cuerpo de la solicitud</span><span class="sxs-lookup"><span data-stu-id="a54e6-150">Request body</span></span>
<span data-ttu-id="a54e6-151">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="a54e6-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="a54e6-152">Respuesta</span><span class="sxs-lookup"><span data-stu-id="a54e6-152">Response</span></span>
<span data-ttu-id="a54e6-153">Si se ejecuta correctamente, este método devuelve 200 OK y una lista de [incidentes](api-incident.md) en el cuerpo de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="a54e6-153">If successful, this method returns 200 OK, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="a54e6-154">Asignación del esquema</span><span class="sxs-lookup"><span data-stu-id="a54e6-154">Schema mapping</span></span>

| <span data-ttu-id="a54e6-155">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="a54e6-155">Field name</span></span>                                | <span data-ttu-id="a54e6-156">Description</span><span class="sxs-lookup"><span data-stu-id="a54e6-156">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="a54e6-157">Valor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a54e6-157">Example value</span></span>                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="a54e6-158">**Metadatos del incidente**</span><span class="sxs-lookup"><span data-stu-id="a54e6-158">**Incident metadata**</span></span>                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="a54e6-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="a54e6-159">incidentId</span></span>                                | <span data-ttu-id="a54e6-160">Identificador único que representa el incidente.</span><span class="sxs-lookup"><span data-stu-id="a54e6-160">Unique identifier to represent the incident.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="a54e6-161">924565</span><span class="sxs-lookup"><span data-stu-id="a54e6-161">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="a54e6-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="a54e6-162">redirectIncidentId</span></span>                        | <span data-ttu-id="a54e6-163">Solo se rellena en caso de que un incidente se agrupe con otro incidente, como parte de la lógica de procesamiento de incidentes.</span><span class="sxs-lookup"><span data-stu-id="a54e6-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span>                                                                                                                                                                                                                                                           | <span data-ttu-id="a54e6-164">924569</span><span class="sxs-lookup"><span data-stu-id="a54e6-164">924569</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="a54e6-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="a54e6-165">incidentName</span></span>                              | <span data-ttu-id="a54e6-166">Valor de cadena disponible para cada incidente.</span><span class="sxs-lookup"><span data-stu-id="a54e6-166">String value available for every incident.</span></span>                                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="a54e6-167">Actividad de ransomware</span><span class="sxs-lookup"><span data-stu-id="a54e6-167">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="a54e6-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="a54e6-168">createdTime</span></span>                               | <span data-ttu-id="a54e6-169">Hora a la que se creó el incidente por primera vez.</span><span class="sxs-lookup"><span data-stu-id="a54e6-169">Time when incident was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                      | <span data-ttu-id="a54e6-170">2020-09-06T14:46:57.0733333 Z</span><span class="sxs-lookup"><span data-stu-id="a54e6-170">2020-09-06T14:46:57.0733333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="a54e6-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="a54e6-171">lastUpdateTime</span></span>                            | <span data-ttu-id="a54e6-172">Hora en que se actualizó por última vez el incidente en el back-end.</span><span class="sxs-lookup"><span data-stu-id="a54e6-172">Time when incident was last updated at the backend.</span></span><br> <span data-ttu-id="a54e6-173">Este campo se puede usar al establecer el parámetro de solicitud para el intervalo de tiempo durante el que se recuperan los incidentes.</span><span class="sxs-lookup"><span data-stu-id="a54e6-173">This field can be used when setting the request parameter for the range of time that incidents are retrieved.</span></span>                                                                                                                                                                                                                      | <span data-ttu-id="a54e6-174">2020-09-06T14:46:57.29 Z</span><span class="sxs-lookup"><span data-stu-id="a54e6-174">2020-09-06T14:46:57.29Z</span></span>                                                                                                                                                                                                                           |
| <span data-ttu-id="a54e6-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="a54e6-175">assignedTo</span></span>                                | <span data-ttu-id="a54e6-176">Propietario del incidente, o *null* si no hay ningún propietario asignado.</span><span class="sxs-lookup"><span data-stu-id="a54e6-176">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="a54e6-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a54e6-177">secop2@contoso.com</span></span>                                                                                                                                                                                                |
| <span data-ttu-id="a54e6-178">classification</span><span class="sxs-lookup"><span data-stu-id="a54e6-178">classification</span></span>                            | <span data-ttu-id="a54e6-179">La especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="a54e6-179">The specification for the incident.</span></span> <span data-ttu-id="a54e6-180">Los valores de la propiedad son: *Unknown*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="a54e6-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span>                                                                                                                                                                                                                                                                           | <span data-ttu-id="a54e6-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="a54e6-181">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="a54e6-182">cálculo</span><span class="sxs-lookup"><span data-stu-id="a54e6-182">determination</span></span>                             | <span data-ttu-id="a54e6-183">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="a54e6-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="a54e6-184">Los valores de la propiedad son: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other*</span><span class="sxs-lookup"><span data-stu-id="a54e6-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span>                                                                                                                                                                                                                | <span data-ttu-id="a54e6-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="a54e6-185">NotAvailable</span></span>                                                                                                                                                                                                                                      |
| <span data-ttu-id="a54e6-186">status</span><span class="sxs-lookup"><span data-stu-id="a54e6-186">status</span></span>                                    | <span data-ttu-id="a54e6-187">Clasifique los incidentes (como *activos*o *resueltos*).</span><span class="sxs-lookup"><span data-stu-id="a54e6-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="a54e6-188">Esto le ayudará a organizar y administrar la respuesta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="a54e6-188">This helps you organize and manage your response to incidents.</span></span>                                                                                                                                                                                                                                                                  | <span data-ttu-id="a54e6-189">Activo</span><span class="sxs-lookup"><span data-stu-id="a54e6-189">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="a54e6-190">severity</span><span class="sxs-lookup"><span data-stu-id="a54e6-190">severity</span></span>                                  | <span data-ttu-id="a54e6-191">Indica el posible impacto en los activos.</span><span class="sxs-lookup"><span data-stu-id="a54e6-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="a54e6-192">Cuanto mayor sea la gravedad, mayor será el impacto.</span><span class="sxs-lookup"><span data-stu-id="a54e6-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="a54e6-193">Normalmente, los elementos de mayor gravedad requieren la atención más inmediata.</span><span class="sxs-lookup"><span data-stu-id="a54e6-193">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="a54e6-194">Uno de los siguientes valores: *informativo*, *bajo*, \* medio y *alto*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                | <span data-ttu-id="a54e6-195">Mediano</span><span class="sxs-lookup"><span data-stu-id="a54e6-195">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="a54e6-196">tags</span><span class="sxs-lookup"><span data-stu-id="a54e6-196">tags</span></span>                                      | <span data-ttu-id="a54e6-197">Matriz de etiquetas personalizadas asociadas a un incidente, por ejemplo, para marcar un grupo de incidentes con una característica común.</span><span class="sxs-lookup"><span data-stu-id="a54e6-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span>                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="a54e6-198">alerts</span><span class="sxs-lookup"><span data-stu-id="a54e6-198">alerts</span></span>                                    | <span data-ttu-id="a54e6-199">Matriz de todas las alertas relacionadas con el incidente y otra información, como la gravedad, las entidades implicadas en la alerta, el origen de las alertas.</span><span class="sxs-lookup"><span data-stu-id="a54e6-199">Array of all the alerts related to the incident and other information, such as severity, entities that were involved in the alert, the source of the alerts.</span></span>                                                                                                                                                                                                                     | <span data-ttu-id="a54e6-200">\[\] (consulte los detalles de los campos de alerta a continuación)</span><span class="sxs-lookup"><span data-stu-id="a54e6-200">\[\] (see details on alert fields below)</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="a54e6-201">**Metadatos de alertas**</span><span class="sxs-lookup"><span data-stu-id="a54e6-201">**Alerts metadata**</span></span>                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="a54e6-202">alertId</span><span class="sxs-lookup"><span data-stu-id="a54e6-202">alertId</span></span>                                   | <span data-ttu-id="a54e6-203">Identificador único que representa la alerta</span><span class="sxs-lookup"><span data-stu-id="a54e6-203">Unique identifier to represent the alert</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="a54e6-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="a54e6-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>                                                                                                                                                                                                            |
| <span data-ttu-id="a54e6-205">incidentId</span><span class="sxs-lookup"><span data-stu-id="a54e6-205">incidentId</span></span>                                | <span data-ttu-id="a54e6-206">Identificador único que representa el incidente al que está asociada esta alerta</span><span class="sxs-lookup"><span data-stu-id="a54e6-206">Unique identifier to represent the incident this alert is associated with</span></span>                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="a54e6-207">924565</span><span class="sxs-lookup"><span data-stu-id="a54e6-207">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="a54e6-208">serviceSource</span><span class="sxs-lookup"><span data-stu-id="a54e6-208">serviceSource</span></span>                             | <span data-ttu-id="a54e6-209">Servicio del que se origina la alerta, como ATP de Microsoft defender, Microsoft Cloud App Security, Azure ATP o Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="a54e6-209">Service that the alert originates from, such as Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, or Office 365 ATP.</span></span>                                                                                                                                                                                                                                                                     | <span data-ttu-id="a54e6-210">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="a54e6-210">MicrosoftCloudAppSecurity</span></span>                                                                                                                                                                                                                         |
| <span data-ttu-id="a54e6-211">creationTime</span><span class="sxs-lookup"><span data-stu-id="a54e6-211">creationTime</span></span>                              | <span data-ttu-id="a54e6-212">Hora a la que se creó la alerta por primera vez.</span><span class="sxs-lookup"><span data-stu-id="a54e6-212">Time when alert was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="a54e6-213">2020-09-06T14:46:55.7182276 Z</span><span class="sxs-lookup"><span data-stu-id="a54e6-213">2020-09-06T14:46:55.7182276Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="a54e6-214">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="a54e6-214">lastUpdatedTime</span></span>                           | <span data-ttu-id="a54e6-215">Hora de la última actualización de la alerta en el back-end.</span><span class="sxs-lookup"><span data-stu-id="a54e6-215">Time when alert was last updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="a54e6-216">2020-09-06T14:46:57.2433333 Z</span><span class="sxs-lookup"><span data-stu-id="a54e6-216">2020-09-06T14:46:57.2433333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="a54e6-217">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="a54e6-217">resolvedTime</span></span>                              | <span data-ttu-id="a54e6-218">Hora a la que se resolvió la alerta.</span><span class="sxs-lookup"><span data-stu-id="a54e6-218">Time when alert was resolved.</span></span>                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="a54e6-219">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="a54e6-219">2020-09-10T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="a54e6-220">firstActivity</span><span class="sxs-lookup"><span data-stu-id="a54e6-220">firstActivity</span></span>                             | <span data-ttu-id="a54e6-221">Hora en que la alerta notificó por primera vez que se actualizó la actividad en el back-end.</span><span class="sxs-lookup"><span data-stu-id="a54e6-221">Time when alert first reported that activity was updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="a54e6-222">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="a54e6-222">2020-09-04T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="a54e6-223">title</span><span class="sxs-lookup"><span data-stu-id="a54e6-223">title</span></span>                                     | <span data-ttu-id="a54e6-224">Valor de cadena de identificación breve disponible para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="a54e6-224">Brief identifying string value available for each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="a54e6-225">Actividad de ransomware</span><span class="sxs-lookup"><span data-stu-id="a54e6-225">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="a54e6-226">description</span><span class="sxs-lookup"><span data-stu-id="a54e6-226">description</span></span>                               | <span data-ttu-id="a54e6-227">Valor de cadena que describe cada alerta.</span><span class="sxs-lookup"><span data-stu-id="a54e6-227">String value describing each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="a54e6-228">El usuario de prueba user2 (testUser2@contoso.com) ha manipulado 99 archivos con varias extensiones que finalizan con la extensión no común *herunterladen*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-228">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="a54e6-229">Se trata de un número inusual de manipulaciones de archivos e indica un posible ataque de ransomware.</span><span class="sxs-lookup"><span data-stu-id="a54e6-229">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span> |
| <span data-ttu-id="a54e6-230">categoría</span><span class="sxs-lookup"><span data-stu-id="a54e6-230">category</span></span>                                  | <span data-ttu-id="a54e6-231">Vista visual y numérica de cuánto ha progresado el ataque a lo largo de la cadena de eliminación.</span><span class="sxs-lookup"><span data-stu-id="a54e6-231">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="a54e6-232">Se alinea a la [Mitre de ATT&CK™ Framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="a54e6-232">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span>                                                                                                                                                                                                                           | <span data-ttu-id="a54e6-233">Impacto</span><span class="sxs-lookup"><span data-stu-id="a54e6-233">Impact</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="a54e6-234">status</span><span class="sxs-lookup"><span data-stu-id="a54e6-234">status</span></span>                                    | <span data-ttu-id="a54e6-235">Clasifique las alertas (como *nuevas*, *activas*o *resueltas*).</span><span class="sxs-lookup"><span data-stu-id="a54e6-235">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="a54e6-236">Esto le ayudará a organizar y administrar la respuesta a las alertas.</span><span class="sxs-lookup"><span data-stu-id="a54e6-236">This helps you organize and manage your response to alerts.</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="a54e6-237">Nuevo</span><span class="sxs-lookup"><span data-stu-id="a54e6-237">New</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="a54e6-238">severity</span><span class="sxs-lookup"><span data-stu-id="a54e6-238">severity</span></span>                                  | <span data-ttu-id="a54e6-239">Indica el posible impacto en los activos.</span><span class="sxs-lookup"><span data-stu-id="a54e6-239">Indicates the possible impact on assets.</span></span> <span data-ttu-id="a54e6-240">Cuanto mayor sea la gravedad, mayor será el impacto.</span><span class="sxs-lookup"><span data-stu-id="a54e6-240">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="a54e6-241">Normalmente, los elementos de mayor gravedad requieren la atención más inmediata.</span><span class="sxs-lookup"><span data-stu-id="a54e6-241">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="a54e6-242">Uno de los siguientes valores: *informativo*, *bajo*, \* medio y *alto*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-242">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                   | <span data-ttu-id="a54e6-243">Mediano</span><span class="sxs-lookup"><span data-stu-id="a54e6-243">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="a54e6-244">investigationId</span><span class="sxs-lookup"><span data-stu-id="a54e6-244">investigationId</span></span>                           | <span data-ttu-id="a54e6-245">El identificador de investigación automatizada desencadenada por esta alerta.</span><span class="sxs-lookup"><span data-stu-id="a54e6-245">The automated investigation id triggered by this alert.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="a54e6-246">1234</span><span class="sxs-lookup"><span data-stu-id="a54e6-246">1234</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="a54e6-247">investigationState</span><span class="sxs-lookup"><span data-stu-id="a54e6-247">investigationState</span></span>                        | <span data-ttu-id="a54e6-248">Información sobre el estado actual de la investigación.</span><span class="sxs-lookup"><span data-stu-id="a54e6-248">Information on the investigation's current status.</span></span> <span data-ttu-id="a54e6-249">Uno de los siguientes: *Unknown*, *terminated*, *SuccessfullyRemediated*, *benigno*, *failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *queued*, *InnerFailure*, *PreexistingAlert*, *unsupports*, *UnsupportedAlertType* *, SuppressedAlert.*</span><span class="sxs-lookup"><span data-stu-id="a54e6-249">One of the following: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="a54e6-250">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="a54e6-250">UnsupportedAlertType</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="a54e6-251">classification</span><span class="sxs-lookup"><span data-stu-id="a54e6-251">classification</span></span>                            | <span data-ttu-id="a54e6-252">La especificación del incidente.</span><span class="sxs-lookup"><span data-stu-id="a54e6-252">The specification for the incident.</span></span> <span data-ttu-id="a54e6-253">Los valores de la propiedad son: *Unknown*, *FalsePositive*, *TruePositive* o *null*</span><span class="sxs-lookup"><span data-stu-id="a54e6-253">The property values are: *Unknown*, *FalsePositive*, *TruePositive* or *null*</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="a54e6-254">Unknown</span><span class="sxs-lookup"><span data-stu-id="a54e6-254">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="a54e6-255">cálculo</span><span class="sxs-lookup"><span data-stu-id="a54e6-255">determination</span></span>                             | <span data-ttu-id="a54e6-256">Especifica la determinación del incidente.</span><span class="sxs-lookup"><span data-stu-id="a54e6-256">Specifies the determination of the incident.</span></span> <span data-ttu-id="a54e6-257">Los valores de la propiedad son: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other* o  *null*</span><span class="sxs-lookup"><span data-stu-id="a54e6-257">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="a54e6-258">Apt</span><span class="sxs-lookup"><span data-stu-id="a54e6-258">Apt</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="a54e6-259">assignedTo</span><span class="sxs-lookup"><span data-stu-id="a54e6-259">assignedTo</span></span>                                | <span data-ttu-id="a54e6-260">Propietario del incidente, o *null* si no hay ningún propietario asignado.</span><span class="sxs-lookup"><span data-stu-id="a54e6-260">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                            | <span data-ttu-id="a54e6-261">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a54e6-261">secop2@contoso.com</span></span>                                                                                                                                                                                                 |
| <span data-ttu-id="a54e6-262">actorName</span><span class="sxs-lookup"><span data-stu-id="a54e6-262">actorName</span></span>                                 | <span data-ttu-id="a54e6-263">El grupo de actividad, si lo hubiera, asociado con esta alerta.</span><span class="sxs-lookup"><span data-stu-id="a54e6-263">The activity group, if any, the  associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="a54e6-264">BORO</span><span class="sxs-lookup"><span data-stu-id="a54e6-264">BORON</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="a54e6-265">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="a54e6-265">threatFamilyName</span></span>                          | <span data-ttu-id="a54e6-266">Familia de amenazas asociada a esta alerta.</span><span class="sxs-lookup"><span data-stu-id="a54e6-266">Threat family associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="a54e6-267">nulo</span><span class="sxs-lookup"><span data-stu-id="a54e6-267">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="a54e6-268">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="a54e6-268">mitreTechniques</span></span>                           | <span data-ttu-id="a54e6-269">Las técnicas de ataque, que se alinean con el marco de [Mitre ATT&CK](https://attack.mitre.org/)™.</span><span class="sxs-lookup"><span data-stu-id="a54e6-269">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span>                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="a54e6-270">equipos</span><span class="sxs-lookup"><span data-stu-id="a54e6-270">devices</span></span>                                   | <span data-ttu-id="a54e6-271">Todos los dispositivos en los que se enviaron alertas relacionadas con el incidente.</span><span class="sxs-lookup"><span data-stu-id="a54e6-271">All devices where alerts related to the incident were sent.</span></span>                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="a54e6-272">\[\] (vea los detalles de los campos de entidad a continuación)</span><span class="sxs-lookup"><span data-stu-id="a54e6-272">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="a54e6-273">**Formato de dispositivo**</span><span class="sxs-lookup"><span data-stu-id="a54e6-273">**Device format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="a54e6-274">DeviceId</span><span class="sxs-lookup"><span data-stu-id="a54e6-274">DeviceId</span></span>                                  | <span data-ttu-id="a54e6-275">El identificador del dispositivo tal como se ha designado en ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="a54e6-275">The device ID as designated in Microsoft Defender ATP.</span></span>                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="a54e6-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="a54e6-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="a54e6-277">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="a54e6-277">aadDeviceId</span></span>                               |  <span data-ttu-id="a54e6-278">El identificador de dispositivo tal como se ha designado en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span><span class="sxs-lookup"><span data-stu-id="a54e6-278">The device Id as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span></span> <span data-ttu-id="a54e6-279">Solo está disponible para los dispositivos Unidos a un dominio.</span><span class="sxs-lookup"><span data-stu-id="a54e6-279">Only available for domain-joined devices.</span></span>                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="a54e6-280">nulo</span><span class="sxs-lookup"><span data-stu-id="a54e6-280">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="a54e6-281">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="a54e6-281">deviceDnsName</span></span>                             | <span data-ttu-id="a54e6-282">Nombre de dominio completo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a54e6-282">The fully qualified domain name for the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="a54e6-283">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a54e6-283">user5cx.middleeast.corp.contoso.com</span></span>                                                                                                                                                                                                    |
| <span data-ttu-id="a54e6-284">osPlatform</span><span class="sxs-lookup"><span data-stu-id="a54e6-284">osPlatform</span></span>                                | <span data-ttu-id="a54e6-285">La plataforma de sistema operativo que el dispositivo está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="a54e6-285">The OS platform the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="a54e6-286">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="a54e6-286">WindowsServer2016</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="a54e6-287">osBuild</span><span class="sxs-lookup"><span data-stu-id="a54e6-287">osBuild</span></span>                                   | <span data-ttu-id="a54e6-288">La versión de compilación para el sistema operativo que el dispositivo está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="a54e6-288">The build version for the OS the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="a54e6-289">14393</span><span class="sxs-lookup"><span data-stu-id="a54e6-289">14393</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="a54e6-290">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="a54e6-290">rbacGroupName</span></span>                             | <span data-ttu-id="a54e6-291">El grupo [de control de acceso basado en roles](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) asociado al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a54e6-291">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="a54e6-292">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="a54e6-292">WDATP-Ring0</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="a54e6-293">firstSeen</span><span class="sxs-lookup"><span data-stu-id="a54e6-293">firstSeen</span></span>                                 | <span data-ttu-id="a54e6-294">Hora en que se ha visto el dispositivo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="a54e6-294">Time when device was first seen.</span></span>                                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="a54e6-295">2020-02-06T14:16:01.9330135 Z</span><span class="sxs-lookup"><span data-stu-id="a54e6-295">2020-02-06T14:16:01.9330135Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="a54e6-296">healthStatus</span><span class="sxs-lookup"><span data-stu-id="a54e6-296">healthStatus</span></span>                              | <span data-ttu-id="a54e6-297">El estado de mantenimiento del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a54e6-297">The health state of the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="a54e6-298">Activo</span><span class="sxs-lookup"><span data-stu-id="a54e6-298">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="a54e6-299">riskScore</span><span class="sxs-lookup"><span data-stu-id="a54e6-299">riskScore</span></span>                                 | <span data-ttu-id="a54e6-300">La puntuación de riesgo para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a54e6-300">The risk score for the  device.</span></span>                                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="a54e6-301">Alto</span><span class="sxs-lookup"><span data-stu-id="a54e6-301">High</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="a54e6-302">organismos</span><span class="sxs-lookup"><span data-stu-id="a54e6-302">entities</span></span>                                  | <span data-ttu-id="a54e6-303">Todas las entidades que se han identificado como parte de una alerta determinada o están relacionadas con ella.</span><span class="sxs-lookup"><span data-stu-id="a54e6-303">All entities that have been identified to be part of, or related to, a given alert.</span></span>                                                                                                                                                                                                                                                                                | <span data-ttu-id="a54e6-304">\[\] (vea los detalles de los campos de entidad a continuación)</span><span class="sxs-lookup"><span data-stu-id="a54e6-304">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="a54e6-305">**Formato de la entidad**</span><span class="sxs-lookup"><span data-stu-id="a54e6-305">**Entity Format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="a54e6-306">entityType</span><span class="sxs-lookup"><span data-stu-id="a54e6-306">entityType</span></span>                                | <span data-ttu-id="a54e6-307">Entidades que se han identificado como parte de una alerta determinada o están relacionadas con ella.</span><span class="sxs-lookup"><span data-stu-id="a54e6-307">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="a54e6-308">Los valores de las propiedades son: *usuario*, *IP*, *dirección URL*, *archivo*, *proceso*, *buzón*, *MailMessage*, *MailCluster*, *registro*</span><span class="sxs-lookup"><span data-stu-id="a54e6-308">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="a54e6-309">User</span><span class="sxs-lookup"><span data-stu-id="a54e6-309">User</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="a54e6-310">SHA1</span><span class="sxs-lookup"><span data-stu-id="a54e6-310">sha1</span></span>                                      | <span data-ttu-id="a54e6-311">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-311">Available if entityType is *File*.</span></span><br><span data-ttu-id="a54e6-312">Hash de archivo de alertas asociadas a un archivo o proceso.</span><span class="sxs-lookup"><span data-stu-id="a54e6-312">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="a54e6-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="a54e6-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="a54e6-314">SHA256</span><span class="sxs-lookup"><span data-stu-id="a54e6-314">sha256</span></span>                                    | <span data-ttu-id="a54e6-315">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-315">Available if entityType is *File*.</span></span><br><span data-ttu-id="a54e6-316">Hash de archivo de alertas asociadas a un archivo o proceso.</span><span class="sxs-lookup"><span data-stu-id="a54e6-316">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="a54e6-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="a54e6-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="a54e6-318">fileName</span><span class="sxs-lookup"><span data-stu-id="a54e6-318">fileName</span></span>                                  | <span data-ttu-id="a54e6-319">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-319">Available if entityType is *File*.</span></span><br><span data-ttu-id="a54e6-320">El nombre de archivo de las alertas asociadas a un archivo o proceso</span><span class="sxs-lookup"><span data-stu-id="a54e6-320">The file name for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="a54e6-321">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="a54e6-321">Detector.UnitTests.dll</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="a54e6-322">Rutaarchivo</span><span class="sxs-lookup"><span data-stu-id="a54e6-322">filePath</span></span>                                  | <span data-ttu-id="a54e6-323">Disponible si entityType es *File*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-323">Available if entityType is *File*.</span></span><br><span data-ttu-id="a54e6-324">La ruta de acceso del archivo para las alertas asociadas a un archivo o proceso</span><span class="sxs-lookup"><span data-stu-id="a54e6-324">The file path for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="a54e6-325">C: \\ \\ \\ \\ \_ trabajo \\ \\ \_ del agente Temp \\ \\ deploy \_ sistema 2020-09-06 12 \_ 14 54 de \_ \\ \\ salida</span><span class="sxs-lookup"><span data-stu-id="a54e6-325">C:\\\\Agent\\\\\_work\\\\\_temp\\\\Deploy\_SYSTEM 2020-09-06 12\_14\_54\\\\Out</span></span>                                                                                                                                                                    |
| <span data-ttu-id="a54e6-326">Idproceso</span><span class="sxs-lookup"><span data-stu-id="a54e6-326">processId</span></span>                                 | <span data-ttu-id="a54e6-327">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-327">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="a54e6-328">24348</span><span class="sxs-lookup"><span data-stu-id="a54e6-328">24348</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="a54e6-329">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="a54e6-329">processCommandLine</span></span>                        | <span data-ttu-id="a54e6-330">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-330">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="a54e6-331">" \\ " El archivo está listo para descargar \_1911150169.exe\\ ""</span><span class="sxs-lookup"><span data-stu-id="a54e6-331">"\\"Your File Is Ready To Download\_1911150169.exe\\" "</span></span>                                                                                                                                                                                           |
| <span data-ttu-id="a54e6-332">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="a54e6-332">processCreationTime</span></span>                       | <span data-ttu-id="a54e6-333">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-333">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="a54e6-334">2020-07-18T03:25:38.5269993 Z</span><span class="sxs-lookup"><span data-stu-id="a54e6-334">2020-07-18T03:25:38.5269993Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="a54e6-335">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="a54e6-335">parentProcessId</span></span>                           | <span data-ttu-id="a54e6-336">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-336">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="a54e6-337">16840</span><span class="sxs-lookup"><span data-stu-id="a54e6-337">16840</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="a54e6-338">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="a54e6-338">parentProcessCreationTime</span></span>                 | <span data-ttu-id="a54e6-339">Disponible si entityType es *Process*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-339">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="a54e6-340">2020-07-18T02:12:32.8616797 Z</span><span class="sxs-lookup"><span data-stu-id="a54e6-340">2020-07-18T02:12:32.8616797Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="a54e6-341">ipAddress</span><span class="sxs-lookup"><span data-stu-id="a54e6-341">ipAddress</span></span>                                 | <span data-ttu-id="a54e6-342">Disponible si entityType es *IP*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-342">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="a54e6-343">Dirección IP de alertas asociadas con eventos de red, como *la comunicación a un destino de red malintencionado*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-343">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                   | <span data-ttu-id="a54e6-344">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="a54e6-344">62.216.203.204</span></span>                                                                                                                                                                                                                                    |
| <span data-ttu-id="a54e6-345">URL</span><span class="sxs-lookup"><span data-stu-id="a54e6-345">url</span></span>                                       | <span data-ttu-id="a54e6-346">Disponible si entityType es *URL*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-346">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="a54e6-347">Dirección URL de las alertas asociadas a eventos de red, como *la comunicación a un destino de red malintencionado*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-347">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                  | <span data-ttu-id="a54e6-348">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="a54e6-348">down.esales360.cn</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="a54e6-349">accountName</span><span class="sxs-lookup"><span data-stu-id="a54e6-349">accountName</span></span>                               | <span data-ttu-id="a54e6-350">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-350">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="a54e6-351">testUser2</span><span class="sxs-lookup"><span data-stu-id="a54e6-351">testUser2</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="a54e6-352">domainName</span><span class="sxs-lookup"><span data-stu-id="a54e6-352">domainName</span></span>                                | <span data-ttu-id="a54e6-353">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-353">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="a54e6-354">Europa. Corp. contoso</span><span class="sxs-lookup"><span data-stu-id="a54e6-354">europe.corp.contoso</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="a54e6-355">userSid</span><span class="sxs-lookup"><span data-stu-id="a54e6-355">userSid</span></span>                                   | <span data-ttu-id="a54e6-356">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-356">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="a54e6-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="a54e6-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="a54e6-358">aadUserId</span><span class="sxs-lookup"><span data-stu-id="a54e6-358">aadUserId</span></span>                                 | <span data-ttu-id="a54e6-359">Disponible si entityType es *User*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-359">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="a54e6-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="a54e6-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="a54e6-361">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="a54e6-361">userPrincipalName</span></span>                         | <span data-ttu-id="a54e6-362">Disponible si entityType es *User* / MailMessage de*buzón*de usuario / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-362">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="a54e6-363">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a54e6-363">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="a54e6-364">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="a54e6-364">mailboxDisplayName</span></span>                        | <span data-ttu-id="a54e6-365">Disponible si entityType es *MailBox*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-365">Available if entityType is *MailBox*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="a54e6-366">prueba user2</span><span class="sxs-lookup"><span data-stu-id="a54e6-366">test User2</span></span>                                                                                                                                                                                                                                        |
| <span data-ttu-id="a54e6-367">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="a54e6-367">mailboxAddress</span></span>                            | <span data-ttu-id="a54e6-368">Disponible si entityType es *User* / MailMessage de*buzón*de usuario / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-368">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="a54e6-369">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a54e6-369">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="a54e6-370">clusterBy</span><span class="sxs-lookup"><span data-stu-id="a54e6-370">clusterBy</span></span>                                 | <span data-ttu-id="a54e6-371">Disponible si entityType es  *MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-371">Available if entityType is  *MailCluster*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="a54e6-372">Titular P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="a54e6-372">Subject;P2SenderDomain;ContentType</span></span>                                                                                                                                                                                                                |
| <span data-ttu-id="a54e6-373">remitente</span><span class="sxs-lookup"><span data-stu-id="a54e6-373">sender</span></span>                                    | <span data-ttu-id="a54e6-374">Disponible si entityType es *User* / MailMessage de*buzón*de usuario / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-374">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="a54e6-375">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="a54e6-375">user.abc@mail.contoso.co.in</span></span>                                                                                                                                                                 |
| <span data-ttu-id="a54e6-376">destinatario</span><span class="sxs-lookup"><span data-stu-id="a54e6-376">recipient</span></span>                                 | <span data-ttu-id="a54e6-377">Disponible si entityType es *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-377">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="a54e6-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a54e6-378">testUser2@contoso.com</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="a54e6-379">subject</span><span class="sxs-lookup"><span data-stu-id="a54e6-379">subject</span></span>                                   | <span data-ttu-id="a54e6-380">Disponible si entityType es *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-380">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="a54e6-381">\[\]Atención externa</span><span class="sxs-lookup"><span data-stu-id="a54e6-381">\[EXTERNAL\] Attention</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="a54e6-382">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="a54e6-382">deliveryAction</span></span>                            | <span data-ttu-id="a54e6-383">Disponible si entityType es *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-383">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="a54e6-384">Pronuncia</span><span class="sxs-lookup"><span data-stu-id="a54e6-384">Delivered</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="a54e6-385">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="a54e6-385">securityGroupId</span></span>                           | <span data-ttu-id="a54e6-386">Disponible si entityType es  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-386">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="a54e6-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="a54e6-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="a54e6-388">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="a54e6-388">securityGroupName</span></span>                         | <span data-ttu-id="a54e6-389">Disponible si entityType es  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-389">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="a54e6-390">Operadores de configuración de red</span><span class="sxs-lookup"><span data-stu-id="a54e6-390">Network Configuration Operators</span></span>                                                                                                                                                                                                                   |
| <span data-ttu-id="a54e6-391">registryHive</span><span class="sxs-lookup"><span data-stu-id="a54e6-391">registryHive</span></span>                              | <span data-ttu-id="a54e6-392">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-392">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="a54e6-393">HKEY \_ local \_ Machine</span><span class="sxs-lookup"><span data-stu-id="a54e6-393">HKEY\_LOCAL\_MACHINE</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="a54e6-394">Deleteinstance</span><span class="sxs-lookup"><span data-stu-id="a54e6-394">registryKey</span></span>                               | <span data-ttu-id="a54e6-395">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-395">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="a54e6-396">SOFTWARE \\ \\ Microsoft \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon</span><span class="sxs-lookup"><span data-stu-id="a54e6-396">SOFTWARE\\\\Microsoft\\\\Windows NT\\\\CurrentVersion\\\\Winlogon</span></span>                                                                                                                                                                                 |
| <span data-ttu-id="a54e6-397">registryValueType</span><span class="sxs-lookup"><span data-stu-id="a54e6-397">registryValueType</span></span>                         | <span data-ttu-id="a54e6-398">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-398">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="a54e6-399">Cadena</span><span class="sxs-lookup"><span data-stu-id="a54e6-399">String</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="a54e6-400">Deleteinstance</span><span class="sxs-lookup"><span data-stu-id="a54e6-400">registryValue</span></span>                             | <span data-ttu-id="a54e6-401">Disponible si entityType es  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="a54e6-401">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="a54e6-402">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="a54e6-402">31-00-00-00</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="a54e6-403">deviceId</span><span class="sxs-lookup"><span data-stu-id="a54e6-403">deviceId</span></span>                                  | <span data-ttu-id="a54e6-404">IDENTIFICADOR, si existe, del dispositivo relacionado con la entidad.</span><span class="sxs-lookup"><span data-stu-id="a54e6-404">The ID, if any, of the device related to the entity.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="a54e6-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="a54e6-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>                                                                                                                                                                                                          |



## <a name="example"></a><span data-ttu-id="a54e6-406">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a54e6-406">Example</span></span>

<span data-ttu-id="a54e6-407">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="a54e6-407">**Request**</span></span>

```
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="a54e6-408">**Respuesta**</span><span class="sxs-lookup"><span data-stu-id="a54e6-408">**Response**</span></span>
```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="a54e6-409">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="a54e6-409">Related topic</span></span>
- [<span data-ttu-id="a54e6-410">API de incidentes</span><span class="sxs-lookup"><span data-stu-id="a54e6-410">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="a54e6-411">Actualizar incidente</span><span class="sxs-lookup"><span data-stu-id="a54e6-411">Update incident</span></span>](api-update-incidents.md)