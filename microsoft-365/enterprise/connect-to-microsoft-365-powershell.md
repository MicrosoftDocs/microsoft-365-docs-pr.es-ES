---
title: Conectarse a Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Conéctese a su espacio empresarial de Microsoft 365 mediante PowerShell para que Microsoft 365 realice tareas del Centro de administración desde la línea de comandos.
ms.openlocfilehash: d1e347a13ca5c587fa544ef80a8e289a8dec0a59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693978"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="e6f8d-103">Conectarse a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6f8d-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="e6f8d-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="e6f8d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e6f8d-105">PowerShell para Microsoft 365 le permite administrar la configuración de Microsoft 365 desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-105">PowerShell for Microsoft 365 lets you manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="e6f8d-106">Conectarse a PowerShell es un proceso sencillo que consiste en instalar el software necesario y conectarse a su organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-106">Connecting to PowerShell is a simple process where you install the required software and then connect to your Microsoft 365 organization.</span></span> 

<span data-ttu-id="e6f8d-107">Hay dos versiones del módulo de PowerShell que puede usar para conectarse a Microsoft 365 y administrar cuentas de usuario, grupos y licencias:</span><span class="sxs-lookup"><span data-stu-id="e6f8d-107">There are two versions of the PowerShell module that you use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="e6f8d-108">Azure Active Directory PowerShell para Graph (los cmdlets incluyen **AzureAD** en su nombre)</span><span class="sxs-lookup"><span data-stu-id="e6f8d-108">Azure Active Directory PowerShell for Graph (cmdlets include **AzureAD** in their name)</span></span>
- <span data-ttu-id="e6f8d-109">Módulo Microsoft Azure Active Directory para Windows PowerShell (los cmdlets incluyen **MSol** en su nombre)</span><span class="sxs-lookup"><span data-stu-id="e6f8d-109">Microsoft Azure Active Directory Module for Windows PowerShell (cmdlets include **MSol** in their name)</span></span> 

<span data-ttu-id="e6f8d-110">En la fecha de este artículo, el Módulo MAzure Active Directory para Graph no reemplaza completamente la funcionalidad de los cmdlets del Módulo Microsoft Azure Active Directory para Windows PowerShell para la administración de usuarios, grupos y licencias.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-110">As of the date of this article, the Azure Active Directory PowerShell for Graph module does not completely replace the functionality in the cmdlets of Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="e6f8d-111">En algunos casos, deberá usar ambas versiones.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="e6f8d-112">Puede instalar ambas versiones de forma segura en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e6f8d-113">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="e6f8d-113">What do you need to know before you begin?</span></span>

<span data-ttu-id="e6f8d-114">Puede usar las siguientes versiones de Windows:</span><span class="sxs-lookup"><span data-stu-id="e6f8d-114">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="e6f8d-115">Windows 10, Windows 8.1, Windows 8 o Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="e6f8d-115">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="e6f8d-116">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="e6f8d-116">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

    > [!NOTE]
    > <span data-ttu-id="e6f8d-117">Para el Módulo Azure Active Directory PowerShell para Graph, debe usar la versión 5.1 o posterior de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-117">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span> <span data-ttu-id="e6f8d-118">Para el Módulo Microsoft Azure Active Directory para Windows PowerShell, debe usar la versión 5.1 o posterior de PowerShell hasta la versión 6.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-118">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later up to PowerShell version 6.</span></span> <span data-ttu-id="e6f8d-119">No puede usar la versión 7 de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-119">You cannot use PowerShell version 7.</span></span> <span data-ttu-id="e6f8d-120">Para Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 y Windows Server 2008 R2 SP1, descargue e instale [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="e6f8d-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="e6f8d-p104">Use una versión de 64 bits de Windows. La compatibilidad con la versión de 32 bits de Módulo de Microsoft Azure Active Directory para Windows PowerShell se descontinuó en octubre de 2014.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-p104">Use a 64-bit version of Windows. Support for the 32-bit version the Microsoft Azure Active Directory Module for Windows PowerShell was discontinued in October of 2014.</span></span>
    
<span data-ttu-id="e6f8d-123">Estos procedimientos están diseñados para los usuarios que sean miembros de un rol de administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-123">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="e6f8d-124">Para obtener más información, vea [Asignar roles de administrador](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span><span class="sxs-lookup"><span data-stu-id="e6f8d-124">For more information, see [About admin roles](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e6f8d-125">Conéctese al módulo de PowerShell de Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="e6f8d-125">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e6f8d-126">Los comandos del módulo PowerShell Azure Active Directory para Graph incluyen **AzureAD** en su nombre de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-126">Commands in the Azure Active Directory PowerShell for Graph module have **AzureAD** in their cmdlet name.</span></span> <span data-ttu-id="e6f8d-127">Puede instalar el módulo [Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) o [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-3.6.1).</span><span class="sxs-lookup"><span data-stu-id="e6f8d-127">You can install the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) module or [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-3.6.1).</span></span>

<span data-ttu-id="e6f8d-128">Para los procedimientos que necesitan los nuevos cmdlets del módulo de PowerShell Azure Active Directory para Graph, siga estos pasos para instalar el módulo y conectarse a su suscripción a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-128">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, use these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="e6f8d-129">Vea [Módulo de PowerShell Azure Active Directory para Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) para obtener información sobre la compatibilidad con diferentes versiones de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-129">See [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) for information about the support for different versions of Microsoft Windows.</span></span>
>

### <a name="step-1-install-required-software"></a><span data-ttu-id="e6f8d-130">Paso 1: Instalar el software necesario</span><span class="sxs-lookup"><span data-stu-id="e6f8d-130">Step 1: Install required software</span></span>

<span data-ttu-id="e6f8d-p107">Estos pasos son necesarios una sola vez en el equipo, no cada vez que se conecta. Sin embargo, probablemente necesitará instalar las versiones más recientes de software periódicamente.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-p107">These steps are required once on your computer, not every time you connect. However, you'll likely need to install newer versions of the software periodically.</span></span>
  
1. <span data-ttu-id="e6f8d-133">Abra un símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador).</span><span class="sxs-lookup"><span data-stu-id="e6f8d-133">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="e6f8d-134">En la ventana de comandos **Administrador: Windows PowerShell**, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="e6f8d-134">In the **Administrator: Windows PowerShell** command window, run this command:</span></span>
    
  ```powershell
  Install-Module -Name AzureAD
  ```

<span data-ttu-id="e6f8d-135">Si se le pregunta si quiere instalar un módulo desde un repositorio que no es de confianza, escriba **Y** y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-135">If prompted about installing a module from an untrusted repository, type **Y** and press ENTER.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="e6f8d-136">Paso 2: Conectarse a Azure AD para la suscripción de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6f8d-136">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="e6f8d-137">Para conectarse a Azure AD para la suscripción de Microsoft 365 con un nombre de cuenta y contraseña o con la autenticación multifactor (MFA), ejecute uno de estos comandos desde un símbolo del sistema de Windows PowerShell (no tiene que ser elevado).</span><span class="sxs-lookup"><span data-stu-id="e6f8d-137">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication (MFA), run one of these commands from a Windows PowerShell command prompt (it does not have to be elevated).</span></span>

| <span data-ttu-id="e6f8d-138">Nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="e6f8d-138">Office 365 cloud</span></span> | <span data-ttu-id="e6f8d-139">Comando</span><span class="sxs-lookup"><span data-stu-id="e6f8d-139">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="e6f8d-140">Office 365 Worldwide (+GCC)</span><span class="sxs-lookup"><span data-stu-id="e6f8d-140">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="e6f8d-141">Office 365 ofrecido por 21Vianet</span><span class="sxs-lookup"><span data-stu-id="e6f8d-141">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="e6f8d-142">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="e6f8d-142">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="e6f8d-143">Office 365 U.S. Government DoD y Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="e6f8d-143">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="e6f8d-144">En el cuadro de diálogo **Inicie sesión**, escriba su nombre de usuario y contraseña de la cuenta profesional o educativa de Microsoft 365 y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-144">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then click **OK**.</span></span>

<span data-ttu-id="e6f8d-145">Si usa MFA, siga las instrucciones en los cuadros de diálogo adicionales para proporcionar más información de autenticación, como un código de comprobación.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-145">If you are using MFA, follow the instructions in the additional dialog boxes to provide more authentication information, such as a verification code.</span></span>

<span data-ttu-id="e6f8d-146">Después de conectar, puede usar los cmdlets para el módulo [PowerShell de Azure Active Directory para](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span><span class="sxs-lookup"><span data-stu-id="e6f8d-146">After connecting, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span></span>
  

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e6f8d-147">Conectar con el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6f8d-147">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e6f8d-148">Los comandos del Módulo Microsoft Azure Active Directory para Windows PowerShell tienen **Msol** en el nombre de su cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-148">Commands in the Microsoft Azure Active Directory Module for Windows PowerShell have **Msol** in their cmdlet name.</span></span>

<span data-ttu-id="e6f8d-149">La versión 7 de PowerShell no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-149">PowerShell version 7 and later do not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="e6f8d-150">Para la versión 7 de PowerShell y versiones posteriores, debe usar el Módulo Azure Active Directory Powershell para Graph o Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-150">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="e6f8d-151">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-151">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="e6f8d-152">Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-152">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span> 
    
### <a name="step-1-install-required-software"></a><span data-ttu-id="e6f8d-153">Paso 1: Instalar el software necesario</span><span class="sxs-lookup"><span data-stu-id="e6f8d-153">Step 1: Install required software</span></span>

<span data-ttu-id="e6f8d-p110">Estos pasos son necesarios una sola vez en el equipo, no cada vez que se conecta. Sin embargo, probablemente necesitará instalar las versiones más recientes de software periódicamente.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-p110">These steps are required once on your computer, not every time you connect. However, you'll likely need to install newer versions of the software periodically.</span></span>
  
1.  <span data-ttu-id="e6f8d-156">Si no ejecuta Windows 10, instale la versión de 64 bits de Microsoft Online Services - Ayudante para el inicio de sesión: [Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de TI (RTW)](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span><span class="sxs-lookup"><span data-stu-id="e6f8d-156">If you are not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
    
2. <span data-ttu-id="e6f8d-157">Instale el Módulo Microsoft Azure Active Directory para Windows PowerShell siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e6f8d-157">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>
    
  - <span data-ttu-id="e6f8d-158">Abra un símbolo del sistema de Windows PowerShell con privilegios elevados (ejecute Windows PowerShell como administrador).</span><span class="sxs-lookup"><span data-stu-id="e6f8d-158">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
  - <span data-ttu-id="e6f8d-159">Ejecute el comando **Install-Module MSOnline**.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-159">Run the **Install-Module MSOnline** command.</span></span>
  - <span data-ttu-id="e6f8d-160">Si se le pide que instale el proveedor de NuGet, escriba **Y** y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-160">If prompted to install the NuGet provider, type **Y** and press ENTER.</span></span>
  - <span data-ttu-id="e6f8d-161">Si se le pide que instale el módulo desde PSGallery, escriba **Y** y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-161">If prompted to install the module from PSGallery, type **Y** and press ENTER.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="e6f8d-162">Paso 2: Conectarse a Azure AD para la suscripción de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6f8d-162">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="e6f8d-163">Para conectarse a Azure AD para la suscripción de Microsoft 365 con un nombre de cuenta y contraseña o con la autenticación multifactor (MFA), ejecute uno de estos comandos desde un símbolo del sistema de Windows PowerShell (no tiene que ser elevado).</span><span class="sxs-lookup"><span data-stu-id="e6f8d-163">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication (MFA), run one of these commands from a Windows PowerShell command prompt (it does not have to be elevated).</span></span>

| <span data-ttu-id="e6f8d-164">Nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="e6f8d-164">Office 365 cloud</span></span> | <span data-ttu-id="e6f8d-165">Comando</span><span class="sxs-lookup"><span data-stu-id="e6f8d-165">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="e6f8d-166">Office 365 Worldwide (+GCC)</span><span class="sxs-lookup"><span data-stu-id="e6f8d-166">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="e6f8d-167">Office 365 ofrecido por 21Vianet</span><span class="sxs-lookup"><span data-stu-id="e6f8d-167">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="e6f8d-168">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="e6f8d-168">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="e6f8d-169">Office 365 U.S. Government DoD y Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="e6f8d-169">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="e6f8d-170">En el cuadro de diálogo **Inicie sesión**, escriba su nombre de usuario y contraseña de la cuenta profesional o educativa de Microsoft 365 y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-170">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then click **OK**.</span></span>

<span data-ttu-id="e6f8d-171">Si usa MFA, siga las instrucciones en los cuadros de diálogo adicionales para proporcionar más información de autenticación, como un código de comprobación.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-171">If you are using MFA, follow the instructions in the additional dialog boxes to provide more authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e6f8d-172">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="e6f8d-172">How do you know this worked?</span></span>

<span data-ttu-id="e6f8d-173">Si no se muestra ningún error, la conexión se habrá establecido correctamente.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-173">If you don't receive any errors, you connected successfully.</span></span> <span data-ttu-id="e6f8d-174">Para hacer una prueba rápida, ejecute un cmdlet de Microsoft 365, como **Get-MsolUser**, y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-174">A quick test is to run a Microsoft 365 cmdlet—for example, **Get-MsolUser** —and see the results.</span></span>
  
<span data-ttu-id="e6f8d-175">Si surgen errores, compruebe los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="e6f8d-175">If you receive errors, check the following requirements:</span></span>
  
- <span data-ttu-id="e6f8d-176">**Un problema habitual es una contraseña incorrecta**.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-176">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="e6f8d-177">Vuelva a realizar el paso 2.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-177">Run Step 2 again.</span></span> <span data-ttu-id="e6f8d-178">y preste especial atención al nombre de usuario y la contraseña que escriba.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-178">and pay close attention to the user name and password you enter.</span></span>
    
- <span data-ttu-id="e6f8d-p113">**El Módulo de Microsoft Azure Active Directory para Windows PowerShell requiere que la característica Microsoft .NET Framework 3.5.* x* esté habilitada en el equipo\*\*. Es probable que el equipo tenga instalada una versión más reciente (por ejemplo, 4 o 4.5. *x*), pero sea posible habilitar o deshabilitar la compatibilidad con versiones anteriores de .NET Framework. Para obtener más información al respecto, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6f8d-p113">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that the Microsoft .NET Framework 3.5.* x* feature is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*), but backwards compatibility with older versions of the .NET Framework can be enabled or disabled. For more information, see the following topics:</span></span>
    
  - <span data-ttu-id="e6f8d-181">Para Windows Server 2012 o Windows Server 2012 R2, vea [Habilitar .NET Framework 3.5 con el Asistente para agregar roles y características](https://go.microsoft.com/fwlink/p/?LinkId=532368).</span><span class="sxs-lookup"><span data-stu-id="e6f8d-181">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](https://go.microsoft.com/fwlink/p/?LinkId=532368)</span></span>
    
  - <span data-ttu-id="e6f8d-182">Para Windows 7 o Windows Server 2008 R2, vea [No puede abrir el Módulo de Azure Active Directory para Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370).</span><span class="sxs-lookup"><span data-stu-id="e6f8d-182">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370)</span></span>

  - <span data-ttu-id="e6f8d-183">Para Windows 10, Windows 8.1 y Windows 8, vea [Instalar .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)</span><span class="sxs-lookup"><span data-stu-id="e6f8d-183">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)</span></span>

  
- <span data-ttu-id="e6f8d-184">**Puede que su versión de Módulo de Microsoft Azure Active Directory para Windows PowerShell esté obsoleta.**</span><span class="sxs-lookup"><span data-stu-id="e6f8d-184">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="e6f8d-185">Para comprobarlo, ejecute el siguiente comando en PowerShell para Microsoft 365 o el Módulo de Microsoft Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e6f8d-185">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="e6f8d-186">Si el número de versión devuelto es menor que el valor 1.0.8070.2, desinstale el Módulo de Microsoft Azure Active Directory para Windows PowerShell e instale de nuevo siguiendo el Paso 1, que encontrará arriba.</span><span class="sxs-lookup"><span data-stu-id="e6f8d-186">If the version number returned is lower than the value 1.0.8070.2, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from Step 1 above.</span></span>

- <span data-ttu-id="e6f8d-187">**Si recibe un error de conexión, vea este tema:** [Error “Connect-MsolService: Se produjo una excepción de tipo”](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span><span class="sxs-lookup"><span data-stu-id="e6f8d-187">**If you receive a connection error, see this topic:** ["Connect-MsolService: Exception of type was thrown" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span></span>
    
- <span data-ttu-id="e6f8d-188">**Si recibe un mensaje de error "Obtener elemento: No se encontró la ruta de acceso", utilice este comando:**</span><span class="sxs-lookup"><span data-stu-id="e6f8d-188">**If you receive a "Get-Item : Cannot find path" error, use this command:**</span></span> 

```powershell
  (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
```

## <a name="see-also"></a><span data-ttu-id="e6f8d-189">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6f8d-189">See also</span></span>

- [<span data-ttu-id="e6f8d-190">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6f8d-190">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e6f8d-191">Introducción a PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6f8d-191">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e6f8d-192">Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6f8d-192">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)