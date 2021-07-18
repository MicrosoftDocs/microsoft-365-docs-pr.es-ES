---
title: Usar Microsoft Teams clases con Blackboard Learn Ultra
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Usar Microsoft Teams clases con Blackboard Learn Ultra
ms.openlocfilehash: a97d5bf56e1e045ccb0ef7cc66ecef7dfba4041a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454643"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a><span data-ttu-id="dcafa-103">Usar Microsoft Teams clases con Blackboard Learn Ultra</span><span class="sxs-lookup"><span data-stu-id="dcafa-103">Use Microsoft Teams classes with Blackboard Learn Ultra</span></span>

<span data-ttu-id="dcafa-104">El trabajo en equipo es el núcleo de todas las organizaciones modernas.</span><span class="sxs-lookup"><span data-stu-id="dcafa-104">Teamwork is at the core of every modern organization.</span></span> <span data-ttu-id="dcafa-105">Al fomentar la colaboración, es una característica definitoria de todas las instituciones exitosas.</span><span class="sxs-lookup"><span data-stu-id="dcafa-105">By fostering collaboration, it’s a defining characteristic of every successful institution.</span></span> <span data-ttu-id="dcafa-106">Puedes mejorar todas las capacidades y características de Blackboard Learn Ultra al emparejarlos con Microsoft Teams clases.</span><span class="sxs-lookup"><span data-stu-id="dcafa-106">You can enhance all the capabilities and features of Blackboard Learn Ultra by pairing them up with Microsoft Teams classes.</span></span>

<span data-ttu-id="dcafa-107">Las clases pueden incluir conversaciones en tiempo real, reuniones de vídeo o interacciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="dcafa-107">Your classes might include real-time conversations, video meetings, or asynchronous interactions.</span></span> <span data-ttu-id="dcafa-108">Puede agregar experiencias de cocreación y uso compartido de archivos para sus alumnos, todo en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="dcafa-108">You can add file sharing and cocreation experiences for your students, all in one place.</span></span> <span data-ttu-id="dcafa-109">Microsoft Teams clases con Learn Ultra redefinen la dinámica de la enseñanza y lo que significa un aprendizaje eficaz.</span><span class="sxs-lookup"><span data-stu-id="dcafa-109">Microsoft Teams classes with Learn Ultra redefine the dynamics of teaching and what effective learning means.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcafa-110">Asegúrese de que ha configurado correctamente el campo Correo electrónico de la institución en el [Sistema de información de estudiantes (SIS)](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student_Information_System/SIS_Planning)</span><span class="sxs-lookup"><span data-stu-id="dcafa-110">Ensure that you have successfully set up the Institution Email field in your [Student Information System (SIS)](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student_Information_System/SIS_Planning)</span></span>
>
><span data-ttu-id="dcafa-111">La integración Microsoft Teams clases de Microsoft Teams se basa en el campo de correo electrónico de la institución del SIS para asignarlo al nombre de principio de usuario [(UPN)](/azure/active-directory/hybrid/howto-troubleshoot-upn-changes)de Microsoft Azure Active Directory (AAD) correcto .</span><span class="sxs-lookup"><span data-stu-id="dcafa-111">The Microsoft Teams classes integration relies on the institution email field in your SIS to map to the correct Microsoft Azure Active Directory’s (AAD) [User Principle Name (UPN)](/azure/active-directory/hybrid/howto-troubleshoot-upn-changes).</span></span> <span data-ttu-id="dcafa-112">Si no se ha aprovisionado ningún correo electrónico de la institución, este valor predeterminado será el correo electrónico existente.</span><span class="sxs-lookup"><span data-stu-id="dcafa-112">If no institution email has been provisioned, this will default to the existing email.</span></span> <span data-ttu-id="dcafa-113">Se recomienda establecer este campo para que todos los usuarios se aseguren de que sus datos se sincronizan correctamente y que no haya conflictos de datos de correo electrónico entre AAD y Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="dcafa-113">It’s recommended that this field be set for every user to ensure their data is synchronized correctly and that there is no conflict of email data between AAD and Blackboard Learn Ultra.</span></span>
>
> <span data-ttu-id="dcafa-114">Si no ha establecido este campo correctamente en la asignación de SIS, la integración seguirá funcionando, pero es posible que los usuarios no aparezcan en las clases Teams creadas y que se produzcan errores.</span><span class="sxs-lookup"><span data-stu-id="dcafa-114">If you haven’t set this field appropriately in your SIS mapping, the integration will continue to work, but users might not appear in the Teams classes created, and errors could occur.</span></span>

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a><span data-ttu-id="dcafa-115">Compatibilidad con la asignación de datos institucionales: campo SIS de correo electrónico de la institución</span><span class="sxs-lookup"><span data-stu-id="dcafa-115">Supporting Institutional Data Mapping – Institution Email SIS Field</span></span>

<span data-ttu-id="dcafa-116">Como parte de la evolución con las integraciones de  proveedores de nube, Blackboard Learn Ultra ha creado un nuevo campo de correo electrónico de la institución, tanto en la integración de Student Information System Framework como en las API públicas de REST, lo que permite a las instituciones administrar el proceso de sincronización de datos de forma eficaz entre Blackboard Learn Ultra y AAD.</span><span class="sxs-lookup"><span data-stu-id="dcafa-116">As part of the evolution with Cloud provider integrations, Blackboard Learn Ultra has created a new **Institution Email** field, in both the Student Information System Framework integration and public REST APIs, allowing institutions to manage the data synchronization process effectively between Blackboard Learn Ultra and AAD.</span></span>

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a><span data-ttu-id="dcafa-117">¿Qué significa el correo electrónico de la institución y qué admite?</span><span class="sxs-lookup"><span data-stu-id="dcafa-117">What does the Institution Email mean and what does it support?</span></span>

<span data-ttu-id="dcafa-118">El **campo Correo electrónico de** la institución permite asignaciones de campos personalizadas entre los orígenes de datos admitidos externamente de un cliente y Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="dcafa-118">The **Institution Email** field allows customized field mappings between a client’s externally supported data sources and Blackboard Learn Ultra.</span></span> <span data-ttu-id="dcafa-119">Si los orígenes de datos son proveedores de nube, como Microsoft, el nombre de principio de usuario (UPN) es un identificador único principal para cada usuario que consta de un prefijo UPN (nombre de cuenta del usuario) y un sufijo UPN (un nombre de dominio DNS) unidos con un símbolo @.</span><span class="sxs-lookup"><span data-stu-id="dcafa-119">If data sources are cloud providers, such as Microsoft, the User Principle Name (UPN) is a primary unique identifier for each user consisting of a UPN prefix (the user’s account name) and a UPN suffix (a DNS domain name) joined together with an @ symbol.</span></span> <span data-ttu-id="dcafa-120">Esto crea una dirección de correo electrónico única para cada usuario específico dentro del Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dcafa-120">This creates a unique email address for each specific user within the Microsoft Azure Active Directory.</span></span>

<span data-ttu-id="dcafa-121">Para asegurarse de que los datos son precisos y de que las inscripciones o pertenencias entre las clases Desinscripción Ultra y Microsoft Teams de Blackboard se logran correctamente, la dirección de correo electrónico de un usuario debe coincidir entre ambos sistemas.</span><span class="sxs-lookup"><span data-stu-id="dcafa-121">To ensure data is accurate and enrollments or memberships between Blackboard Learn Ultra and Microsoft Teams classes are correctly achieved, a user’s email address must match between both systems.</span></span> <span data-ttu-id="dcafa-122">En Blackboard Learn Ultra, los usuarios pueden cambiar o invalidar su dirección de correo electrónico existente en la interfaz de usuario, lo que podría provocar errores de sincronización y que el usuario no se agregara correctamente a un equipo de clase.</span><span class="sxs-lookup"><span data-stu-id="dcafa-122">In Blackboard Learn Ultra, users can change or override their existing email address in the user interface, which could result in sync errors occurring and the user not being correctly added to a Class Team.</span></span> <span data-ttu-id="dcafa-123">La **asignación** del campo Correo electrónico de la institución garantiza que este nivel de comprobación de seguridad y validación se pueda administrar correctamente, independientemente de si los usuarios han cambiado su correo electrónico dentro de Blackboard Learn Ultra o no.</span><span class="sxs-lookup"><span data-stu-id="dcafa-123">The **Institution Email** field mapping ensures this level of security and validation checking can be correctly managed, regardless if users have changed their email within Blackboard Learn Ultra or not.</span></span>

 <span data-ttu-id="dcafa-124">Cuando dos direcciones de correo electrónico son diferentes:</span><span class="sxs-lookup"><span data-stu-id="dcafa-124">When two email addresses are different, either:</span></span>

- <span data-ttu-id="dcafa-125">Se debe tomar una decisión sobre qué origen tiene prioridad y se tomarán como correos electrónicos de persona e institución.</span><span class="sxs-lookup"><span data-stu-id="dcafa-125">A decision must be made as to which source has precedence and will be taken as both the Person and Institution Emails.</span></span>
  <span data-ttu-id="dcafa-126">O</span><span class="sxs-lookup"><span data-stu-id="dcafa-126">Or</span></span>
- <span data-ttu-id="dcafa-127">Una institución puede establecer una asignación de campo personalizada en su correo electrónico de la institución, que puede resolver un posible conflicto.</span><span class="sxs-lookup"><span data-stu-id="dcafa-127">An institution can set a custom field mapping in its Institution Email, which can resolve a potential conflict.</span></span>

<span data-ttu-id="dcafa-128">La **asignación de campo** De correo electrónico de la institución ya está disponible para todos los tipos de integración de SIS existentes en Configuración avanzada **Configuración**  >  **usuarios aprendan asignación de** campo de tipo de  >  **objeto**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-128">The **Institution Email** field mapping is now available for all existing SIS integration types at **Advanced Configuration Settings** > **Users Learn Object Type** > **Field Mapping**.</span></span>

> [!NOTE]
> <span data-ttu-id="dcafa-129">Es importante tener en cuenta que,  de forma predeterminada, el correo electrónico de la institución se establece en el correo electrónico de persona para todos los formatos de SIS y debe ser único para cada persona. </span><span class="sxs-lookup"><span data-stu-id="dcafa-129">It’s important to note that, by default, the **Institution Email** is set to the **Person Email** for all SIS formats and must be unique for each person.</span></span> <span data-ttu-id="dcafa-130">Todas las integraciones existentes que estén configuradas y en ejecución tendrán esta asignación de datos en su lugar, ya que SIS no podrá importar usuarios si su correo electrónico está duplicado.</span><span class="sxs-lookup"><span data-stu-id="dcafa-130">All existing integrations that are set up and running will have this data mapping in place, as SIS will fail to import users if their email is duplicated.</span></span> <span data-ttu-id="dcafa-131">Si una institución requiere la capacidad de cambiar el correo electrónico de la institución a **personalizado,** tendrá que administrarlo a través de la configuración avanzada **Configuración** en el SIS.</span><span class="sxs-lookup"><span data-stu-id="dcafa-131">If an institution requires the ability to change the Institution Email to **custom**, they'll need to manage this through the **Advanced Configuration Settings** in the SIS.</span></span>

## <a name="requirements"></a><span data-ttu-id="dcafa-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dcafa-132">Requirements</span></span>

<span data-ttu-id="dcafa-133">La integración Microsoft Teams clases de curso está disponible solo para los cursos **de vista de curso ultra.**</span><span class="sxs-lookup"><span data-stu-id="dcafa-133">The Microsoft Teams classes integration is available for **Ultra Course View courses only**.</span></span> <span data-ttu-id="dcafa-134">La institución debe completar estos requisitos para usarlo:</span><span class="sxs-lookup"><span data-stu-id="dcafa-134">Your institution needs to complete these requirements to use it:</span></span>

- <span data-ttu-id="dcafa-135">Tener Habilitado El SaaS de Aprendizaje Ultra de Blackboard con navegación ultra base</span><span class="sxs-lookup"><span data-stu-id="dcafa-135">Have Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span></span>

  ![un ejemplo de la característica está habilitado en los cursos](media/feature-availability.png)

- <span data-ttu-id="dcafa-137">Habilitar LTI para su uso en cursos.</span><span class="sxs-lookup"><span data-stu-id="dcafa-137">Enable LTI for use in courses.</span></span>

  <span data-ttu-id="dcafa-138">a.</span><span class="sxs-lookup"><span data-stu-id="dcafa-138">a.</span></span> <span data-ttu-id="dcafa-139">Vaya al **Panel de administrador**  >  **LTI Tool Providers** Manage Global  >  **Properties**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-139">Go to the **Administrator Panel** > **LTI Tool Providers** > **Manage Global Properties**.</span></span>

  <span data-ttu-id="dcafa-140">b.</span><span class="sxs-lookup"><span data-stu-id="dcafa-140">b.</span></span> <span data-ttu-id="dcafa-141">Seleccione **LTI habilitado en cursos y,** opcionalmente, seleccione **Habilitado en organizaciones**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-141">Select **LTI Enabled in Courses**, and optionally, select **Enabled in Organizations**.</span></span>

  <span data-ttu-id="dcafa-142">c.</span><span class="sxs-lookup"><span data-stu-id="dcafa-142">c.</span></span> <span data-ttu-id="dcafa-143">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-143">Select **Submit**.</span></span>

- <span data-ttu-id="dcafa-144">Debe haber configurado LTI</span><span class="sxs-lookup"><span data-stu-id="dcafa-144">Must have LTI configured</span></span>

- <span data-ttu-id="dcafa-145">Agregar integración de LTI Teams Clases de Aprendizaje de Blackboard</span><span class="sxs-lookup"><span data-stu-id="dcafa-145">Add Blackboard Learn Ultra Teams Classes LTI Integration</span></span>

- <span data-ttu-id="dcafa-146">Agregar Microsoft Teams clases de complemento LTI 1.3 Tool</span><span class="sxs-lookup"><span data-stu-id="dcafa-146">Add Microsoft Teams Classes LTI 1.3 Tool</span></span>

- <span data-ttu-id="dcafa-147">Agregar la herramienta api de REST y el uso compartido de recursos entre orígenes</span><span class="sxs-lookup"><span data-stu-id="dcafa-147">Add the REST API Tool and Cross-Origin Resource Sharing</span></span>

- <span data-ttu-id="dcafa-148">Configurar y aprobar clases Microsoft Teams integración</span><span class="sxs-lookup"><span data-stu-id="dcafa-148">Configure and approve Microsoft Teams classes Integration</span></span>

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a><span data-ttu-id="dcafa-149">Agregar la herramienta LTI 1.3 Teams Clases de aprendizaje ultra de Blackboard Learn</span><span class="sxs-lookup"><span data-stu-id="dcafa-149">Add the Blackboard Learn Ultra Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="dcafa-150">En el **Panel de administrador,** seleccione **Proveedores de herramientas LTI**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-150">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="dcafa-151">Seleccione **Registrar herramienta LTI 1.3**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-151">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="dcafa-152">En el **campo Id.** de cliente, escriba o copie y pegue este identificador:</span><span class="sxs-lookup"><span data-stu-id="dcafa-152">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="dcafa-153">Revise todas las opciones de configuración que se han rellenado previamente y en **Estado de** la herramienta y, a continuación, seleccione **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-153">Review all settings that have been pre-populated and in **Tool Status**, and then select **Enabled**.</span></span>

5. <span data-ttu-id="dcafa-154">En **Directivas de entidad**, seleccione Rol en Curso, Nombre y Dirección de correo **electrónico** **y,** a continuación, **seleccione Sí** para ambos.</span><span class="sxs-lookup"><span data-stu-id="dcafa-154">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**, and then select **Yes** for both.</span></span>

6. <span data-ttu-id="dcafa-155">Seleccione **Permitir acceso al servicio de calidad** y Permitir acceso al servicio de **pertenencia.**</span><span class="sxs-lookup"><span data-stu-id="dcafa-155">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a><span data-ttu-id="dcafa-156">Agregar la herramienta Microsoft Teams clases de trabajo LTI 1.3</span><span class="sxs-lookup"><span data-stu-id="dcafa-156">Add the Microsoft Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="dcafa-157">En el **Panel de administrador,** seleccione **Proveedores de herramientas LTI**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-157">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="dcafa-158">Seleccione **Registrar herramienta LTI 1.3**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-158">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="dcafa-159">En el **campo Id.** de cliente, escriba o copie y pegue este identificador:</span><span class="sxs-lookup"><span data-stu-id="dcafa-159">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. <span data-ttu-id="dcafa-160">Revise todas las configuraciones que se han rellenado previamente y en *Estado de la* herramienta y seleccione *Habilitado.*</span><span class="sxs-lookup"><span data-stu-id="dcafa-160">Review all settings that have been pre-populated and in *Tool Status* and select *Enabled.*</span></span>

5. <span data-ttu-id="dcafa-161">En **Directivas de la** institución, seleccione Rol en **Curso, Nombre y** Dirección de correo **electrónico**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-161">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**.</span></span> <span data-ttu-id="dcafa-162">Seleccione **Sí** para ambos.</span><span class="sxs-lookup"><span data-stu-id="dcafa-162">Select **Yes** for both.</span></span>

6. <span data-ttu-id="dcafa-163">Seleccione **Permitir acceso al servicio de calidad** y Permitir acceso al servicio de **pertenencia.**</span><span class="sxs-lookup"><span data-stu-id="dcafa-163">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-rest-api-tool"></a><span data-ttu-id="dcafa-164">Agregar la herramienta API de REST</span><span class="sxs-lookup"><span data-stu-id="dcafa-164">Add the REST API tool</span></span>

1. <span data-ttu-id="dcafa-165">En el **Panel de administrador,** vaya a **Integraciones** y seleccione **Integraciones de la API de Rest**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-165">From the **Administrator Panel**, navigate to **Integrations** and select **Rest API Integrations**.</span></span>

2. <span data-ttu-id="dcafa-166">Seleccione **Crear integración**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-166">Select **Create Integration**.</span></span>

3. <span data-ttu-id="dcafa-167">En el **campo Id. de** aplicación, escriba o copie y pegue este identificador:</span><span class="sxs-lookup"><span data-stu-id="dcafa-167">In the **Application ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="dcafa-168">Escriba un usuario para esta integración.</span><span class="sxs-lookup"><span data-stu-id="dcafa-168">Type a user for this integration.</span></span>

   <span data-ttu-id="dcafa-169">Este usuario será el que tenga acceso a la API principal desde la que está asociada la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dcafa-169">This user will be the one with home API access from which the application is associated.</span></span>

5. <span data-ttu-id="dcafa-170">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-170">Select **Submit**.</span></span>

## <a name="add-the-cross-origin-resource-sharing"></a><span data-ttu-id="dcafa-171">Agregar el uso compartido de recursos entre orígenes</span><span class="sxs-lookup"><span data-stu-id="dcafa-171">Add the Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="dcafa-172">En el **panel Administrador,** vaya a **Integraciones** y seleccione \* Uso compartido de *recursos entre orígenes*.</span><span class="sxs-lookup"><span data-stu-id="dcafa-172">From the **Administrator panel**, navigate to **Integrations** and select \**Cross-origin Resource Sharing*.</span></span>

2. <span data-ttu-id="dcafa-173">Seleccione **Crear configuración**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-173">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="dcafa-174">En el **campo Origen,** escriba copiar y pegar esta dirección URL:</span><span class="sxs-lookup"><span data-stu-id="dcafa-174">In the **Origin** field, type of copy and paste this URL:</span></span>

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. <span data-ttu-id="dcafa-175">En el **campo Encabezados permitidos,** escriba **Autorización**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-175">In the **Allowed Headers** field, type **Authorization**.</span></span>

5. <span data-ttu-id="dcafa-176">Establezca **Disponible** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-176">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="dcafa-177">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-177">Select **Submit**.</span></span>

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a><span data-ttu-id="dcafa-178">Configurar y aprobar clases Microsoft Teams integración</span><span class="sxs-lookup"><span data-stu-id="dcafa-178">Configure and Approve Microsoft Teams classes Integration</span></span>

<span data-ttu-id="dcafa-179">Para integrar correctamente la instancia de Blackboard Learn Ultra con las clases Microsoft Teams, deberá asegurarse de que la aplicación Descúes de Blackboard Learn Ultra esté aprobada para el acceso en el espacio empresarial Microsoft Azure usuario.</span><span class="sxs-lookup"><span data-stu-id="dcafa-179">To successfully integrate your Blackboard Learn Ultra instance with Microsoft Teams classes, you'll need to make sure the Blackboard Learn Ultra application is approved for access within your Microsoft Azure tenant.</span></span> <span data-ttu-id="dcafa-180">Este es un proceso que deberá completar el administrador global Microsoft 365 la entidad.</span><span class="sxs-lookup"><span data-stu-id="dcafa-180">This is a process that will need to be completed by your institution’s Microsoft 365 Global Admin.</span></span>

<span data-ttu-id="dcafa-181">Este proceso se puede realizar antes o después de configurar las aplicaciones LTI en la instancia ultra de Blackboard Learn.</span><span class="sxs-lookup"><span data-stu-id="dcafa-181">This process can be done either before or after you have configured the LTI applications in your Blackboard Learn Ultra Instance.</span></span>

### <a name="before-configuring-the-lti-applications"></a><span data-ttu-id="dcafa-182">Antes de configurar las aplicaciones LTI</span><span class="sxs-lookup"><span data-stu-id="dcafa-182">Before Configuring the LTI Applications</span></span>

<span data-ttu-id="dcafa-183">Si decide aprobar la aplicación Azure de Clases de Aprendizaje ultra Teams de Blackboard Learn antes de configurar las integraciones de LTI, deberá redirigir al extremo de consentimiento de administrador de la plataforma de identidades de **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-183">If you choose to approve the Blackboard Learn Ultra Teams Classes Azure app before configuring the LTI integrations, you'll need to redirect to the **Microsoft Identity Platform Admin Consent Endpoint**.</span></span> <span data-ttu-id="dcafa-184">Se muestra la dirección URL:</span><span class="sxs-lookup"><span data-stu-id="dcafa-184">The URL is shown:</span></span>

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> <span data-ttu-id="dcafa-185">Reemplazará **{Tenant}** por su identificador de inquilino Microsoft Azure institucional específico.</span><span class="sxs-lookup"><span data-stu-id="dcafa-185">You’ll replace **{Tenant}** with your specific institutional Microsoft Azure tenant ID.</span></span>

<span data-ttu-id="dcafa-186">Verá una ventana de permisos que explica que está dando permiso a Blackboard Learn Ultra para obtener acceso a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dcafa-186">You'll see a permissions window that explains you're giving permission to Blackboard Learn Ultra to access Microsoft Teams.</span></span>

![la ventana de permisos para Microsoft y Blackboard](media/permissions1.png)

### <a name="after-configuring-the-lti-applications"></a><span data-ttu-id="dcafa-188">Después de configurar las aplicaciones LTI</span><span class="sxs-lookup"><span data-stu-id="dcafa-188">After Configuring the LTI Applications</span></span>

1. <span data-ttu-id="dcafa-189">En el **Panel de administrador,** vaya **a Herramientas y** utilidades y seleccione Microsoft Teams Administrador de **integración.**</span><span class="sxs-lookup"><span data-stu-id="dcafa-189">On the **Administrator Panel**, navigate to **Tools and Utilities** and select **Microsoft Teams Integration Admin**.</span></span>

2. <span data-ttu-id="dcafa-190">Seleccione **Habilitar Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-190">Select **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="dcafa-191">Agregue el **identificador de inquilino de Microsoft** al campo de texto disponible.</span><span class="sxs-lookup"><span data-stu-id="dcafa-191">Add your **Microsoft Tenant ID** into the available text field.</span></span>

4. <span data-ttu-id="dcafa-192">Elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="dcafa-192">Choose one of the following options:</span></span>

   - <span data-ttu-id="dcafa-193">Si la aplicación tiene el consentimiento previo, mostrará una pequeña marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="dcafa-193">If the app has pre-consent, it will show a small checkmark.</span></span> <span data-ttu-id="dcafa-194">Si aparece la marca de verificación, seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-194">If the checkmark appears, select **Submit**.</span></span>

   - <span data-ttu-id="dcafa-195">Si no se ha aprobado el consentimiento, siga los pasos descritos para generar la dirección URL para el consentimiento y enviarla al administrador global Microsoft 365 para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="dcafa-195">If consent hasn’t been approved, follow the steps described to generate the URL for consent and send it to the Microsoft 365 Global Admin for approval.</span></span>

5. <span data-ttu-id="dcafa-196">Una vez que haya confirmado la aprobación, seleccione **Reintentar** para confirmar y, a continuación, **seleccione Enviar**.</span><span class="sxs-lookup"><span data-stu-id="dcafa-196">Once you've confirmation of approval, select **Retry** to confirm, and then select **Submit**.</span></span>

   ![Cuadro de diálogo que indica que el acceso se ha bloqueado](media/blocked-access.png)