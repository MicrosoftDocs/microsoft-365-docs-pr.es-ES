---
title: Crear un certificado de APNs para dispositivos iOS
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Administrar dispositivos iOS en la movilidad y la seguridad básicas.
ms.openlocfilehash: 8b41c1c6c891a5d6cb98a6a381c65aa0310a1761
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337099"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="47678-103">Crear un certificado de APNs para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="47678-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="47678-104">Para administrar dispositivos iOS como iPad y iPhone en Basic Mobility and Security, cree un certificado de APNs.</span><span class="sxs-lookup"><span data-stu-id="47678-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="47678-105">Inicie sesión en Microsoft 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="47678-105">Sign in to Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="47678-106">En el explorador, escriba  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="47678-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>
    
3. <span data-ttu-id="47678-107">Seleccione  **Data loss prevention**   >  **Administración de dispositivos**de prevención de pérdida de datos y elija **certificado de APNs para dispositivos iOS**.</span><span class="sxs-lookup"><span data-stu-id="47678-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>    

4. <span data-ttu-id="47678-108">En la página Configuración del certificado de notificación de inserción de Apple, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="47678-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>
    
5. <span data-ttu-id="47678-109">Seleccione descargar el archivo CSR y guardar la solicitud de firma de certificado en algún lugar del equipo que recuerde.</span><span class="sxs-lookup"><span data-stu-id="47678-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="47678-110">Seleccione  **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="47678-110">Select  **Next**.</span></span>
    
6. <span data-ttu-id="47678-111">En la página crear un certificado de APNs:</span><span class="sxs-lookup"><span data-stu-id="47678-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="47678-112">Seleccione portal de APNS de Apple para abrir el portal de certificados push de Apple.</span><span class="sxs-lookup"><span data-stu-id="47678-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
    
    2. <span data-ttu-id="47678-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="47678-113">Sign in with an Apple ID.</span></span>   

    >[!IMPORTANT]
    ><span data-ttu-id="47678-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="47678-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="47678-116">Seleccione  **crear un certificado**   y acepte los términos de uso.</span><span class="sxs-lookup"><span data-stu-id="47678-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>
    
    4. <span data-ttu-id="47678-117">Vaya a la solicitud de firma de certificado que descargó en el equipo de Microsoft 365 y seleccione **cargar**.</span><span class="sxs-lookup"><span data-stu-id="47678-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>
    
        <span data-ttu-id="47678-118">Descargue el certificado de APNs creado por el portal de certificados push de Apple en su equipo.</span><span class="sxs-lookup"><span data-stu-id="47678-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>
    
       >[!TIP]
       ><span data-ttu-id="47678-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="47678-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="47678-120">Vuelva a Microsoft 365 y seleccione **siguiente**   para ir a la página  **cargar certificado de APNS**   .</span><span class="sxs-lookup"><span data-stu-id="47678-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>
    
8. <span data-ttu-id="47678-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="47678-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
9. <span data-ttu-id="47678-122">Seleccione  **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="47678-122">Select  **Finish**.</span></span>
    
<span data-ttu-id="47678-123">Para completar la configuración, vuelva al centro de cumplimiento de & de seguridad > **directivas de seguridad**   >  **Administración de dispositivos administración**de la   >  **configuración**.</span><span class="sxs-lookup"><span data-stu-id="47678-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>