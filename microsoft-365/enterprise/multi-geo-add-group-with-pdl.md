---
title: Crear un grupo de 365 de Microsoft con un PDL específico
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: Obtenga información sobre cómo crear un grupo de Microsoft 365 con una ubicación de datos preferida especificada en un entorno multigeográfico.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906d0b4881dd69bbf47cbb536c6c448a1a4f611
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693943"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a>Crear un grupo de 365 de Microsoft con un PDL específico

Cuando los usuarios de un entorno multigeográfico crean un grupo de Microsoft 365, la ubicación de datos preferida del grupo se establece automáticamente en la del usuario. Los administradores globales, de SharePoint y de Exchange pueden crear grupos en cualquier región que seleccionen. 

Si necesita crear un grupo con un PDL específico, puede hacerlo desde el Centro de administración de SharePoint o a través del cmdlet New-UnifiedGroup de Exchange Online de Microsoft PowerShell. Al hacerlo, tanto el buzón del grupo como el sitio de SharePoint asociado con el grupo se aprovisionarán en el PDL especificado.

Para crear un grupo de 365 de Microsoft con el PDL que especifique, vaya al centro de administración de SharePoint en la ubicación geográfica en la que desea crear el sitio de grupo.

Por ejemplo:

Si desea crear un sitio de grupo en su ubicación de Australia, puede ir a https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement

1. Seleccione **+ Crear**.
2. Siga el proceso para crear un sitio de grupo.

El sitio de grupo se aprovisionará en la ubicación geográfica correspondiente al Centro de administración de SharePoint desde el que haya iniciado la solicitud de creación de sitios. 

Usar Exchange PowerShell 

Conéctese a Exchange Online PowerShell y pase el parámetro *-MailBoxRegion* con el código de ubicación geográfica.

Por ejemplo: 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Captura de pantalla del cmdlet de PowerShell New-UnifiedGroup con la sintaxis](../media/multi-geo-new-group-with-pdl-powershell.png)

Tenga en cuenta que el aprovisionamiento de sitios de grupo de SharePoint se realiza a petición. El sitio se aprovisionará la primera vez que un propietario o miembro del grupo intente acceder a él.

## <a name="geo-location-codes"></a>Códigos de ubicación geográfica

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>Temas relacionados

[Conectarse a Exchange Online mediante PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)