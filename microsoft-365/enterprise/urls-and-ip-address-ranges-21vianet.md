---
title: Direcciones URL e intervalos de direcciones IP para Office 365 operado por 21Vianet
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/29/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- GMA150
- GPA150
- GEA150
ms.assetid: 5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
description: En este artículo se enumeran las direcciones URL y los intervalos de direcciones IP Office 365 cuando 21Vianet lo opera en China.
hideEdit: true
ms.openlocfilehash: 80d9dd6626214215a4d84273297f881441992f14
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925198"
---
# <a name="urls-and-ip-address-ranges-for-office-365-operated-by-21vianet"></a>Direcciones URL e intervalos de direcciones IP para Office 365 operado por 21Vianet

 *Hace referencia a Office 365 operado por 21Vianet: administración de pequeña empresa, Office 365 operado por 21Vianet: administración*

**Resumen**: los siguientes puntos de conexión (FQDN, puertos, direcciones URL, IPv4 y prefijos de IPv6) se aplican a Office 365 operado por 21Vianet y están diseñados para ofrecer servicios de productividad para las organizaciones que usan solo estos planes.
  
 **Puntos de conexión de Office 365:** [mundial (incluido GCC)](urls-and-ip-address-ranges.md)  | *Office 365 operado por 21Vianet* | [Office 365 Germany](microsoft-365-germany-endpoints.md)  |  [Office 365 Administración Pública de Estados Unidos (DoD)](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 Administración Pública de Estados Unidos (GCC High)](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
**Last updated:** 03/29/2021 - ![ RSS Change Log ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [subscription](https://endpoints.office.com/version/China?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)

**Descargue:** todos los destinos obligatorios y opcionales en una lista de [formato JSON](https://endpoints.office.com/endpoints/China?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).

Comience por [Administrar los puntos de conexión de Office 365](managing-office-365-endpoints.md) si desea entender nuestras recomendaciones para administrar la conectividad de red con estos datos. Los datos de los puntos de conexión se actualizan al principio de cada mes, según sea necesario, con las nuevas direcciones IP y URL publicadas 30 días antes de su activación. Esto permite que los clientes que todavía no hayan automatizado las actualizaciones completen el proceso antes de que se requiera una nueva conectividad. También podrían actualizarse los puntos de conexión durante el mes, si fuera necesario, para gestionar la canalización del soporte técnico, los incidentes de seguridad u otros requisitos operativos inmediatos. Los datos que aparecen en la página siguiente se generan desde los servicios web basados en REST. Si usa un dispositivo de red o un script para obtener acceso a estos datos, vaya directamente al [Servicio web](microsoft-365-ip-web-service.md).

Los siguientes datos de puntos de conexión enumeran los requisitos para la conectividad del equipo de un usuario a Office 365. No incluye las conexiones de red de Microsoft a una red de clientes, a veces denominadas híbridas o conexiones de red de entrada.

Los puntos de conexión se agrupan en cuatro áreas de servicio. Las tres primeras se pueden seleccionar por separado para la conectividad; la cuarta área de servicio es una dependencia común (denominada de Microsoft 365 Common y Office) y debe disponer de conectividad de red en todo momento.

Estas son columnas de datos que se muestran:

- **ID**: el número de identificación de la fila, también conocido como un conjunto de puntos de conexión. Este identificador es el mismo que devuelve el servicio web para el conjunto de puntos de conexión.

- **Categoría**: muestra si el conjunto de puntos de conexión se clasifica como "Optimizar", "Permitir" o "Predeterminado". Puede leer acerca de estas categorías y encontrar indicaciones para su administración en [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md). Esta columna también muestra los conjuntos de puntos de conexión que deben tener conectividad de red. Para los conjuntos de puntos de conexión que no necesitan conectividad de red, le proporcionamos notas en este campo para indicar qué funcionalidad faltaría si se bloqueara el conjunto de puntos de conexión. Si va a excluir un área de servicio completa, los conjuntos de puntos de conexión enumerados como necesarios no necesitan conectividad.

- **EMERGENCIA**: aparece como **Sí** si el conjunto de puntos de conexión se admite en Azure ExpressRoute con prefijos de ruta de Office 365. La comunidad de BGP que incluye los prefijos de ruta que aparecen se alinea con el área de servicio que se muestra. Si EMERGENCIA aparece como **No**, esto significa que ExpressRoute no es compatible con este conjunto de puntos de conexión. Sin embargo, no se debe dar por hecho que no se anuncia ninguna ruta para un conjunto de puntos de conexión cuando EMERGENCIA se establezca como **No**.

- **Direcciones**: enumera los FQDN o nombres de dominio con caracteres comodín y los intervalos de direcciones IP para el conjunto de puntos de conexión. Tenga en cuenta que un intervalo de direcciones IP está en formato CIDR y puede incluir varias direcciones IP individuales en la red especificada.
 
- **Puertos**: muestra los puertos TCP o UDP que se combinan con las direcciones para formar el punto de conexión de la red. Es posible que observe repeticiones de intervalos de direcciones IP cuando se enumeran diferentes puertos.

[!INCLUDE [Office 365 operated by 21Vianet endpoints](../includes/office-365-operated-by-21vianet-endpoints.md)]