---
title: Información sobre la configuración de los perfiles de AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Los perfiles de AutoPilot te ayudan a controlar Windows se instala en dispositivos de usuario. Los perfiles contienen configuraciones predeterminadas y opcionales, como omitir la instalación de Cortana.
ms.openlocfilehash: 86f8718131f0a0b93e18e65e39e02e7d65aded1a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578515"
---
# <a name="about-autopilot-profile-settings"></a>Información sobre la configuración de los perfiles de AutoPilot

## <a name="autopilot-profile-settings"></a>Configuración del perfil de AutoPilot

Puedes usar perfiles de AutoPilot para controlar cómo se Windows en dispositivos de usuario. Los perfiles contienen la siguiente configuración.
  
 **Características predeterminadas de AutoPilot (necesarias) que se establecen automáticamente:**
  
|**Valor**|**Descripción**|
|:-----|:-----|
|Omitir el registro de Cortana, OneDrive y OEM  <br/> |Omite la instalación de aplicaciones de consumidor como Cortana y los OneDrive. El usuario del dispositivo puede instalar estos más adelante siempre que el usuario sea un administrador local en el dispositivo. El registro del fabricante original se omite porque el dispositivo se administrará Microsoft 365 Empresa Premium.  <br/> |
|Experiencia de inicio de sesión con la marca de su empresa  <br/> |Si tu empresa tiene una página Agregar la marca de tu empresa [Microsoft 365](../admin/setup/customize-sign-in-page.md)inicio de sesión, el usuario del dispositivo tendrá esa experiencia al iniciar sesión.  <br/> |
|Inscripción automática de MDM con cuentas de AAD configuradas.  <br/> |La identidad de usuario la administrará Azure Active Directory y los usuarios iniciarán sesión en Windows y Microsoft 365 con sus Microsoft 365 Empresa Premium credenciales.  <br/> |
   
 **Configuración opcional:**
  
|**Valor**|**Descripción**|
|:-----|:-----|
|Omitir la configuración de privacidad (desactivado de forma predeterminada)  <br/> |Si esta opción está establecida en **On**, el usuario del dispositivo no verá el contrato de licencia para el dispositivo y se Windows la primera vez que inicia sesión.  <br/> |
|No permitir que el usuario se convierta en el administrador local  <br/> |Si esta opción está establecida en **On**, el usuario del dispositivo no podrá instalar ninguna aplicación personal, como Cortana.<br/> |
