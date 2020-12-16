---
title: Información adicional de Azure Active Directory para la migración desde la nube de Microsoft Alemania
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
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
description: 'Resumen: información adicional de Azure Active Directory al cambiar de Microsoft Cloud Germany (Microsoft Cloud Alemania) a Office 365 Services en la nueva región del centro de datos en alemán.'
ms.openlocfilehash: 4fc5dda95e5e7afc4d69141a9a4debd0a74c492b
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688837"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="4e41d-103">Información adicional de Azure Active Directory para la migración desde la nube de Microsoft Alemania</span><span class="sxs-lookup"><span data-stu-id="4e41d-103">Additional Azure Active Directory information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="4e41d-104">Para completar el traslado de la nube de Azure en alemán a la nube pública de Azure, se recomienda actualizar el punto de conexión de autenticación, el gráfico de Azure Active Directory (Azure AD) y los puntos de conexión de MS Graph de las aplicaciones a los de la nube comercial, cuando el punto de conexión de OpenID Connect (OIDC), `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` inicia la notificación de puntos de conexión de nube comercial.</span><span class="sxs-lookup"><span data-stu-id="4e41d-104">To complete the move from the Azure German cloud to the Azure public cloud we recommend that the authentication endpoint, Azure Active Directory (Azure AD) Graph, and MS Graph endpoints for your applications be updated to those of the commercial cloud when the OpenID Connect (OIDC) endpoint, `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`, starts reporting commercial cloud endpoints.</span></span> 
 
<span data-ttu-id="4e41d-105">**¿Cuándo debería realizar este cambio?**</span><span class="sxs-lookup"><span data-stu-id="4e41d-105">**When should I make this change?**</span></span>

<span data-ttu-id="4e41d-106">Recibirá una notificación en el portal de Azure/Office cuando el inquilino complete la migración de la nube alemana a la nube comercial.</span><span class="sxs-lookup"><span data-stu-id="4e41d-106">You'll receive a notification in Azure/Office portal when your tenant completes migration from German cloud to the commercial cloud.</span></span> <span data-ttu-id="4e41d-107">Tiene 30 días después de recibir esta notificación para completar estas actualizaciones, de modo que la aplicación siga funcionando para los inquilinos que se migren desde la nube de Azure Germany a la nube pública de Azure.</span><span class="sxs-lookup"><span data-stu-id="4e41d-107">You have 30 days after receiving this notification to complete these updates so that your app continues to work for tenants that are migrated from Azure Germany cloud to Azure Public cloud.</span></span>
 
<span data-ttu-id="4e41d-108">Hay tres condiciones previas para actualizar la autoridad de inicio de sesión:</span><span class="sxs-lookup"><span data-stu-id="4e41d-108">There are three preconditions to updating your sign-in authority:</span></span>

 - <span data-ttu-id="4e41d-109">OIDC punto de conexión de detección del inquilino `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` devuelve los puntos de conexión de la nube pública de Azure ad.</span><span class="sxs-lookup"><span data-stu-id="4e41d-109">OIDC discovery endpoint for your tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returns Azure AD public cloud endpoints.</span></span>

 - <span data-ttu-id="4e41d-110">Si el espacio empresarial está configurado para la Federación, los servicios de Federación de Active Directory (AD FS) se actualizan para sincronizarse con Azure AD público.</span><span class="sxs-lookup"><span data-stu-id="4e41d-110">If your tenant is set up for federation, Active Directory Federation Services (AD FS) is updated to sync with Azure AD Public.</span></span> <span data-ttu-id="4e41d-111">Puede seguir las instrucciones para actualizar la configuración de Azure AD Connect para realizar este cambio.</span><span class="sxs-lookup"><span data-stu-id="4e41d-111">You can follow instructions to update Azure AD Connect settings for making this change.</span></span>

 - <span data-ttu-id="4e41d-112">Las aplicaciones de recursos, si las hay, usadas por las aplicaciones se modifican para aceptar tokens firmados por Azure AD Germany y Azure AD público.</span><span class="sxs-lookup"><span data-stu-id="4e41d-112">Resource applications, if any, used by your applications are modified to accept tokens that are signed by both Azure AD Germany and Azure AD Public.</span></span>
 
<span data-ttu-id="4e41d-113">**¿Qué tipo de aplicaciones?**</span><span class="sxs-lookup"><span data-stu-id="4e41d-113">**What kind of applications?**</span></span>

<span data-ttu-id="4e41d-114">Una aplicación puede ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="4e41d-114">An application could be any of the following:</span></span>

- [<span data-ttu-id="4e41d-115">Aplicación de una sola página (SPA)</span><span class="sxs-lookup"><span data-stu-id="4e41d-115">Single-page app (SPA)</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [<span data-ttu-id="4e41d-116">Aplicación web que inicia sesión en los usuarios</span><span class="sxs-lookup"><span data-stu-id="4e41d-116">Web app that signs in users</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [<span data-ttu-id="4e41d-117">Aplicación web que llama a las API Web</span><span class="sxs-lookup"><span data-stu-id="4e41d-117">Web app that calls web APIs</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [<span data-ttu-id="4e41d-118">API Web protegida</span><span class="sxs-lookup"><span data-stu-id="4e41d-118">Protected web API</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [<span data-ttu-id="4e41d-119">API Web que llama a las API Web</span><span class="sxs-lookup"><span data-stu-id="4e41d-119">Web API that calls web APIs</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [<span data-ttu-id="4e41d-120">Aplicación de escritorio</span><span class="sxs-lookup"><span data-stu-id="4e41d-120">Desktop app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [<span data-ttu-id="4e41d-121">Aplicación demonio</span><span class="sxs-lookup"><span data-stu-id="4e41d-121">Daemon app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [<span data-ttu-id="4e41d-122">Aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="4e41d-122">Mobile app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> <span data-ttu-id="4e41d-123">Cuando una aplicación cambia a usar `login.microsoftonline.com` como su autoridad, los tokens serán firmados por esta nueva entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="4e41d-123">When an application switches to using `login.microsoftonline.com` as your authority, the tokens will be signed by this new authority.</span></span> <span data-ttu-id="4e41d-124">Si hospeda aplicaciones de recursos en las que otras aplicaciones llaman, deberá permitir la validación de tokens LAX.</span><span class="sxs-lookup"><span data-stu-id="4e41d-124">If you host any resource applications that other apps call into, you will need to allow for lax token validation.</span></span> <span data-ttu-id="4e41d-125">Esto significa que la aplicación debe permitir tokens que estén firmados por las nubes públicas de Azure AD Alemania y Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4e41d-125">This means that your app needs to allow tokens that are signed by both the Azure AD Germany and Azure AD public clouds.</span></span> <span data-ttu-id="4e41d-126">Esta validación de token de LAX es necesaria hasta que todas las aplicaciones cliente que llaman a su servicio se migren por completo a la nube pública de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4e41d-126">This lax token validation is needed until all client applications that call your service are fully migrated to the Azure AD public cloud.</span></span> <span data-ttu-id="4e41d-127">Después de la migración, la aplicación de recursos solo necesita aceptar tokens firmados por la nube pública de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4e41d-127">After migration, your resource application only needs to accept tokens signed by the Azure AD public cloud.</span></span>

<span data-ttu-id="4e41d-128">**¿Qué es necesario actualizar?**</span><span class="sxs-lookup"><span data-stu-id="4e41d-128">**What do I need to update?**</span></span>

1. <span data-ttu-id="4e41d-129">Si hospeda una aplicación en Azure Germany que se usa para autenticar usuarios de Azure Germany o Office 365 Germany, asegúrese de que `https://login.microsoftonline.com` se usa como la autoridad en el contexto de autenticación.</span><span class="sxs-lookup"><span data-stu-id="4e41d-129">If you're hosting an application in Azure Germany that is used to authenticate Azure Germany or Office 365 Germany users, ensure that `https://login.microsoftonline.com` is used as the authority in the authentication context.</span></span>

    - <span data-ttu-id="4e41d-130">Consulte contextos de autenticación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4e41d-130">See Azure AD authentication contexts.</span></span>
    - <span data-ttu-id="4e41d-131">Esto se aplica tanto a la autenticación en su aplicación como a cualquier API a la que pueda llamar la aplicación (es decir, Microsoft Graph, el gráfico de Azure AD, el administrador de recursos de Azure).</span><span class="sxs-lookup"><span data-stu-id="4e41d-131">This applies both to authentication to your application as well as authentication to any APIs that your application may be calling (that is, Microsoft Graph, Azure AD Graph, Azure Resource Manager).</span></span>

2. <span data-ttu-id="4e41d-132">Actualizar el extremo de Azure AD Graph `https://graph.windows.net` .</span><span class="sxs-lookup"><span data-stu-id="4e41d-132">Update Azure AD Graph endpoint to be `https://graph.windows.net`.</span></span>

3. <span data-ttu-id="4e41d-133">Actualizar el extremo de MS Graph `https://graph.microsoft.com` .</span><span class="sxs-lookup"><span data-stu-id="4e41d-133">Update MS Graph endpoint to be `https://graph.microsoft.com`.</span></span>

4. <span data-ttu-id="4e41d-134">Actualice los puntos de conexión de nube en alemán (como los de Exchange Online y SharePoint Online) que las aplicaciones usan para que sean los de la nube pública.</span><span class="sxs-lookup"><span data-stu-id="4e41d-134">Update any German cloud endpoints (such as those for Exchange Online and SharePoint Online) that are used by your applications to be those of the public cloud.</span></span>

5. <span data-ttu-id="4e41d-135">Actualice los parámetros de entorno para que sean `AzurePublic` (en lugar de `AzureGermany` ) en las herramientas de administración y los scripts para:</span><span class="sxs-lookup"><span data-stu-id="4e41d-135">Update environment parameters to be `AzurePublic` (instead of `AzureGermany`) in administrative tools and scripts for:</span></span>

    - [<span data-ttu-id="4e41d-136">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e41d-136">Azure PowerShell</span></span>](https://docs.microsoft.com/powershell/azure/install-az-ps)
    - [<span data-ttu-id="4e41d-137">PowerShell de Azure AD (MSOnline)</span><span class="sxs-lookup"><span data-stu-id="4e41d-137">Azure AD PowerShell (MSOnline)</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/overview)
    - [<span data-ttu-id="4e41d-138">PowerShell de Azure AD (AzureAD)</span><span class="sxs-lookup"><span data-stu-id="4e41d-138">Azure AD PowerShell (AzureAD)</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?)
    - [<span data-ttu-id="4e41d-139">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="4e41d-139">Azure CLI</span></span>](https://docs.microsoft.com/cli/azure/install-azure-cli)
 
<span data-ttu-id="4e41d-140">**¿Qué ocurre con las aplicaciones que se publican?**</span><span class="sxs-lookup"><span data-stu-id="4e41d-140">**What about applications that I publish?**</span></span>

<span data-ttu-id="4e41d-141">Si publica una aplicación que está disponible para los usuarios que están fuera de su inquilino, es posible que deba cambiar el registro de la aplicación para garantizar la continuidad.</span><span class="sxs-lookup"><span data-stu-id="4e41d-141">If you publish an application that is available to users who are outside of your tenant, you may need to change your application registration to ensure continuity.</span></span> <span data-ttu-id="4e41d-142">Otros inquilinos que usan la aplicación pueden moverse en un tiempo diferente al del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="4e41d-142">Other tenants that use your application may be moved at a different time than your tenant.</span></span> <span data-ttu-id="4e41d-143">Para asegurarse de que nunca pierdan el acceso a la aplicación, deberá dar su consentimiento a la aplicación que se está sincronizando desde Azure Germany a Azure Public.</span><span class="sxs-lookup"><span data-stu-id="4e41d-143">To ensure that they never lose access to your application, you'll need to consent to your app being synchronized from Azure Germany to Azure public.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="4e41d-144">Consideraciones adicionales</span><span class="sxs-lookup"><span data-stu-id="4e41d-144">Additional considerations</span></span>

<span data-ttu-id="4e41d-145">Estas son algunas consideraciones adicionales para Azure AD:</span><span class="sxs-lookup"><span data-stu-id="4e41d-145">Here are some additional considerations for Azure AD:</span></span>

- <span data-ttu-id="4e41d-146">Para la autenticación federada:</span><span class="sxs-lookup"><span data-stu-id="4e41d-146">For federated authentication:</span></span>

  - <span data-ttu-id="4e41d-147">No debe crear, promover o disminuir el nivel de un dominio federado mientras la transición de inquilino esté en proceso.</span><span class="sxs-lookup"><span data-stu-id="4e41d-147">You must not create, promote, or demote a federated domain while the tenant transition is in process.</span></span> <span data-ttu-id="4e41d-148">Una vez finalizada la migración al servicio de Azure AD (el inquilino se ha completado completamente), puede reanudar la administración de dominios federados.</span><span class="sxs-lookup"><span data-stu-id="4e41d-148">After the migration to the Azure AD service is complete (the tenant is fully complete), you can resume managing federated domains.</span></span>

  - <span data-ttu-id="4e41d-149">Si está usando la autenticación federada con los servicios de Federación de Active Directory (AD FS), no debe realizar cambios en las URI del emisor usadas para toda la autenticación con los servicios de dominio de Active Directory (AD DS) locales durante la migración.</span><span class="sxs-lookup"><span data-stu-id="4e41d-149">If you're using federated authentication with Active Directory Federation Services (AD FS), you shouldn't make changes to Issuer URIs used for all authentication with your on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="4e41d-150">Cambiar los URI del emisor conducirá a errores de autenticación para los usuarios del dominio.</span><span class="sxs-lookup"><span data-stu-id="4e41d-150">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="4e41d-151">Los URI del emisor se pueden cambiar directamente en AD FS o cuando un dominio se convierte de administrado a federado y viceversa.</span><span class="sxs-lookup"><span data-stu-id="4e41d-151">Issuer URIs can be changed directly in AD FS or when a domain is converted from managed to federated and vice versa.</span></span> <span data-ttu-id="4e41d-152">Microsoft recomienda a los clientes no agregar, quitar ni convertir un dominio federado en el inquilino de Azure AD que se está migrando.</span><span class="sxs-lookup"><span data-stu-id="4e41d-152">Microsoft recommends customers don't add, remove, or convert a federated domain in the Azure AD tenant being migrated.</span></span> <span data-ttu-id="4e41d-153">Los URI del emisor se pueden cambiar una vez que la migración se haya completado completamente.</span><span class="sxs-lookup"><span data-stu-id="4e41d-153">Issuer URIs can be changed after the migration is fully complete.</span></span>

- <span data-ttu-id="4e41d-154">Para redes:</span><span class="sxs-lookup"><span data-stu-id="4e41d-154">For networking:</span></span>

  - <span data-ttu-id="4e41d-155">La creación de redes con nombre IPv6 no funciona en Azure portal `http://portal.microsoftazure.de/` .</span><span class="sxs-lookup"><span data-stu-id="4e41d-155">Creating IPv6-named networks doesn't work in the Azure portal, `http://portal.microsoftazure.de/`.</span></span> <span data-ttu-id="4e41d-156">Use Azure portal en `https://portal.azure.com` para crear redes con nombre IPv6.</span><span class="sxs-lookup"><span data-stu-id="4e41d-156">Use the Azure portal at `https://portal.azure.com` to create IPv6-named networks.</span></span>
 
   - <span data-ttu-id="4e41d-157">No puede crear intervalos de direcciones IP de confianza para la configuración del servicio de Azure multi-factor Authentication (MFA) en Microsoft Cloud Alemania portal.</span><span class="sxs-lookup"><span data-stu-id="4e41d-157">You can't create trusted IP address ranges for Azure Multi-Factor Authentication (MFA) service settings from the Microsoft Cloud Deutschland portal.</span></span> <span data-ttu-id="4e41d-158">Use el portal de Azure AD para los servicios de Office 365 para crear intervalos de direcciones IP de confianza de Azure MFA.</span><span class="sxs-lookup"><span data-stu-id="4e41d-158">Use the Azure AD portal for Office 365 services to create Azure MFA trusted IP address ranges.</span></span>


- <span data-ttu-id="4e41d-159">Para el acceso condicional:</span><span class="sxs-lookup"><span data-stu-id="4e41d-159">For Conditional Access:</span></span> 

  - <span data-ttu-id="4e41d-160">Las directivas de acceso condicional con los siguientes controles Grant no se admiten hasta que se complete la migración a Office 365 Services (después de la finalización de la fase de migración de [Azure ad](ms-cloud-germany-transition.md#how-is-the-migration-organized) ):</span><span class="sxs-lookup"><span data-stu-id="4e41d-160">Conditional Access policies with the following grant controls aren't supported until migration to Office 365 services is complete (after the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase):</span></span>

    - <span data-ttu-id="4e41d-161">Requerir dispositivo compatible</span><span class="sxs-lookup"><span data-stu-id="4e41d-161">Require Compliant Device</span></span>
    - <span data-ttu-id="4e41d-162">Requerir una aplicación aprobada</span><span class="sxs-lookup"><span data-stu-id="4e41d-162">Require Approved App</span></span>
    - <span data-ttu-id="4e41d-163">Requerir Directiva de protección de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="4e41d-163">Require App Protection Policy</span></span>
    
  - <span data-ttu-id="4e41d-164">La interfaz de directiva de acceso condicional da una falsa Advertencia sobre la habilitación de los valores predeterminados de seguridad para el inquilino, incluso cuando está deshabilitado, y las directivas de acceso condicional ya existen para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="4e41d-164">The Conditional Access policy interface gives a false warning about security defaults being enabled for the tenant even when it's disabled, and Conditional Access policies already exist for the tenant.</span></span> <span data-ttu-id="4e41d-165">Debe omitir la advertencia o usar el portal de servicios de Office 365 para administrar las directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="4e41d-165">You should ignore the warning or use the Office 365 services portal to manage Conditional Access policies.</span></span> 

- <span data-ttu-id="4e41d-166">Los escenarios de Intune solo se admiten en extremos mundiales tras la finalización de la migración de inquilinos, incluidas todas las migraciones de cargas de trabajo de Office.</span><span class="sxs-lookup"><span data-stu-id="4e41d-166">Intune scenarios are supported only against worldwide endpoints after tenant migration is complete, including all office workloads migrations.</span></span>

- <span data-ttu-id="4e41d-167">Microsoft Cloud Alemania los usuarios que usan el método de notificación de aplicaciones móviles para solicitudes de MFA ven el ObjectId del usuario (un GUID) en lugar del nombre principal del usuario (UPN) en la aplicación Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="4e41d-167">Microsoft Cloud Deutschland users who use the Mobile App Notification method for MFA requests see the user's ObjectId (a GUID) instead of the user principal name (UPN) in the Microsoft Authenticator app.</span></span> <span data-ttu-id="4e41d-168">Después de que se complete la migración del inquilino de Azure AD y se hospede en los servicios de Office 365, las nuevas activaciones de Microsoft Authenticator mostrarán los UPN de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4e41d-168">After migration of the Azure AD tenant is complete and hosted in Office 365 services, new Microsoft Authenticator activations will display users' UPNs.</span></span> <span data-ttu-id="4e41d-169">Las cuentas existentes de Microsoft Authenticator seguirán mostrando el usuario ObjectId, pero seguirán trabajando para notificaciones de aplicaciones móviles.</span><span class="sxs-lookup"><span data-stu-id="4e41d-169">Existing Microsoft Authenticator accounts will continue to display the user ObjectId, but they'll continue to work for mobile app notifications.</span></span> 

- <span data-ttu-id="4e41d-170">Para los inquilinos que se crean después del 22 de octubre de 2019, los valores predeterminados de seguridad pueden estar habilitados automáticamente para el inquilino cuando se migre al servicio de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e41d-170">For tenants that are created after October 22, 2019, security defaults may be auto-enabled for the tenant when it's migrated to the Office 365 service.</span></span> <span data-ttu-id="4e41d-171">Los administradores de inquilinos pueden elegir dejar los valores predeterminados de seguridad habilitados y registrarse para MFA, o pueden deshabilitar la característica.</span><span class="sxs-lookup"><span data-stu-id="4e41d-171">Tenant admins can choose to leave security defaults enabled and register for MFA, or they can disable the feature.</span></span> <span data-ttu-id="4e41d-172">Para obtener más información, vea [deshabilitar los valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="4e41d-172">For more information, see [Disabling security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults).</span></span> 

  > [!NOTE]
  > <span data-ttu-id="4e41d-173">Es posible que las organizaciones que no se habilitan automáticamente durante la migración se puedan inscribir automáticamente en el futuro, ya que la característica para habilitar los valores predeterminados de seguridad se implementa en el servicio de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e41d-173">Organizations that are not auto-enabled during migration may still be auto-enrolled in the future as the feature to enable security defaults is rolled out in the Office 365 service.</span></span> <span data-ttu-id="4e41d-174">Los administradores que elijan o deshabiliten explícitamente los valores predeterminados de seguridad pueden hacerlo si actualizan la característica en **propiedades > de Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="4e41d-174">Admins who choose to explicitly disable or enable security defaults may do so by updating the feature under **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="4e41d-175">Una vez que el administrador haya habilitado la característica explícitamente, no se habilitará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4e41d-175">After the feature is explicitly enabled by the admin, it will not be auto-enabled.</span></span>

- <span data-ttu-id="4e41d-176">Se mostrará una advertencia sobre la versión de Azure AD Connect en el portal de Office 365 Germany y en el portal de Office 365 una vez que el inquilino se encuentra en la migración.</span><span class="sxs-lookup"><span data-stu-id="4e41d-176">There will be warning about the version of Azure AD Connect in the Office 365 Germany portal as well as in the Office 365 portal once the tenant is in migration.</span></span> <span data-ttu-id="4e41d-177">Esto puede pasarse por alto si la advertencia de versión ya no muestra la advertencia una vez finalizada la migración.</span><span class="sxs-lookup"><span data-stu-id="4e41d-177">This can be ignored if the version warning is no longer showing the warning after the migration is complete.</span></span> <span data-ttu-id="4e41d-178">Si hay una advertencia, ya sea antes o después de la migración, en cualquier portal, debe actualizarse Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="4e41d-178">If there's a warning, either before or after migration, in either portal, Azure AD Connect must be updated.</span></span> <span data-ttu-id="4e41d-179">El mensaje de advertencia dice: "se detectó que está usando una herramienta de sincronización de directorios obsoleta.</span><span class="sxs-lookup"><span data-stu-id="4e41d-179">The warning message says: "We detected you're using an outdated directory sync tool.</span></span> <span data-ttu-id="4e41d-180">Le recomendamos que vaya al centro de descarga de Microsoft para obtener la versión más reciente de Azure AD Connect. "</span><span class="sxs-lookup"><span data-stu-id="4e41d-180">We recommend you go to the Microsoft Download Center to get the latest version of Azure AD Connect."</span></span>

## <a name="more-information"></a><span data-ttu-id="4e41d-181">Más información</span><span class="sxs-lookup"><span data-stu-id="4e41d-181">More information</span></span>

<span data-ttu-id="4e41d-182">Introducción:</span><span class="sxs-lookup"><span data-stu-id="4e41d-182">Getting started:</span></span>

- [<span data-ttu-id="4e41d-183">Migración desde Microsoft Cloud Alemania a Office 365 Services en las nuevas regiones del centro de administración de Office en alemán</span><span class="sxs-lookup"><span data-stu-id="4e41d-183">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="4e41d-184">Asistencia para la migración a Microsoft Cloud Alemania</span><span class="sxs-lookup"><span data-stu-id="4e41d-184">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="4e41d-185">Cómo participar en la migración</span><span class="sxs-lookup"><span data-stu-id="4e41d-185">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="4e41d-186">Experiencia del cliente durante la migración</span><span class="sxs-lookup"><span data-stu-id="4e41d-186">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="4e41d-187">Desplazarse por la transición:</span><span class="sxs-lookup"><span data-stu-id="4e41d-187">Moving through the transition:</span></span>

- [<span data-ttu-id="4e41d-188">Impactos y acciones de las fases de migración</span><span class="sxs-lookup"><span data-stu-id="4e41d-188">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="4e41d-189">Pre-trabajo adicional</span><span class="sxs-lookup"><span data-stu-id="4e41d-189">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="4e41d-190">Información adicional para [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="4e41d-190">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="4e41d-191">Aplicaciones en la nube:</span><span class="sxs-lookup"><span data-stu-id="4e41d-191">Cloud apps:</span></span>

- [<span data-ttu-id="4e41d-192">Información del programa de migración de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="4e41d-192">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="4e41d-193">Información del programa de migración de Power BI</span><span class="sxs-lookup"><span data-stu-id="4e41d-193">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="4e41d-194">Introducción a su actualización de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4e41d-194">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)