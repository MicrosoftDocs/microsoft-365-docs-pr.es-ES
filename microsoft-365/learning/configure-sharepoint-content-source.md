---
title: 'Próximamente: Configure SharePoint como un origen de contenido de aprendizaje para Microsoft Viva Learning (versión preliminar)'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Obtenga información sobre cómo configurar SharePoint como un origen de contenido de aprendizaje para Microsoft Viva Learning (versión preliminar).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: da75ec0573519ed73507994afeac995c0461de0c
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52101089"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a>Próximamente: Configure SharePoint como un origen de contenido de aprendizaje para Microsoft Viva Learning (versión preliminar)

> [!NOTE]
> La información de este artículo se refiere a un producto de vista previa que puede modificarse considerablemente antes de su lanzamiento comercial. 

Puede configurar el SharePoint como un origen de contenido de aprendizaje para que el propio contenido de su organización esté disponible en Viva Learning (versión preliminar).

## <a name="overview"></a>Información general

El administrador del conocimiento (o administrador global) proporciona una dirección URL del sitio a la que el servicio de aprendizaje puede crear una ubicación centralizada vacía (el repositorio de contenido de la aplicación de aprendizaje) en forma de una lista de SharePoint estructurada. La organización puede usar esta lista para hospedar vínculos a carpetas entre SharePoint que contienen contenido de aprendizaje. Los administradores son responsables de recopilar y comisariar una lista de direcciones URL de carpetas. Estas carpetas solo deben incluir contenido que pueda estar disponible en Viva Learning (versión preliminar).

Viva Learning (versión preliminar) admite los siguientes tipos de documentos:

- Word, PowerPoint, Excel, PDF
- Audio (.m4a)
- Vídeo (.mov, .mp4, .avi)

Para obtener más información, consulte [la SharePoint online](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498). 

## <a name="permissions"></a>Permisos

Las direcciones URL de carpetas de biblioteca de documentos se pueden recopilar SharePoint sitio de la organización. Viva Learning (versión preliminar) sigue todos los permisos de contenido existentes. Por lo tanto, solo el contenido para el que un usuario tiene permiso de acceso es visible y se puede buscar en Viva Learning (versión preliminar). Cualquier contenido dentro de estas carpetas se puede buscar, pero solo se puede usar el contenido al que el empleado individual tenga permisos.

Actualmente, no se admite la eliminación de contenido del repositorio de la organización.

Para quitar contenido que no se ha presentado de forma involuntarla, siga estos pasos:

1.  Para restringir el acceso a la biblioteca de documentos, seleccione la **opción Mostrar acciones** y, a continuación, seleccione Administrar **acceso**.
     
     ![Página de biblioteca de documentos SharePoint muestra la opción Mostrar acciones con Administrar acceso con alta puntuación.](../media/learning/learning-sharepoint-permissions2.png)

2.  Elimine el documento original dentro de la biblioteca de documentos.

Para obtener más información, vea [Sharing and permissions in the SharePoint modern experience](/sharepoint/modern-experience-sharing-permissions). 

## <a name="learning-service"></a>Servicio de aprendizaje

El servicio de aprendizaje usa las direcciones URL de carpeta proporcionadas para obtener metadatos de todo el contenido almacenado en esas carpetas. En un plazo de 24 horas después de proporcionar la dirección URL de carpeta en el repositorio centralizado, los empleados pueden buscar y usar el contenido de la organización en Viva Learning (versión preliminar). Todos los cambios en el contenido, incluidos los metadatos y permisos actualizados, también se aplicarán en el Servicio de aprendizaje en un plazo de 24 horas.

## <a name="configure-sharepoint-as-a-source"></a>Configurar SharePoint como origen

Debe ser un administrador Microsoft 365 global, SharePoint administrador o administrador de conocimientos para realizar estas tareas.

Para configurar SharePoint como orígenes de contenido de aprendizaje en para Viva Learning (versión preliminar), siga estos pasos:

1.  En la navegación izquierda del centro Microsoft 365 administración, vaya a **Configuración**  >  **configuración de la organización.**
 
2.  En la **página Configuración de** la organización, en la pestaña **Servicios,** seleccione **Aplicación de aprendizaje (versión preliminar).**

     ![Configuración en el Centro Microsoft 365 administración que muestra Viva Learning en la lista.](../media/learning/learning-sharepoint-configure1.png)

3.  En el panel Aplicación de aprendizaje **(versión** preliminar), en SharePoint, proporciona la dirección URL del sitio al sitio SharePoint donde desea que Viva Learning cree un repositorio centralizado.

     ![Panel de aprendizaje del centro Microsoft 365 administración que muestra SharePoint seleccionado.](../media/learning/learning-sharepoint-configure2.png)

4.  Una SharePoint se crea automáticamente en el sitio SharePoint proporcionado.

     ![Lista de SharePoint creada recientemente en el SharePoint web.](../media/learning/learning-sharepoint-configure3.png)

     En la navegación izquierda del sitio SharePoint, seleccione **Contenido** del sitio Aprendizaje del repositorio de contenido  >  **de la aplicación**. 

     ![SharePoint que muestra la navegación por el contenido del sitio y la sección Repositorio de contenido de la aplicación de aprendizaje.](../media/learning/learning-sharepoint-configure4.png) 

5. En la **página Repositorio de contenido de** la aplicación de aprendizaje, rellene la lista SharePoint con direcciones URL a las carpetas de contenido de aprendizaje.

   1. Seleccione **Nuevo** para ver el **panel Nuevo** elemento. 

       ![Página Repositorio de contenido de aprendizaje SharePoint muestra la opción Nuevo.](../media/learning/learning-sharepoint-configure5.png)
 
   2. En el **panel Nuevo elemento,** en el **campo Título,** agregue un nombre de directorio de su elección. En el **campo Dirección URL de** carpeta, agregue la dirección URL a la carpeta de contenido de aprendizaje. Haga clic en **Guardar**.

       ![Nuevo panel de elementos en SharePoint que muestra los campos De título y Dirección URL de carpeta.](../media/learning/learning-sharepoint-configure6.png)

   3. La **página Repositorio de contenido de** la aplicación de aprendizaje se actualiza con el nuevo contenido de aprendizaje.

       ![Página repositorio de contenido de aprendizaje en SharePoint muestra la información actualizada.](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> Para permitir un acceso más amplio al repositorio de contenido de la aplicación de aprendizaje, pronto estará disponible un vínculo a la lista en la interfaz de Viva Learning (versión preliminar), donde los usuarios pueden solicitar acceso y, en última instancia, ayudar a rellenar la lista. Los propietarios del sitio y los administradores globales tendrán que conceder acceso a la lista. El acceso es específico de la lista únicamente y no se aplica al sitio donde se almacena la lista. Para obtener más información, [vea Proporcionar el contenido](#provide-your-own-organizations-content) de su propia organización más adelante en este artículo.

### <a name="folder-url-document-library-curation"></a>Curación de la biblioteca de documentos de dirección URL de carpeta

Los metadatos predeterminados (como la fecha de modificación, creados por, el nombre del documento, el tipo de contenido y el nombre de la organización) se extraen automáticamente en Viva Learning (versión preliminar) mediante la API de Microsoft Graph.
 
Para mejorar la detección general y la relevancia de búsqueda del contenido, se recomienda agregar una **columna** Descripción.

Para agregar una **columna Description** a la página de la biblioteca de documentos, siga estos pasos:

1.  En la **página Documentos,** seleccione **Agregar columna**.

2. Seleccione la **opción Mostrar acciones** y, a continuación, seleccione Línea única de **texto**.

     ![Página Documentos en SharePoint que muestra las opciones Mostrar acciones con una sola línea de texto resaltada.](../media/learning/learning-sharepoint-curation1.png)

3. En el panel **Crear una columna,** en el **campo Nombre,** agregue un nombre descriptivo para la columna. Haga clic en **Guardar**.

     ![Cree un panel de columnas en SharePoint que muestre el nombre y otros campos.](../media/learning/learning-sharepoint-curation2.png)
 
4. En la **página Documentos,** en la **columna Descripción,** agregue descripciones personalizadas para cada elemento. Si no se proporciona ninguna descripción, Viva Learning (versión preliminar) proporcionará un mensaje predeterminado que resalta el contenido como de su propia SharePoint biblioteca. 

     ![Página Documentos de SharePoint que muestra las descripciones de la columna Descripción.](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a>Proporcionar el contenido de su propia organización

Los administradores de conocimientos pueden acceder al repositorio de contenido de aplicaciones de aprendizaje de su organización en SharePoint, donde pueden proporcionar referencias a bibliotecas de documentos entre organizaciones. El contenido de estas bibliotecas aparecerá como contenido de aprendizaje en Viva Learning (versión preliminar).

1. En Viva Learning (versión preliminar), seleccione **Más opciones** (**...**) y, a continuación, **seleccione Configuración**.

     ![SharePoint de biblioteca que muestra la opción Más opciones y Configuración.](../media/learning/learning-sharepoint-library-1.png)
     
2. En **Configuración**, seleccione **Permisos**.

     ![Configuración página de opciones en SharePoint muestra las opciones Permisos y Comprobar acceso.](../media/learning/learning-sharepoint-library-2.png)

3. Seleccione **Comprobar el acceso** para conectarse a la biblioteca centralizada de la organización.
     