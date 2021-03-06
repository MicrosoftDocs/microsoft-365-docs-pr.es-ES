---
title: Información general del procesamiento de formularios
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Más información sobre el procesamiento de formularios en Microsoft SharePoint Syntex
ms.openlocfilehash: e3cf8298a2db9383e5b88dde737efc84e75c7f19
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222262"
---
# <a name="form-processing-overview"></a>Información general del procesamiento de formularios

 ![Generador de IA](../media/content-understanding/ai-builder.png)</br>

Microsoft SharePoint Syntex usa el procesamiento de formularios del [generador de IA](/ai-builder/overview) de Microsoft PowerApps para crear modelos en las bibliotecas de documentos de SharePoint.

Puede usar el procesamiento de formularios del generador de IA para crear modelos de IA que usan la tecnología de aprendizaje automático para identificar y extraer pares de valor-clave y datos de tabla de documentos estructurados o semiestructurados, como formularios y facturas.

La mayoría de las organizaciones suelen recibir facturas en grandes cantidades y de una gran variedad de orígenes, como correo, fax, correo electrónico, etc. Procesar estos documentos y añadirlos manualmente a una base de datos puede suponer un tiempo considerable. Mediante el uso de IA para extraer el texto, los pares clave o de valor y las tablas de los documentos, el procesamiento de formularios automatiza este proceso. 

> [!NOTE]
> Consulte la guía [Adopción de SharePoint Syntex: Guía de introducción](./adoption-getstarted.md) para obtener más información sobre ejemplos de escenarios de procesamiento de formularios.

Por ejemplo, puede crear un modelo de procesamiento de formularios que identifique todos los documentos de pedido de compra que se hayan cargado en la biblioteca de documentos. A partir de cada pedido de compra, puede extraer y mostrar datos específicos que sean importantes para usted, como el *Número de pedido de compra*, la *Fecha* o el *Coste total*.

![Vista de la biblioteca de documentos](../media/content-understanding/doc-lib-done.png)</br>  

Use archivos de ejemplo para entrenar el modelo y definir la información que se extrae del formulario. El diseño del documento viene se aprende al entrenar el modelo. Solo necesita cinco documentos de formulario para empezar. El generador de IA analizará los archivos de ejemplo para pares de clave y valor, y también puede identificar manualmente los que no se hayan detectado.  El generador de IA le permite probar la precisión de su modelo en los archivos de ejemplo.

Una vez que haya entrenado y publicado el modelo, el modelo crea un [flujo de Power Automate](/power-automate/getting-started). El flujo se ejecuta cuando se carga un archivo en la biblioteca de documentos de SharePoint y se extraen los datos identificados en el modelo. Los datos extraídos se mostrarán en columnas en la vista de la biblioteca de documentos del modelo.

Los administradores de Office 365 deben [habilitar el procesamiento de formularios](./set-up-content-understanding.md) para la biblioteca de documentos de SharePoint para que los usuarios puedan [crear un modelo de procesamiento de formularios](create-a-form-processing-model.md) en ella. Puede seleccionar los sitios durante la instalación o después de la misma, en la configuración de administración.

### <a name="file-limitations"></a>Limitaciones de archivos

Al usar modelos de procesamiento de formularios, asegúrese de tener en cuenta las [limitaciones específicas para el uso de archivos](/ai-builder/form-processing-model-requirements).

### <a name="multi-geo-environments"></a>Entornos de Multi-Geo

Al configurar SharePoint Syntex en un [entorno de Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md), solo puede configurarlo para usar el procesamiento de formularios en la ubicación central. Si quiere utilizar el procesamiento de formularios en una ubicación satélite, póngase en contacto con el Soporte técnico de Microsoft.






## <a name="see-also"></a>Vea también
  
[Documentación de Power Automate](/power-automate/)

[Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)

[Información general sobre la comprensión de documentos](document-understanding-overview.md)

[Aprendizaje: mejorar el rendimiento empresarial con el generador de IA](/learn/paths/improve-business-performance-ai-builder/?source=learn)