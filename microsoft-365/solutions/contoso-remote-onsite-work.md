---
title: Respuesta COVID-19 de Contoso y soporte técnico para trabajos remotos y en el sitio
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda cómo ha respondido contoso Corporation al COVID-19 Pandemic y se ha diseñado su infraestructura de instalación y actualización de software para el trabajo remoto y en el sitio.
ms.openlocfilehash: 8e25b399d7acd2cb3486283623d29315eac9491e
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371776"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a><span data-ttu-id="32aa8-103">Respuesta COVID-19 de Contoso y soporte técnico para trabajos remotos y en el sitio</span><span class="sxs-lookup"><span data-stu-id="32aa8-103">Contoso's COVID-19 response and support for remote and onsite work</span></span>

<span data-ttu-id="32aa8-104">Contoso siempre ha admitido a sus trabajadores remotos que han tenido acceso a recursos locales a través de un servidor VPN central en la sede central de París.</span><span class="sxs-lookup"><span data-stu-id="32aa8-104">Contoso had always supported its remote workers, who accessed on-premises resources through a central VPN server in the Paris headquarters.</span></span> <span data-ttu-id="32aa8-105">Contoso ha emitido a todos los trabajadores remotos un portátil administrado.</span><span class="sxs-lookup"><span data-stu-id="32aa8-105">Contoso had issued all remote workers a managed laptop.</span></span> <span data-ttu-id="32aa8-106">Los trabajadores locales tenían una mezcla de equipos de escritorio y portátiles.</span><span class="sxs-lookup"><span data-stu-id="32aa8-106">On-premises workers had a mixture of desktop computers and laptops.</span></span>

## <a name="contosos-response-to-covid-19"></a><span data-ttu-id="32aa8-107">Respuesta de Contoso a COVID-19</span><span class="sxs-lookup"><span data-stu-id="32aa8-107">Contoso’s response to COVID-19</span></span>

<span data-ttu-id="32aa8-108">Con el comienzo del COVID-19 Pandemic, de repente todos los trabajadores básicos eran trabajadores remotos.</span><span class="sxs-lookup"><span data-stu-id="32aa8-108">With the onset of the COVID-19 pandemic, suddenly all but essential workers were remote workers.</span></span> <span data-ttu-id="32aa8-109">Contoso ha respondido cambiando su personal para trabajar desde casa y dirigir sus actividades principales a través del acceso remoto a recursos locales y en línea con los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32aa8-109">Contoso responded by shifting its workforce to work from home and conduct its primary activities through remote access to on-premises resources and online using Microsoft 365 cloud services.</span></span>

<span data-ttu-id="32aa8-110">Contoso tenía servidores VPN de acceso remoto en la oficina de la sede de París para admitir el 25% de su personal ya Remote, pero se ha movido rápidamente a escalabilidad vertical de su capacidad de acceso remoto para que admita el 90% de su personal.</span><span class="sxs-lookup"><span data-stu-id="32aa8-110">Contoso had remote access VPN servers in the Paris headquarters office to support the 25% of its already remote workforce, but quickly moved to scale up it's remote access capacity to support 90% of its workforce.</span></span> <span data-ttu-id="32aa8-111">Contoso implementó servidores VPN de acceso remoto en cada oficina satélite para que los trabajadores remotos usen un punto de entrada de cierre regional para obtener acceso a la intranet de contoso.</span><span class="sxs-lookup"><span data-stu-id="32aa8-111">Contoso deployed remote access VPN servers in each satellite office so that remote workers would use a regionally close entry point for access to the Contoso intranet.</span></span>

<span data-ttu-id="32aa8-112">Contoso también se actualizó la configuración de los clientes de VPN instalados en equipos portátiles, tabletas y teléfonos inteligentes para túneles divididos, de modo que el tráfico para el conjunto Optimize de los extremos de Office 365 omitió la conexión VPN y se envió directamente a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="32aa8-112">Contoso also updated the configuration of VPN clients installed on laptops, tablets, and smart phones for split tunneling so that traffic for the Optimize set of Office 365 endpoints bypassed the VPN connection and was sent directly over the internet.</span></span> <span data-ttu-id="32aa8-113">Para obtener más información, consulte [optimizar la conectividad de Office 365 para usuarios remotos mediante la tunelización dividida de VPN](../enterprise/microsoft-365-vpn-split-tunnel.md).</span><span class="sxs-lookup"><span data-stu-id="32aa8-113">For more information, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

<span data-ttu-id="32aa8-114">Esta es la configuración resultante con los dispositivos VPN instalados en la sede central de París y en cada una de las oficinas satélite.</span><span class="sxs-lookup"><span data-stu-id="32aa8-114">Here is the resulting configuration with VPN devices installed in the Paris headquarters and each of the satellite offices.</span></span> 

![Infraestructura de VPN de Contoso](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

<span data-ttu-id="32aa8-116">Un trabajador remoto con el cliente VPN instalado usa DNS para encontrar la oficina más cercana a la región y se conecta al dispositivo VPN instalado allí.</span><span class="sxs-lookup"><span data-stu-id="32aa8-116">A remote worker with the installed VPN client uses DNS to find the regionally closest office and connects to the VPN device installed there.</span></span> <span data-ttu-id="32aa8-117">Con la tunelización dividida, el tráfico a Microsoft 365 optimizar extremos se envía directamente a la ubicación de red de Microsoft 365 de la forma más cercana.</span><span class="sxs-lookup"><span data-stu-id="32aa8-117">With split tunneling, traffic to Microsoft 365 Optimize endpoints gets sent directly to the regionally closest Microsoft 365 network location.</span></span> <span data-ttu-id="32aa8-118">El resto del tráfico se envía a través de la conexión VPN al dispositivo VPN.</span><span class="sxs-lookup"><span data-stu-id="32aa8-118">All other traffic gets sent over the VPN connection to the VPN device.</span></span>

## <a name="contosos-support-for-remote-and-onsite-work"></a><span data-ttu-id="32aa8-119">Soporte de Contoso para trabajos remotos y en el sitio</span><span class="sxs-lookup"><span data-stu-id="32aa8-119">Contoso’s support for remote and onsite work</span></span>

<span data-ttu-id="32aa8-120">Una vez que se han realizado los cambios iniciales para admitir principalmente los trabajadores remotos durante los bloqueos regionales, contoso realizó cambios en la infraestructura para apoyar el trabajo remoto y en el sitio en el que un trabajador podría ser:</span><span class="sxs-lookup"><span data-stu-id="32aa8-120">After the initial changes were made to support mostly remote workers during regional lockdowns, Contoso made infrastructure changes to support remote and onsite work in which a worker could be:</span></span>

- <span data-ttu-id="32aa8-121">Siempre remoto.</span><span class="sxs-lookup"><span data-stu-id="32aa8-121">Always remote.</span></span>
- <span data-ttu-id="32aa8-122">Siempre local.</span><span class="sxs-lookup"><span data-stu-id="32aa8-122">Always on-premises.</span></span>
- <span data-ttu-id="32aa8-123">Una combinación de remoto y local.</span><span class="sxs-lookup"><span data-stu-id="32aa8-123">A combination of remote and on-premises.</span></span>

<span data-ttu-id="32aa8-124">Las características de identidad, seguridad y cumplimiento de Microsoft 365 están diseñadas para la confianza cero y para funcionar independientemente de la ubicación del usuario y de su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="32aa8-124">Microsoft 365 identity, security, and compliance features are designed for Zero Trust and to work regardless of the location of the user and their device.</span></span> <span data-ttu-id="32aa8-125">Para obtener más información, consulte [Zero Trust](https://www.microsoft.com/security/business/zero-trust).</span><span class="sxs-lookup"><span data-stu-id="32aa8-125">For more information, see [Zero Trust](https://www.microsoft.com/security/business/zero-trust).</span></span>

<span data-ttu-id="32aa8-126">Sin embargo, la administración de nuevas instalaciones y actualizaciones de software depende de la ubicación del dispositivo porque el software que se va a instalar puede provenir de un origen local o de Internet.</span><span class="sxs-lookup"><span data-stu-id="32aa8-126">However, managing new installs and updates of software is dependent on the location of the device because the software to install could come from an on-premises or an internet source.</span></span> <span data-ttu-id="32aa8-127">Los arquitectos de TI de Contoso diseñaron sus nuevas instalaciones y actualizan la infraestructura en función de la ubicación del dispositivo, en lugar del trabajo.</span><span class="sxs-lookup"><span data-stu-id="32aa8-127">Contoso IT architects designed their new installs and updates infrastructure based on the location of the device, rather than the worker.</span></span>

<span data-ttu-id="32aa8-128">Designó dos tipos de dispositivos: dedicado de forma local y móvil.</span><span class="sxs-lookup"><span data-stu-id="32aa8-128">They designated two types of devices: dedicated on-premises and roaming.</span></span>

### <a name="dedicated-on-premises"></a><span data-ttu-id="32aa8-129">Dedicado localmente</span><span class="sxs-lookup"><span data-stu-id="32aa8-129">Dedicated on-premises</span></span>

<span data-ttu-id="32aa8-130">Un dispositivo local dedicado es un equipo de escritorio o servidor que nunca sale de la intranet de Contoso y no tiene un cliente de VPN instalado.</span><span class="sxs-lookup"><span data-stu-id="32aa8-130">A dedicated on-premises device is a desktop or server computer that never leaves the Contoso intranet and does not have a VPN client installed.</span></span> <span data-ttu-id="32aa8-131">Estos dispositivos locales siguen usando Microsoft Endpoint Configuration Manager y sus puntos de distribución para instalaciones y actualizaciones de Windows 10, Microsoft 365 apps for Enterprise y el explorador perimetral.</span><span class="sxs-lookup"><span data-stu-id="32aa8-131">These on-premises devices continue to use Microsoft Endpoint Configuration Manager and its distribution points for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and the Edge browser.</span></span>

### <a name="roaming"></a><span data-ttu-id="32aa8-132">Movilidad</span><span class="sxs-lookup"><span data-stu-id="32aa8-132">Roaming</span></span>

<span data-ttu-id="32aa8-133">Un dispositivo móvil puede dejar la intranet de Contoso e incluye equipos portátiles emitidos a muchos trabajadores de Office y todos los trabajadores remotos y otros dispositivos de propiedad de la organización, como teléfonos inteligentes y tabletas con el cliente de VPN de Contoso instalado.</span><span class="sxs-lookup"><span data-stu-id="32aa8-133">A roaming device can leave the Contoso intranet and includes laptops issued to many office workers and all remote workers and other organization-owned devices such as smart phones and tablets with the Contoso VPN client installed.</span></span> 

<span data-ttu-id="32aa8-134">Como estos dispositivos se pueden conectar a Internet en cualquier momento, usan Intune u otros servicios basados en la nube para instalaciones y actualizaciones de Windows 10, Microsoft 365 apps for Enterprise y Edge.</span><span class="sxs-lookup"><span data-stu-id="32aa8-134">Because these devices can be connected to the Internet at any given time, they use Intune or other cloud-based services for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="32aa8-135">No usan los puntos de distribución existentes del administrador de configuración local.</span><span class="sxs-lookup"><span data-stu-id="32aa8-135">They do not use the existing on-premises Configuration Manager distribution points.</span></span>

<span data-ttu-id="32aa8-136">Esto significa que algunas de las instalaciones y actualizaciones del dispositivo móvil se realizarán a través de Internet mientras están locales y conectadas a la intranet.</span><span class="sxs-lookup"><span data-stu-id="32aa8-136">This means some of the installs and updates for roaming device will be done over the internet while they are on-premises and connected to the intranet.</span></span> <span data-ttu-id="32aa8-137">Pero los arquitectos de TI de Contoso decidieron que la simplicidad de la configuración era más importante que la optimización del ancho de banda de la intranet a Internet, sobre todo cuando la mayoría de los trabajadores remotos rara vez están conectados a la intranet.</span><span class="sxs-lookup"><span data-stu-id="32aa8-137">But Contoso IT architects decided that simplicity of configuration was more important than optimization of intranet bandwidth to the internet, especially when most remote workers are seldom connected to the intranet.</span></span>

<span data-ttu-id="32aa8-138">Esta es la infraestructura resultante.</span><span class="sxs-lookup"><span data-stu-id="32aa8-138">Here is the resulting infrastructure.</span></span>

![Contoso instala y actualiza la infraestructura](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

<span data-ttu-id="32aa8-140">El comportamiento de la instalación y la actualización se determina haciendo que las cuentas de equipo de los dispositivos sean miembros de uno de estos grupos:</span><span class="sxs-lookup"><span data-stu-id="32aa8-140">Install and update behavior is determined by making the computer accounts of devices a member of one of these groups:</span></span>

- <span data-ttu-id="32aa8-141">OnPremDevices</span><span class="sxs-lookup"><span data-stu-id="32aa8-141">OnPremDevices</span></span>

  <span data-ttu-id="32aa8-142">El cliente de Configuration Manager del dispositivo usa puntos de distribución para instalaciones y actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="32aa8-142">The Configuration Manager client on the device uses distribution points for installs and updates.</span></span>

- <span data-ttu-id="32aa8-143">RoamingDevices</span><span class="sxs-lookup"><span data-stu-id="32aa8-143">RoamingDevices</span></span>

  <span data-ttu-id="32aa8-144">Intune y otras opciones de configuración en el dispositivo especifican el uso de la red de Microsoft 365 para las instalaciones y actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="32aa8-144">Intune and other settings on the device specify the use of the Microsoft 365 network for installs and updates.</span></span>

## <a name="new-onboarding-process"></a><span data-ttu-id="32aa8-145">Nuevo proceso de incorporación</span><span class="sxs-lookup"><span data-stu-id="32aa8-145">New onboarding process</span></span>

<span data-ttu-id="32aa8-146">Para un nuevo dispositivo local dedicado emitido a un nuevo trabajador o para un nuevo servidor en un centro de proceso de trabajo, cuando el trabajador inicia sesión, el cliente de Configuration Manager en función de la pertenencia del dispositivo en el grupo OnPremDevices descarga e instala las actualizaciones más recientes para Windows 10, las aplicaciones de Microsoft 365 para empresas y el perímetro de los puntos de distribución del administrador de configuración local.</span><span class="sxs-lookup"><span data-stu-id="32aa8-146">For a new dedicated on-premises device issued to a new worker or for a new server in a datacenter, when the worker signs in, the Configuration Manager client based on the device's membership in the OnPremDevices group downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge from on-premises Configuration Manager distribution points.</span></span> <span data-ttu-id="32aa8-147">Una vez completado, el dispositivo local dedicado está listo para su uso y usa estos puntos de distribución para las actualizaciones en curso.</span><span class="sxs-lookup"><span data-stu-id="32aa8-147">When complete, the dedicated on-premises device is ready for use and uses these distribution points for ongoing updates.</span></span>

<span data-ttu-id="32aa8-148">Para un nuevo dispositivo remoto emitido a un nuevo trabajador, cuando el trabajador inicie sesión, el dispositivo, según su pertenencia al grupo RoamingDevices, se pone en contacto con el servicio en la nube de Intune y otros servicios y descarga e instala las actualizaciones más recientes para Windows 10, las aplicaciones de Microsoft 365 para empresas y Edge.</span><span class="sxs-lookup"><span data-stu-id="32aa8-148">For a new remote device issued to a new worker, when the worker signs in, the device, based on its membership in the RoamingDevices group, contacts the Intune cloud service and other services and downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="32aa8-149">Una vez completado, el dispositivo remoto está listo para su uso y usa el cliente VPN instalado para tener acceso a los recursos locales y a la red de Microsoft 365 para las actualizaciones continuas.</span><span class="sxs-lookup"><span data-stu-id="32aa8-149">When complete, the remote device is ready for use and uses the installed VPN client for access to on-premises resources and the Microsoft 365 network for ongoing updates.</span></span>

## <a name="next-step"></a><span data-ttu-id="32aa8-150">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="32aa8-150">Next step</span></span>

<span data-ttu-id="32aa8-151">[Permita a los trabajadores remotos](empower-people-to-work-remotely.md) de su organización.</span><span class="sxs-lookup"><span data-stu-id="32aa8-151">[Empower the remote workers](empower-people-to-work-remotely.md) in your organization.</span></span>