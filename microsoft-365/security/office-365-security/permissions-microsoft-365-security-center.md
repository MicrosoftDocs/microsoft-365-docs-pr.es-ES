---
title: Permisos en el Centro de seguridad de Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Los administradores pueden aprender a administrar los permisos en el Centro de seguridad de Microsoft 365 para todas las tareas relacionadas con la seguridad.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c2d28510c25290921084e6a238fa8c781c35624
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772578"
---
# <a name="permissions-in-the-microsoft-365-security-center"></a><span data-ttu-id="7f628-103">Permisos en el Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7f628-103">Permissions in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7f628-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="7f628-104">**Applies to**</span></span>
- [<span data-ttu-id="7f628-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7f628-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7f628-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7f628-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7f628-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f628-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="7f628-108">Necesita administrar escenarios de seguridad que abarcan todos los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f628-108">You need to manage security scenarios that span all the Microsoft 365 services.</span></span> <span data-ttu-id="7f628-109">Y necesita la flexibilidad para dar los permisos de administrador adecuados a las personas adecuadas en su organización.</span><span class="sxs-lookup"><span data-stu-id="7f628-109">And you need the flexibility to give the right admin permissions to the right people in your organization.</span></span>

<span data-ttu-id="7f628-110">El Centro de seguridad de Microsoft 365 en <https://security.microsoft.com> admite la administración directa de permisos para los usuarios que realizan tareas de seguridad en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f628-110">The Microsoft 365 security center at <https://security.microsoft.com> supports directly managing permissions for users who perform security tasks in Microsoft 365.</span></span> <span data-ttu-id="7f628-111">Al usar el centro de seguridad para administrar los permisos, puede administrar los permisos de forma centralizada para todas las tareas relacionadas con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="7f628-111">By using the security center to manage permissions, you can manage permissions centrally for all tasks related to security.</span></span>

<span data-ttu-id="7f628-112">Para administrar permisos en el centro de seguridad, vaya a **Permisos y roles** o <https://security.microsoft.com/securitypermissions>.</span><span class="sxs-lookup"><span data-stu-id="7f628-112">To manage permissions in the security center, go to **Permissions & roles** or <https://security.microsoft.com/securitypermissions>.</span></span> <span data-ttu-id="7f628-113">Debe ser **administrador global** o un miembro del grupo de roles de **Administración de la organización** en el centro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7f628-113">You need to be a **global administrator** or a member of the **Organization Management** role group in the security center.</span></span> <span data-ttu-id="7f628-114">En concreto, el rol de **Administración de roles** permite a los usuarios ver, crear y modificar grupos de roles en el centro de seguridad y, de forma predeterminada, ese rol solo se asigna al grupo de roles **Administración de la organización**.</span><span class="sxs-lookup"><span data-stu-id="7f628-114">Specifically, the **Role Management** role allows users to view, create, and modify role groups in the security center, and by default, that role is assigned only to the **Organization Management** role group.</span></span>

## <a name="relationship-of-members-roles-and-role-groups"></a><span data-ttu-id="7f628-115">Relación de los miembros, los roles y los grupos de roles</span><span class="sxs-lookup"><span data-stu-id="7f628-115">Relationship of members, roles, and role groups</span></span>

<span data-ttu-id="7f628-116">Los permisos en el centro de seguridad se basan en el modelo de permisos de control de acceso basado en roles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="7f628-116">Permissions in the security center are based on the role-based access control (RBAC) permissions model.</span></span> <span data-ttu-id="7f628-117">RBAC es el mismo modelo de permisos que se usa en la mayoría de los servicios de Microsoft 365, por lo que si está familiarizado con la estructura de permisos de estos servicios, le resultará sencillo conceder permisos en el centro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7f628-117">RBAC is the same permissions model that's used by most Microsoft 365 services, so if you're familiar with the permission structure in these services, granting permissions in the security center will be very familiar.</span></span>

<span data-ttu-id="7f628-118">Un **rol** concede permisos para realizar un conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="7f628-118">A **role** grants the permissions to do a set of tasks.</span></span>

<span data-ttu-id="7f628-119">Un **grupo de roles** es un conjunto de roles que permite a las personas hacer su trabajo en el centro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7f628-119">A **role group** is a set of roles that lets people do their jobs in the security center.</span></span> <span data-ttu-id="7f628-120">Por ejemplo, el grupo de roles Administradores de simulador de ataques incluye el rol de Administrador de simulador de ataques para crear y administrar todos los aspectos del aprendizaje de simulación de ataques.</span><span class="sxs-lookup"><span data-stu-id="7f628-120">For example, the Attack Simulator Administrators role group includes the Attack Simulator Admin role to create and manage all aspects of attack simulation training.</span></span>

<span data-ttu-id="7f628-121">El centro de seguridad incluye grupos de roles predeterminados para las tareas y funciones más comunes que debe asignar.</span><span class="sxs-lookup"><span data-stu-id="7f628-121">The security center includes default role groups for the most common tasks and functions that you'll need to assign.</span></span> <span data-ttu-id="7f628-122">Por lo general, le recomendamos que simplemente agregue usuarios individuales como **miembros** a los grupos de roles predeterminados.</span><span class="sxs-lookup"><span data-stu-id="7f628-122">Generally, we recommend simply adding individual users as **members** to the default role groups.</span></span>

![Diagrama que muestra la relación de los grupos de roles con los roles y miembros](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="roles-and-role-groups-in-the-security-center"></a><span data-ttu-id="7f628-124">Roles y grupos de roles en el centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="7f628-124">Roles and role groups in the security center</span></span>

<span data-ttu-id="7f628-125">Los siguientes tipos de roles y grupos de roles están disponibles en **Permisos y roles** en el centro de seguridad:</span><span class="sxs-lookup"><span data-stu-id="7f628-125">The following types of roles and role groups are available in **Permissions & roles** in the security center:</span></span>

- <span data-ttu-id="7f628-126">**Roles de Azure AD**: puede ver los roles y los usuarios asignados, pero no puede administrarlos directamente en el centro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7f628-126">**Azure AD roles**: You can view the roles and assigned users, but you can't manage them directly in the security center.</span></span> <span data-ttu-id="7f628-127">Los roles de Azure AD son roles centrales que asignan permisos para **todos** los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f628-127">Azure AD roles are central roles that assign permissions for **all** Microsoft 365 services.</span></span>

- <span data-ttu-id="7f628-128">**Roles de colaboración y correo electrónico**: son los mismos grupos de roles que están disponibles en el Centro de seguridad y cumplimiento, pero puede administrarlos directamente en el centro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7f628-128">**Email & collaboration roles**: These are the same role groups that are available in the Security & Compliance Center, but you can manage them directly in the security center.</span></span> <span data-ttu-id="7f628-129">Los permisos que asigna aquí son específicos del Centro de seguridad de Microsoft 365, el Centro de cumplimiento de Microsoft 365 y el Centro de seguridad y cumplimiento, y no cubren todos los permisos necesarios en otras cargas de trabajo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f628-129">The permissions that you assign here are specific to the Microsoft 365 security center, the Microsoft 365 compliance center, and the Security & Compliance Center, and don't cover all of the permissions that are needed in other Microsoft 365 workloads.</span></span>

![Página Permisos y roles en el Centro de seguridad de Microsoft 365](../../media/m365-sc-permissions-and-roles-page.png)

### <a name="azure-ad-roles-in-the-security-center"></a><span data-ttu-id="7f628-131">Roles de Azure AD en el centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="7f628-131">Azure AD roles in the security center</span></span>

<span data-ttu-id="7f628-132">Si va a **Roles de colaboración y correo electrónico** \> **Permisos y roles** \> **Roles de Azure AD** \> **Roles** (o directamente a <https://security.microsoft.com/aadpermissions>) verá los roles de Azure AD que se describen en esta sección.</span><span class="sxs-lookup"><span data-stu-id="7f628-132">When you go **Email & collaboration roles** \> **Permissions & roles** \> **Azure AD roles** \> **Roles** (or directly to <https://security.microsoft.com/aadpermissions>) you'll see the Azure AD roles that are described in this section.</span></span>

<span data-ttu-id="7f628-133">Al seleccionar un rol, se muestra un desplegable con detalles que contiene la descripción del rol y las asignaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="7f628-133">When you select a role, a details flyout that contains the description of the role and the user assignments appears.</span></span> <span data-ttu-id="7f628-134">Para administrar esas asignaciones, debe hacer clic en **Administrar miembros en Azure AD** en el desplegable de detalles.</span><span class="sxs-lookup"><span data-stu-id="7f628-134">But to manage those assignments, you need to click **Manage members in Azure AD** in the details flyout.</span></span>

![Vínculo a administrar permisos en Azure Active Directory](../../media/permissions-manage-in-azure-ad-link.png)

<span data-ttu-id="7f628-136">Para más información, consulte [Visualización y asignación de roles de administrador en Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="7f628-136">For more information, see [View and assign administrator roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<br>

****

|<span data-ttu-id="7f628-137">Función</span><span class="sxs-lookup"><span data-stu-id="7f628-137">Role</span></span>|<span data-ttu-id="7f628-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f628-138">Description</span></span>|
|---|---|
|<span data-ttu-id="7f628-139">**Administrador global**</span><span class="sxs-lookup"><span data-stu-id="7f628-139">**Global administrator**</span></span>|<span data-ttu-id="7f628-140">Acceso a todas las características administrativas en todos los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f628-140">Access to all administrative features in all Microsoft 365 services.</span></span> <span data-ttu-id="7f628-141">Los administradores globales son los únicos que pueden asignar otros roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="7f628-141">Only global administrators can assign other administrator roles.</span></span> <span data-ttu-id="7f628-142">Para más información, consulte [Administrador global / Administrador de empresa](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).</span><span class="sxs-lookup"><span data-stu-id="7f628-142">For more information, see [Global Administrator / Company Administrator](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).</span></span>|
|<span data-ttu-id="7f628-143">**Administrador de datos de cumplimiento**</span><span class="sxs-lookup"><span data-stu-id="7f628-143">**Compliance data administrator**</span></span>|<span data-ttu-id="7f628-144">Realizar un seguimiento de los datos de su organización a través de Microsoft 365, asegurarse de que están protegidos y obtener información sobre los problemas para ayudar a reducir los riesgos.</span><span class="sxs-lookup"><span data-stu-id="7f628-144">Keep track of your organization's data across Microsoft 365, make sure it's protected, and get insights into any issues to help mitigate risks.</span></span> <span data-ttu-id="7f628-145">Para obtener más información, consulte [Administrador de datos de cumplimiento](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).</span><span class="sxs-lookup"><span data-stu-id="7f628-145">For more information, see [Compliance Data Administrator](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).</span></span>|
|<span data-ttu-id="7f628-146">**Administrador de cumplimiento**</span><span class="sxs-lookup"><span data-stu-id="7f628-146">**Compliance administrator**</span></span>|<span data-ttu-id="7f628-147">Ayudar a que su organización cumpla con los requisitos normativos, administrar casos de eDiscovery y mantener directivas de gobierno de datos en todas las ubicaciones, identidades y aplicaciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f628-147">Help your organization stay compliant with any regulatory requirements, manage eDiscovery cases, and maintain data governance policies across Microsoft 365 locations, identities, and apps.</span></span> <span data-ttu-id="7f628-148">Para obtener más información, consulte [Administrador de cumplimiento](/azure/active-directory/roles/permissions-reference#compliance-administrator).</span><span class="sxs-lookup"><span data-stu-id="7f628-148">For more information, see [Compliance Administrator](/azure/active-directory/roles/permissions-reference#compliance-administrator).</span></span>|
|<span data-ttu-id="7f628-149">**Operador de seguridad**</span><span class="sxs-lookup"><span data-stu-id="7f628-149">**Security operator**</span></span>|<span data-ttu-id="7f628-150">Ver, investigar y responder a las amenazas activas a usuarios, dispositivos y contenido de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f628-150">View, investigate, and respond to active threats to your Microsoft 365 users, devices, and content.</span></span> <span data-ttu-id="7f628-151">Para obtener más información, vea [Operador de seguridad de seguridad](/azure/active-directory/roles/permissions-reference#security-operator).</span><span class="sxs-lookup"><span data-stu-id="7f628-151">For more information, see [Security Operator](/azure/active-directory/roles/permissions-reference#security-operator).</span></span>|
|<span data-ttu-id="7f628-152">**Lector de seguridad**</span><span class="sxs-lookup"><span data-stu-id="7f628-152">**Security reader**</span></span>|<span data-ttu-id="7f628-153">Ver e investigar amenazas activas a usuarios, dispositivos y contenido de Microsoft 365, pero, a diferencia del operador de seguridad, no tienen permisos para responder realizando una acción.</span><span class="sxs-lookup"><span data-stu-id="7f628-153">View and investigate active threats to your Microsoft 365 users, devices, and content, but (unlike the Security operator) they do not have permissions to respond by taking action.</span></span> <span data-ttu-id="7f628-154">Para obtener más información, vea [Lector de seguridad](/azure/active-directory/roles/permissions-reference#security-reader).</span><span class="sxs-lookup"><span data-stu-id="7f628-154">For more information, see [Security Reader](/azure/active-directory/roles/permissions-reference#security-reader).</span></span>|
|<span data-ttu-id="7f628-155">**Administrador de seguridad**</span><span class="sxs-lookup"><span data-stu-id="7f628-155">**Security administrator**</span></span>|<span data-ttu-id="7f628-156">Controlar la seguridad global de la organización mediante la administración de directivas de seguridad, la revisión de análisis de seguridad y los informes en los productos de Microsoft 365, así como mantenerse al día con el panorama de amenazas.</span><span class="sxs-lookup"><span data-stu-id="7f628-156">Control your organization's overall security by managing security policies, reviewing security analytics and reports across Microsoft 365 products, and staying up-to-speed on the threat landscape.</span></span> <span data-ttu-id="7f628-157">Para obtener más información, vea [Administrador de seguridad](/azure/active-directory/roles/permissions-reference#security-administrator).</span><span class="sxs-lookup"><span data-stu-id="7f628-157">For more information, see [Security Administrator](/azure/active-directory/roles/permissions-reference#security-administrator).</span></span>|
|<span data-ttu-id="7f628-158">**Lector global**</span><span class="sxs-lookup"><span data-stu-id="7f628-158">**Global reader**</span></span>|<span data-ttu-id="7f628-159">La versión de solo lectura del rol de **Administrador global**.</span><span class="sxs-lookup"><span data-stu-id="7f628-159">The read-only version of the **Global administrator** role.</span></span> <span data-ttu-id="7f628-160">Ver todas las configuraciones e información administrativa en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f628-160">View all settings and administrative information across Microsoft 365.</span></span> <span data-ttu-id="7f628-161">Para más información, vea [Lector global](/azure/active-directory/roles/permissions-reference#global-reader).</span><span class="sxs-lookup"><span data-stu-id="7f628-161">For more information, see [Global Reader](/azure/active-directory/roles/permissions-reference#global-reader).</span></span>|
|<span data-ttu-id="7f628-162">**Administrador de simulación de ataque**</span><span class="sxs-lookup"><span data-stu-id="7f628-162">**Attack simulation administrator**</span></span>|<span data-ttu-id="7f628-163">Crea y administra todos los aspectos de la creación de [simulación de ataques](attack-simulation-training.md), el lanzamiento o la programación de la simulación y la revisión de los resultados de la misma.</span><span class="sxs-lookup"><span data-stu-id="7f628-163">Create and manage all aspects of [attack simulation](attack-simulation-training.md) creation, launch/scheduling of a simulation, and the review of simulation results.</span></span> <span data-ttu-id="7f628-164">Para más información, consulte [Administrador de simulación de ataque](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).</span><span class="sxs-lookup"><span data-stu-id="7f628-164">For more information, see [Attack Simulation Administrator](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).</span></span>|
|<span data-ttu-id="7f628-165">**Autor de carga de ataque**</span><span class="sxs-lookup"><span data-stu-id="7f628-165">**Attack payload author**</span></span>|<span data-ttu-id="7f628-166">Crea cargas de ataques pero no las inicia ni programa.</span><span class="sxs-lookup"><span data-stu-id="7f628-166">Create attack payloads but not actually launch or schedule them.</span></span> <span data-ttu-id="7f628-167">Para más información, consulte [Autor de carga de ataques](/azure/active-directory/roles/permissions-reference#attack-payload-author).</span><span class="sxs-lookup"><span data-stu-id="7f628-167">For more information, see [Attack Payload Author](/azure/active-directory/roles/permissions-reference#attack-payload-author).</span></span>|
|

### <a name="email--collaboration-roles-in-the-security-center"></a><span data-ttu-id="7f628-168">Roles de colaboración y correo electrónico en el centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="7f628-168">Email & collaboration roles in the security center</span></span>

<span data-ttu-id="7f628-169">Si va a **Roles de colaboración y correo electrónico** \> **Permisos y roles** \> **Roles de colaboración y correo electrónico** \> **Roles** (o directamente a <https://security.microsoft.com/emailandcollabpermissions>) verá los mismos grupos de roles que están disponibles en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="7f628-169">When you go to **Email & collaboration roles** \> **Permissions & roles** \> **Email & collaboration roles** \> **Roles** (or directly to <https://security.microsoft.com/emailandcollabpermissions>) you'll see the same role groups that are available in the Security & Compliance Center.</span></span>

<span data-ttu-id="7f628-170">Para ver la información completa sobre estos grupos de roles, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7f628-170">For complete information about these role groups, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)</span></span>

#### <a name="modify-email--collaboration-role-membership-in-the-security-center"></a><span data-ttu-id="7f628-171">Modificar la pertenencia al rol de colaboración y correo electrónico en el centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="7f628-171">Modify Email & collaboration role membership in the security center</span></span>

1. <span data-ttu-id="7f628-172">En el centro de seguridad, vaya a **Roles de colaboración y correo electrónico** \> **Permisos y roles** \> **Roles de colaboración y correo electrónico** \> **Roles**.</span><span class="sxs-lookup"><span data-stu-id="7f628-172">In the security center, go to **Email & collaboration roles** \> **Permissions & roles** \> **Email & collaboration roles** \> **Roles**.</span></span>

2. <span data-ttu-id="7f628-173">En la página de **Permisos** que aparece, seleccione en la lista el grupo de roles que quiere modificar.</span><span class="sxs-lookup"><span data-stu-id="7f628-173">In the **Permissions** page that opens, select the role group that you want to modify from the list.</span></span> <span data-ttu-id="7f628-174">Puede seleccionar el encabezado de columna **Nombre** para ordenar la lista por nombre o **Búsqueda** ![Icono de búsqueda](../../media/m365-cc-sc-search-icon.png) para buscar el grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="7f628-174">You can click on the **Name** column header to sort the list by name, or you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find the role group.</span></span>

3. <span data-ttu-id="7f628-175">En el desplegable de detalles del grupo de roles que aparece, seleccione **Editar** en la sección **Miembros**.</span><span class="sxs-lookup"><span data-stu-id="7f628-175">In the role group details flyout that appears, click **Edit** in the **Members** section.</span></span>

4. <span data-ttu-id="7f628-176">En la página **Editar Elegir miembros** que aparece, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="7f628-176">In the **Editing choose members** page that appears, do one of the following steps:</span></span>
   - <span data-ttu-id="7f628-177">Si no hay ningún miembro del grupo de roles, seleccione **Elegir miembros**.</span><span class="sxs-lookup"><span data-stu-id="7f628-177">If there are no role group members, click **Choose members**.</span></span>
   - <span data-ttu-id="7f628-178">Si hay miembros en el grupo de roles, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7f628-178">If there are existing role group members, click **Edit**</span></span>

5. <span data-ttu-id="7f628-179">En el desplegable **Elegir miembros** que aparece, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="7f628-179">In the **Choose members** flyout that appears, do one of the following steps:</span></span>

   - <span data-ttu-id="7f628-180">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7f628-180">Click **Add**.</span></span> <span data-ttu-id="7f628-181">En la lista de usuarios que aparece, seleccione uno o más usuarios.</span><span class="sxs-lookup"><span data-stu-id="7f628-181">In the list of users that appears, select one or more users.</span></span> <span data-ttu-id="7f628-182">O bien, puede seleccionar **Búsqueda**![Icono de búsqueda](../../media/m365-cc-sc-search-icon.png) para buscar y seleccionar usuarios.</span><span class="sxs-lookup"><span data-stu-id="7f628-182">Or, you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find and select users.</span></span>

     <span data-ttu-id="7f628-183">Cuando haya seleccionado los usuarios que quiera, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7f628-183">When you've selected the users that you want to add, click **Add**.</span></span>

   - <span data-ttu-id="7f628-184">Seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="7f628-184">Click **Remove**.</span></span> <span data-ttu-id="7f628-185">Seleccione uno o varios de los miembros existentes.</span><span class="sxs-lookup"><span data-stu-id="7f628-185">Select one or more of the existing members.</span></span> <span data-ttu-id="7f628-186">O bien, puede seleccionar **Búsqueda**![Icono de búsqueda](../../media/m365-cc-sc-search-icon.png) para buscar y seleccionar miembros.</span><span class="sxs-lookup"><span data-stu-id="7f628-186">Or, you can click **Search** ![Search icon](../../media/m365-cc-sc-search-icon.png) to find and select members.</span></span>

     <span data-ttu-id="7f628-187">Después de seleccionar los usuarios que quiera, seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="7f628-187">When you've selected the users that you want to remove, click **Remove**.</span></span>

6. <span data-ttu-id="7f628-188">En el desplegable **Elegir miembros**, seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="7f628-188">Back on the **Choose members** flyout, click **Done**.</span></span>

7. <span data-ttu-id="7f628-189">En la página **Editar Elegir miembros**, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7f628-189">Back on the **Editing choose members** page, click **Save**.</span></span>

8. <span data-ttu-id="7f628-190">En el desplegable de detalles del grupo de roles, seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="7f628-190">Back on the role group details flyout, click **Done**.</span></span>