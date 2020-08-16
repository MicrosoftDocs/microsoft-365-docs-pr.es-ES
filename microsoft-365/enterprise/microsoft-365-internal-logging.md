---
title: Registro interno de Microsoft 365 para ingeniería de Microsoft 365
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
f1.keywords:
- NOCSH
description: En este artículo, encontrará una explicación de cómo funciona el registro interno para Microsoft 365 Engineering Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b4c4b1db876a6b68ec852adbbd51afe7386a1855
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696601"
---
# <a name="internal-logging-for-microsoft-365-engineering"></a>Registro interno para Microsoft 365 Engineering

Además de los datos de registro y eventos disponibles para los clientes, también hay un sistema de recopilación de datos de registro interna que está disponible para los ingenieros de Microsoft 365 en Microsoft. Se cargan muchos tipos diferentes de datos de registro de los servidores de Microsoft 365 en un servicio informático interno de gran tamaño denominado cosmos. Cada equipo de servicio carga los registros de auditoría desde sus servidores respectivos a la base de datos cosmos para agregación y análisis. Esta transferencia de datos se produce en una conexión TLS validada por FIPS 140-2 en puertos y protocolos aprobados específicamente mediante una herramienta de automatización patentada llamada Office Data Loader (ODL). Las herramientas usadas en Microsoft 365 para recopilar y procesar registros de auditoría no permiten cambios permanentes o irreversibles en el contenido del registro de auditoría original o el pedido de tiempo.

Los equipos de servicios usan cosmos como repositorio centralizado para realizar un análisis del uso de la aplicación, medir el rendimiento del sistema y el funcionamiento y buscar anomalías y patrones que puedan indicar problemas o problemas de seguridad. Cada equipo de servicio carga una línea base de registros en cosmos, según lo que quiera analizar, que a menudo incluyen:

- Registros de eventos
- Registros de AppLocker
- Datos de rendimiento
- Datos de System Center
- Registros de detalles de llamadas
- Datos de la calidad de la experiencia
- Registros del servidor Web de IIS
- Registros de SQL Server
- Datos de syslog
- Registros de auditoría de seguridad

Antes de cargar datos en cosmos, la aplicación ODL usa un servicio de limpieza para ofuscar cualquier campo que contenga datos de clientes, como información de inquilinos e información de identificación del usuario final, y reemplazar los campos con un valor hash. Los registros hash y anonimizan se reescriben y, a continuación, se cargan en cosmos. Los equipos de servicio ejecutan consultas en el ámbito con sus datos en cosmos para obtener correlación, alertas e informes. El período de retención de datos del registro de auditoría en cosmos está determinado por los equipos de servicio; la mayoría de los datos del registro de auditoría se conservan durante 90 días o más para admitir investigaciones de incidentes de seguridad y para cumplir con los requisitos de retención de normativas.

El acceso a los datos de Microsoft 365 almacenados en cosmos está restringido al personal autorizado. Microsoft restringe la administración de la funcionalidad de auditoría al subconjunto limitado de miembros del equipo de servicio que son responsables de la funcionalidad de auditoría. Estos miembros del equipo no tienen la capacidad de modificar o eliminar datos de Cosmos, y todos los cambios en los mecanismos de registro para cosmos se registran y auditan.

Cada equipo de servicio tiene acceso a sus datos de registro para su análisis mediante la autorización de determinadas aplicaciones para realizar análisis específicos. Por ejemplo, el equipo de seguridad 365 de Microsoft usa datos de Cosmos a través de un analizador de registro de eventos de propietario para correlacionar, alertar y generar informes que requieren acción en el entorno de producción Microsoft 365. Los informes de estos datos se usan para corregir las vulnerabilidades y para mejorar el rendimiento general del servicio. Si un informe o alerta específico requiere más investigación, el personal de servicio puede solicitar que los datos se importen de nuevo en el servicio Microsoft 365. Dado que el registro específico que se importa de Cosmos está en cifrado y el personal de servicio no tiene acceso a las claves de descifrado, el registro de destino se pasa mediante programación a través de un servicio de descifrado que devuelve los resultados con ámbito al personal de servicio autorizado. Todas las vulnerabilidades encontradas en este ejercicio se notifican y se escalan con los canales de administración de incidentes de seguridad estándar de Microsoft.