---
title: Plan de fin de soporte de Project Server 2010
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
description: El soporte técnico finaliza para Project Server 2010 finaliza el 13 de abril de 2021. Use este artículo como guía para actualizar a Project online o a una versión más reciente de Project Server local.
ms.openlocfilehash: e20c8752b088b783f622fabf30302bbb8d4b8975
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696574"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Plan de final del soporte técnico de Project Server 2010

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*

Project Server 2010 se desplazará al final del soporte técnico el **13 de abril de 2021**. Esta fecha se ha ampliado desde la fecha de finalización de soporte previa del 13 de octubre de 2020. Si actualmente usa Project Server 2010, tenga en cuenta que estos otros productos relacionados tienen las siguientes fechas de fin de soporte:
  
| Producto |Fecha de finalización del soporte técnico|
|:-----|:-----|
|Proyecto 2010 estándar <br/> |13 de octubre de 2020  <br/> |
|Proyecto 2010 Professional  <br/> |13 de octubre de 2020  <br/> |

   
Para obtener más información acerca de los servidores de Office 2010 que alcanzan la finalización del soporte, consulte [upgrade from office 2010 Servers and Client Products](plan-upgrade-previous-versions-office.md).
  
## <a name="what-does-end-of-support-mean"></a>¿Qué significa el fin de soporte?

Project Server, al igual que casi todos los productos de Microsoft, tiene un ciclo de vida de soporte técnico durante el cual ofrecemos nuevas características, correcciones de errores y actualizaciones de seguridad. Este ciclo de vida suele durar 10 años a partir de la fecha de lanzamiento inicial del producto y el final de este ciclo de vida se conoce como el final del soporte técnico del producto. Cuando Project Server 2010 llegue a su fin de soporte el 13 de abril de 2021, Microsoft dejará de proporcionar:
  
- Soporte técnico para los problemas que pueden surgir.
    
- Correcciones de errores para problemas detectados y que pueden afectar a la estabilidad y la usabilidad del servidor.
    
- Revisiones de seguridad para las vulnerabilidades detectadas y que pueden hacer que el servidor sea vulnerable a las infracciones de seguridad.
    
- Las actualizaciones de zona horaria.
    
La instalación de Project Server 2010 seguirá ejecutándose después de esta fecha. Sin embargo, debido a los cambios mencionados anteriormente, se recomienda encarecidamente que migre de Project Server 2010 lo antes posible.
  
## <a name="what-are-my-options"></a>¿Qué opciones tengo?

Si usa Project Server 2010, debe explorar las opciones de migración, que son:
  
- Migrar a Project online
    
- Migre a una versión local más reciente de Project Server (preferiblemente Project Server 2019).

Estas son las dos rutas que puede realizar para evitar la finalización de la compatibilidad con Project Server 2010.

![Rutas de actualización de Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

    


|**¿Por qué preferiría migrar a Project Server 2019?**|**¿Por qué preferiría migrar a Project online?**|
|:-----|:-----|
|Las reglas de negocios delimitan el funcionamiento de mi empresa en la nube.  <br/>  Necesito el control de las actualizaciones de mi entorno.  <br/> | Tengo usuarios móviles o remotos.  <br/>  Los costos de migración de los servidores locales son una gran preocupación (hardware, software, horas y esfuerzo de implementación, etc.).  <br/>  Después de la migración, los costos de mantenimiento de mi entorno son una gran preocupación (por ejemplo, actualizaciones automáticas, tiempo de actividad garantizado, etc.).  <br/>  |

   
> [!NOTE]
> Para obtener más información acerca de las opciones para mover desde los servidores de Office 2010, vea [recursos para ayudarle a actualizar desde office 2010 servidores y clientes](upgrade-from-office-2010-servers-and-products.md). Tenga en cuenta que Project Server no admite una configuración híbrida, ya que Project Server y Project online no pueden compartir el mismo grupo de recursos. 

### <a name="what-are-my-options-for-project-client"></a>¿Cuáles son mis opciones para el cliente de Project?
Si usa Project Professional 2010 o Project Standard 2010 y desea explorar las opciones de migración, tiene la opción de:
- Pasar a una versión más reciente de Project Professional o Project Standard.
- Pasar a una solución en línea, como Project online o Project para la Web.
 
#### <a name="moving-to-a-newer-version-of-project-client"></a>Pasar a una versión más reciente del cliente de Project

Si va a migrar desde Project Standard 2010, puede migrar a una versión más reciente de Project Standard (Project Standard 2016 o Project Standard 2019).  Le recomendamos que se mueva a la versión más reciente para aprovechar las características y funciones más recientes. Además, la migración a una versión menos actual (Project Standard 2016) significa que tendrá que migrar desde esta versión antes de que aparezca su fecha de finalización de soporte técnico.

De forma similar, si va a migrar desde Project Professional 2010, puede optar por migrar a una versión más reciente (Project Professional 2019 o Project Professional 2016). Se recomienda cambiar a la versión más reciente si es posible.  Si usa Project Professional para conectarse a Project Server, asegúrese de migrar a una versión de Project Professional que sea compatible para conectarse con la versión de Project Server que está usando.

Project Professional 2010 los usuarios también pueden elegir migrar al cliente de escritorio de Project online. Se trata de una versión basada en suscripciones de Project Professional 2019 y se incluye en las suscripciones de Project Plan 3 y Project Plan 5. 

#### <a name="moving-to-an-online-solution"></a>Cambio a una solución en línea

También puede optar por migrar desde Project Professional 2010 o Project Standard 2010 a soluciones en línea basadas en la suscripción de Project. El plan de proyecto 3 y el plan 5 incluyen Project online y la última oferta [de nube, Project para la web](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1). Ambos ofrecen una serie de nuevas características y ventajas que merece la pena explorar.

Para obtener más información acerca de las características incluidas en ambos, así como las licencias de plan de proyecto incluidas en, vea la [Descripción del servicio de Microsoft Project](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description).



  
## <a name="important-considerations-you-need-to-make-when-planning-to-migrate-from-project-server-2010"></a>Consideraciones importantes que debe tener en cuenta al planear la migración desde Project Server 2010

Debe tener en cuenta lo siguiente al planear la migración desde Project Server 2010:
  
- **Obtener ayuda de un proveedor de soluciones de Microsoft** : la actualización desde Project Server 2010 puede ser un reto y requiere gran parte de la preparación y la planeación. Puede ser especialmente difícil si no es el que se va a instalar y configurar originalmente Project Server 2010. Afortunadamente, hay proveedores de soluciones de Microsoft que puede pasar a la persona que lo hace por un testamento vital, independientemente de si planea migrar a Project Server 2019 o a Project online. Puede buscar un proveedor de soluciones de Microsoft para ayudarle con la migración en el [centro de Microsoft Solution Provider](https://go.microsoft.com/fwlink/p/?linkid=841249). 
    
- **Planeación de las personalizaciones** : tenga en cuenta que muchas de las personalizaciones que ha trabajado en el entorno de project Server 2010 podrían no funcionar al migrar a project Server 2019 o a Project online. Existen grandes diferencias en la arquitectura de Project Server entre versiones, así como los sistemas operativos, los servidores de bases de datos y los exploradores Web de cliente que se admiten para trabajar con la versión más reciente. Disponer de un plan sobre cómo probar o volver a crear las personalizaciones según sea necesario en el nuevo entorno. La planeación de la actualización también será una buena oportunidad para comprobar si realmente se necesita una personalización específica mientras avanza. [Crear un plan de personalizaciones actuales durante la actualización a SharePoint 2013 tiene una]( https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013) gran información general sobre la evaluación y la planeación de las personalizaciones actuales durante la actualización. 
    
- La planeación, ejecución y pruebas de actualización del **tiempo y la paciencia** asumirán mucho tiempo y esfuerzo, especialmente si va a actualizar a Project Server 2019. Por ejemplo, si va a migrar de Project Server 2010 a Project Server 2019, primero tendrá que migrar de Project Server 2010 a Project Server 2013 y, a continuación, comprobar los datos y, a continuación, hacer lo mismo al migrar a todas las versiones sucesivas (a Project Server 2016 y, a continuación, a Project Server 2019). Es posible que desee consultar con un proveedor de soluciones de Microsoft para comparar los costos estimados con sus estimaciones de Cuánto tardarán en realizarse y con qué costos. 
    
## <a name="migrate-to-project-online"></a>Migrar a Project online

Si elige migrar de Project Server 2010 a Project online, puede hacer lo siguiente para migrar manualmente los datos del plan del proyecto:
  
1. Guarde los planes de proyecto de Project Server 2010 en. Formato MPP.
    
2. Con Project Professional 2016, Project Professional 2019 o el cliente de escritorio de Project online, abra cada archivo. MPP y, a continuación, guárdelo y publíquelo en Project online.
    
Puede crear manualmente la configuración de PWA en Project online (por ejemplo, volver a crear los campos personalizados o los calendarios de empresa necesarios). Los proveedores de soluciones de Microsoft también pueden ayudarle con esto.
  
Recursos clave:
  
|**Recurso**|**Descripción**|
|:-----|:-----|
|[Introducción a Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Cómo configurar y usar Project online.  <br/> |
|[Descripción del servicio Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |Información sobre los distintos planes de Project online que tiene a su disposición.  <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migrar a una versión local más reciente de Project Server

Aunque creemos que puede lograr el mejor valor y la experiencia del usuario mediante la migración a Project online, también sabemos que algunas organizaciones necesitan mantener los datos de Project en un entorno local. Si opta por mantener los datos de proyecto locales, puede migrar el entorno de Project Server 2010 a Project Server 2013, Project Server 2016 o Project Server 2019.
  
Le recomendamos que migre a Project Server 2019 si no puede migrar a Project online. Project Server 2019 incluye la mayoría de las características y los avances incluidos en versiones anteriores de Project Server, y se ajusta mejor a la experiencia disponible en Project online (aunque algunas características solo están disponibles en Project online).
  
Una vez completada cada migración, debe comprobar los datos para asegurarse de que se han migrado correctamente.
  
> [!NOTE]
> Si solo está pensando en migrar a Project Server 2013 si está limitado a una solución local, es importante tener en cuenta que solo hay unos cuantos años de soporte técnico restantes. La fecha de finalización del soporte técnico de Project Server 2013 con Service Pack 2 es la 10/13/2023. Para obtener más información acerca de las fechas de fin de soporte, consulte [Directiva de ciclo de vida del producto de Microsoft](https://go.microsoft.com/fwlink/p/?linkid=842066). 
  
### <a name="how-do-i-migrate-to-project-server-2019"></a>¿Cómo migro a Project Server 2019?

Las diferencias de arquitectura entre Project Server 2010 y Project Server 2019 impiden una ruta de migración directa. Esto significa que tendrá que migrar los datos de Project Server 2010 a la siguiente versión sucesiva de Project Server hasta que actualice a Project Server 2019.
  
Tendrá que realizar los pasos siguientes para actualizar Project Server 2010 a Project Server 2019:
  
1. Migrar a Project Server 2013.
    
2. Migrar desde Project atender 2013 a Project Server 2016.
    
3. Migrar de Project Server 2016 a Project Server 2019.
    
Una vez completada cada migración, debe comprobar los datos para asegurarse de que se han migrado correctamente.
  
    
### <a name="step-1-migrate-to-project-server-2013"></a>Paso 1: migrar a Project Server 2013

El primer paso para migrar los datos de Project Server 2010 a Project Server 2019 es migrar primero a Project Server 2013. 
  
Para obtener una descripción completa de lo que debe hacer para actualizar de Project Server 2010 a Project Server 2013, consulte [Upgrade to Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822). 
  
Recursos clave:
  
- [Información general sobre el proceso de actualización de Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Obtenga información de alto nivel sobre lo que necesita hacer para actualizar de Project Server 2010 a Project Server 2013.
- [Planeación de la actualización a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823) 

  Consulte las consideraciones de planeación que debe tomar al actualizar de Project Server 2010 a Project Server 2013, incluidos los requisitos del sistema.
   
[What's New in Project Server 2013 upgrade](https://go.microsoft.com/fwlink/p/?linkid=841824) le indica algunos cambios importantes para la actualización de esta versión, el que resulta más notable: 
  
- No hay ninguna actualización local a Project Server 2013. El método de base de datos adjunta es el único método admitido para actualizar de Project Server 2010 a Project Server 2013.
    
- El proceso de actualización no solo convertirá los datos de Project Server 2010 al formato de Project Server 2013, sino que también consolidará las cuatro bases de datos de Project Server 2010 en una sola base de datos de Project Web App.
    
- Tanto SharePoint Server 2013 como Project Server 2013 cambian a la autenticación basada en notificaciones de la versión anterior. Tendrá que tener en cuenta al actualizar si usa la autenticación clásica. Para obtener más información, vea [Migrar del modo clásico a autenticaciones basadas en notificaciones en SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013).
    
Recursos clave:
  
- [Introducción al proceso de actualización a Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [Actualización de las bases de datos y de las colecciones de sitios de Project Web App (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Diagrama del proceso de actualización de Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [La gran consolidación de la base de datos, la migración de Project Server 2010 a 2013 en 8 pasos sencillos](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-2-migrate-to-project-server-2016"></a>Paso 2: migrar a Project Server 2016

Después de migrar a Project Server 2013 y comprobar que los datos se han migrado correctamente, el siguiente paso consiste en migrar los datos a Project Server 2016.
  
Para obtener una descripción completa de lo que debe hacer para actualizar de Project Server 2013 a Project Server 2016, consulte [Upgrade to Project server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).
  
Recursos clave:
  
- [Introducción al proceso de actualización a Project Server 2016](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Obtenga información de alto nivel sobre lo que necesita hacer para actualizar de Project Server 2013 a Project Server 2016.

- [Planeación de la actualización a Project Server 2016](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  Consulte las consideraciones de planeación que necesita realizar al actualizar de Project Server 2013 a Project Server 2016.
   
Lo [que debe saber sobre la actualización de Project Server 2016](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) le indica algunos cambios importantes para actualizar a esta versión, que incluyen: 
  
- Al crear su entorno de Project Server 2016 en el que va a migrar los datos de Project Server 2013, tenga en cuenta que los archivos de instalación de Project Server 2016 se incluyen en SharePoint Server 2016. Para obtener más información, vea [deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829).
    
- Los planes de recursos están en desuso en Project Server 2016. Los planes de recursos de Project Server 2013 se migrarán a las negociaciones de recursos en Project Server 2016 y Project online. Para obtener más información, vea [información general: negociaciones de recursos](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) . 
    
### <a name="step-3-migrate-to-project-server-2019"></a>Paso 3: migrar a Project Server 2019

Después de migrar a Project Server 2016 y comprobar que los datos se han migrado correctamente, el siguiente paso consiste en migrar los datos a Project Server 2019.
  
Para obtener una descripción completa de lo que debe hacer para actualizar de Project Server 2016 a Project Server 2019, consulte [Upgrade to Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016).
  
Recursos clave:
  
- [Información general sobre el proceso de actualización de Project Server 2019](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Obtenga información de alto nivel sobre lo que necesita hacer para actualizar de Project Server 2013 a Project Server 2016.

- [Planeación de la actualización a Project Server 2019](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Consulte las consideraciones de planeación que necesita realizar al actualizar de Project Server 2016 a Project Server 2019.
   
Lo [que debe saber sobre la actualización de Project Server 2019](https://go.microsoft.com/fwlink/p/?linkid=841827) le indica algunos cambios importantes para actualizar a esta versión, que incluyen: 
  
- El proceso de actualización migrará los datos de la base de datos de Project Server 2016 a la base de datos de contenido de SharePoint Server 2019.  Project Server 2019 ya no creará su propia base de datos de Project Server en la granja de servidores de SharePoint.

- Después de la actualización, tenga en cuenta varios cambios en Project Web App.  Para obtener una descripción de estas características, consulte [what's New in Project Server 2019](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges).

  
Otros recursos:
  
- [Descripciones de servicios de Project online](https://go.microsoft.com/fwlink/p/?linkid=841280): vea las características de administración de cartera incluidas en project Server 2016 y Project online Premium.
    
- [Guía de migración de Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Resumen de opciones para el cliente y los servidores de Office 2010 y Windows 7

Para obtener un resumen visual de las opciones de actualización y migración a la nube para clientes de Office 2010 y servidores de Windows 7, consulte el [póster de final del soporte técnico.](../downloads/Office2010Windows7EndOfSupport.pdf)

[![Imagen de final del soporte técnico para servidores y clientes de Office 2010 y póster de Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

En este póster de una página verá rápidamente las distintas rutas para evitar que finalice el soporte técnico de los productos de cliente y servidor de Office 2010 y Windows 7. Se han resaltado las rutas de acceso preferentes y la compatibilidad con las opciones de Microsoft 365 Enterprise.

Puede [descargar](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf) este póster para imprimirlo en formatos carta, legal o tabloide (11 x 17).
   
## <a name="related-topics"></a>Temas relacionados

[Actualización desde SharePoint 2010](upgrade-from-sharepoint-2010.md)
  
[Actualizar los clientes y servidores de Office 2010](upgrade-from-office-2010-servers-and-products.md)
  
