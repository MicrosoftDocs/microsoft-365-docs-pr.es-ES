---
title: Eliminación de datos de SharePoint Online de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo funciona la eliminación de datos en SharePoint Online, como el lugar donde se almacena el contenido eliminado y durante cuánto tiempo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5cea1b797d078f6ae627700b28c6fb90cc005637
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694057"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a>Eliminación de datos de SharePoint Online en Microsoft 365

SharePoint Online almacena objetos como código abstracto dentro de las bases de datos de la aplicación. Cuando un usuario carga un archivo en SharePoint Online, ese archivo se desensambla y se traduce a código de aplicación y se almacena en varias tablas en varias bases de datos. En SharePoint Online, todo el contenido que carga un cliente se divide en fragmentos, cifrados (potencialmente con varias claves AES 256-bit), y distribuidos en el centro de datos. Para obtener información específica sobre el proceso de fragmentación y cifrado, vea [cifrado en la nube de Microsoft](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview). 

En SharePoint Online, los elementos se conservan durante 93 días desde el momento en que los elimina de su ubicación original. Permanecen en la papelera de reciclaje del sitio todo el tiempo, a menos que alguien las elimine o vacíe dicha papelera de reciclaje. En ese caso, los elementos se dirigen a la papelera de reciclaje de la colección de sitios, donde permanecen durante el resto de los 93 días. Para obtener información sobre cómo restaurar elementos eliminados, vea [Restaurar elementos en la papelera de reciclaje de un sitio de SharePoint](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) y [Restaurar elementos eliminados de la papelera de reciclaje de la colección de sitios](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b). El tiempo de retención de la papelera de reciclaje no se puede configurar en SharePoint Online.

Cuando se elimina una colección de sitios, también se elimina la jerarquía de los sitios de la colección y todo el contenido de los mismos:

- Documentos y bibliotecas de documentos
- Listas y datos de lista
- Opciones de configuración del sitio
- Información de roles y seguridad relacionada con el sitio o sus subsitios
- Subsitios del sitio web de nivel superior, su contenido e información de usuario

Si elimina por error una colección de sitios, puede restaurarla un administrador global o de SharePoint con el centro de administración de SharePoint.

Las colecciones de sitios eliminadas se conservan durante 93 días. Después de 93 días, los sitios y todo su contenido y configuración se eliminan de forma permanente, incluidas las listas, las bibliotecas, las páginas y los subsitios.

La eliminación de hardware se produce cuando un usuario depura elementos eliminados de la papelera de reciclaje de la colección de sitios, cuando expiran los períodos de retención y copia de seguridad, o cuando un administrador elimina permanentemente una colección de sitios con el [cmdlet Remove-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). Cuando un usuario elimina (elimina o purga permanentemente) contenido de SharePoint Online, también se eliminan todas las claves de cifrado de los fragmentos eliminados. Los bloques de los discos que anteriormente almacenaban los fragmentos eliminados se marcan como no usados y disponibles para volver a usarlos.