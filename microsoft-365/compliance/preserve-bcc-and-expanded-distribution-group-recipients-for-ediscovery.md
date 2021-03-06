---
title: Conservar los destinatarios de grupos de distribución expandidos y CCO para la exhibición de documentos electrónicos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2017
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: eb8ddf15-0080-457e-9d83-e73e193da334
description: In-Place de retención, retención por juicio y directivas de retención Microsoft 365 permiten conservar el contenido del buzón para cumplir los requisitos de cumplimiento normativo y exhibición de documentos electrónicos.
ms.openlocfilehash: f00ed951fb68778b9c62ae874c2cca964bd6cb5c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927946"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>Conservar los destinatarios de grupos de distribución expandidos y CCO para la exhibición de documentos electrónicos
  
In-Place de retención, retención por [](./retention.md) juicio y directivas de retención de Microsoft 365 (creadas en el Centro de cumplimiento de seguridad &) permiten conservar el contenido del buzón para cumplir los requisitos de cumplimiento normativo y exhibición de documentos electrónicos. La información sobre los destinatarios directamente dirigidos en los campos Para y Cc de un mensaje se incluye en todos los mensajes de forma predeterminada. Pero su organización puede requerir la capacidad de buscar y reproducir detalles sobre todos los destinatarios de un mensaje. Esto incluye:
  
- **Destinatarios dirigidos mediante el campo CCO de un mensaje:** Los destinatarios CCO se almacenan en el mensaje en el buzón del remitente, pero no se incluyen en los encabezados del mensaje entregado a los destinatarios. 
    
- **Destinatarios de grupos de distribución expandido:** Destinatarios que reciben el mensaje porque son miembros de un grupo de distribución al que se ha dirigido el mensaje, ya sea en los campos Para, Cc o CCO. 
    
Exchange Online y Exchange Server 2013 (actualización acumulativa 7 y versiones posteriores) conservan información sobre CCO y destinatarios de grupos de distribución expandido. Puede buscar esta información mediante una búsqueda de exhibición de documentos electrónicos de In-Place en el Centro de administración de Exchange (EAC) o una búsqueda de contenido en el Centro de seguridad & cumplimiento. 
  
## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>Forma de conservación de los destinatarios CCO y los destinatarios del grupo de distribución expandido

Tal como se mencionó anteriormente, la información los destinatarios CCO se almacena con el mensaje en el buzón de correo del remitente. Esta información está indizada y disponible para las búsquedas y retenciones de exhibición de documentos electrónicos. 
  
La información sobre los destinatarios del grupo de distribución expandido se almacena con el mensaje después de que se coloca en un buzón de correo en conservación local o retención por juicio. En Office 365, esta información también se almacena cuando se aplica una directiva Microsoft 365 de retención a un buzón. La pertenencia al grupo de distribución se determina en el momento en el que se envía el mensaje. La lista de destinatarios ampliada almacenada con el mensaje no se ve afectada por los cambios realizados en la pertenencia del grupo después de que se envía el mensaje. 
  
| La información sobre... | se almacena en... | ¿se almacena de forma predeterminada? | es accesible para... |
|:-----|:-----|:-----|:-----|
|Destinatarios de Para y CC  <br/> |Propiedades del mensaje en los buzones de correo del remitente y los destinatarios  <br/> |Sí  <br/> |Remitente, destinatarios y responsables de cumplimiento normativo  <br/> |
|Destinatarios CCO  <br/> |Propiedad del mensaje en el buzón de correo del remitente  <br/> |Sí  <br/> |Remitente y responsables de cumplimento normativo  <br/> |
|Destinatarios del grupo de distribución expandido  <br/> |Propiedades del mensaje en el buzón de correo del remitente  <br/> |No. La información de destinatarios del grupo de distribución expandido se almacena después de que un buzón se coloca en In-Place retención o retención por juicio, o se asigna a una directiva Microsoft 365 retención.  <br/> |Responsables de cumplimento normativo  <br/> |
   
## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>Buscar mensajes enviados a destinatarios CCO y del grupo de distribución expandido

Cuando se buscan mensajes enviados a un destinatario, los resultados de la búsqueda de exhibición de documentos electrónicos ahora incluyen los mensajes enviados a un grupo de distribución del que es miembro el destinatario. En la tabla siguiente se muestran los escenarios en los que los mensajes enviados a destinatarios CCO y del grupo de distribución ampliado se proporcionan en las búsquedas de exhibición de documentos electrónicos.
  
Escenario 1: John es miembro del grupo de distribución US-Sales En esta tabla se muestran los resultados de búsqueda de la exhibición de documentos electrónicos cuando Bob le envía un mensaje a John directamente o indirectamente mediante un grupo de distribución.
  
| Cuando busca mensajes enviados en el buzón de Bob... | Y el mensaje se envía con... | ¿Los resultados incluyen el mensaje? |
|:-----|:-----|:-----|
|To:John  <br/> |John en TO  <br/> |Sí  <br/> |
|To:John  <br/> |US-Sales en TO  <br/> |Sí  <br/> |
|To:US-Sales  <br/> |US-Sales en TO  <br/> |Sí  <br/> |
|Cc:John  <br/> |John en CC  <br/> |Sí  <br/> |
|Cc:John  <br/> |US-Sales en CC  <br/> |Sí  <br/> |
|Cc:US-Sales  <br/> |US-Sales en CC  <br/> |Sí  <br/> |
   
Escenario 2: Bob le envía un correo electrónico a John (Para/CC) y Jack (CCO directamente o indirectamente mediante un grupo de distribución). En la tabla siguiente se muestran los resultados de búsqueda de la exhibición de documentos electrónicos.
  
| Cuando busca... | Para los mensajes enviados... | ¿Los resultados incluyen el mensaje? | Notas |
|:-----|:-----|:-----|:-----|
|Buzón de correo de Bob  <br/> |To/Cc:John  <br/> |Sí  <br/> |Presenta una indicación de que Jack se incluyó en CCO.  <br/> |
|Buzón de correo de Bob  <br/> |Bcc:Jack  <br/> |Sí  <br/> |Presenta una indicación de que Jack se incluyó en CCO.  <br/> |
|Buzón de correo de Bob  <br/> |Bcc:Jack (mediante grupo de distribución)  <br/> |Sí  <br/> |La lista de miembros del grupo de distribución CCO, expandida cuando se envió el mensaje, está visible en la vista previa, exportación y registros de la búsqueda de exhibición de documentos electrónicos.  <br/> |
|Buzón de correo de John  <br/> |To/Cc:John  <br/> |Sí  <br/> |Sin indicación de los destinatarios CCO.  <br/> |
|Buzón de correo de John  <br/> |Bcc:Jack (directamente o mediante grupo de distribución)  <br/> |No  <br/> |La información de CCO no se almacena en el mensaje que se entrega a los destinatarios. Debe buscar en el buzón de correo del remitente.  <br/> |
|Buzón de correo de Jack  <br/> |To/Cc:John (directamente o mediante grupo de distribución)  <br/> |Sí  <br/> |La información de Para/CC se incluye en el mensaje que se entrega a todos los destinatarios.  <br/> |
|Buzón de correo de Jack  <br/> |Bcc:Jack (directamente o mediante grupo de distribución)  <br/> |No  <br/> |La información de CCO no se almacena en el mensaje que se entrega a los destinatarios. Debe buscar en el buzón de correo del remitente.  <br/> |
   
## <a name="frequently-asked-questions"></a>Preguntas frecuentes

 **P. ¿Cuándo y dónde se almacena la información de destinatarios CCO?**
  
R. La información de CCO se conserva de forma predeterminada en el mensaje original en el buzón de correo del remitente. Si el destinatario CCO es un grupo de distribución, la pertenencia al grupo de distribución solo se expande si el buzón del remitente está en espera o se asigna a una directiva de retención Microsoft 365 distribución.
  
 **P. ¿Cuándo y dónde está almacenada la lista de destinatarios del grupo de distribución expandido?**
  
R. La pertenencia al grupo se expande en el momento en el que se envía el mensaje. La lista de miembros del grupo de distribución expandido se almacena en el mensaje original en el buzón de correo del remitente. El buzón del remitente debe estar en In-Place, retención por juicio o asignado a una directiva Microsoft 365 retención.
  
 **P. ¿Los destinatarios incluidos en Para/CC: pueden ver qué destinatarios figuran en CCO?**
  
R. No. Esta información no se incluye en los encabezados del mensaje y no está visible para los destinatarios incluidos en Para/CC. El remitente puede ver el campo CCO almacenado en el mensaje original almacenado en el buzón de correo. Los responsables de cumplimento normativo pueden ver esta información cuando buscan en el buzón de correo del remitente.
  
 **P. ¿Cómo puedo asegurarme de que los destinatarios de grupos de distribución expandido siempre se conservan?**
  
R: Para asegurarse de que los miembros del grupo de distribución expandido siempre se conservan con un [mensaje,](/Exchange/policy-and-compliance/holds/place-all-mailboxes-on-hold) coloque todos los buzones en espera o cree una directiva de retención Microsoft 365 organización. 
  
 **P. ¿Qué tipos de grupos se admiten?**
  
R. Se admiten grupos de distribución, grupos de seguridad habilitados para correo y grupos de distribución dinámicos. 
  
 **P. ¿Existe un límite en la cantidad de destinatarios del grupo de distribución que se amplía y se almacena en el mensaje?**
  
R. Se conservan hasta 10.000 miembros de un grupo de distribución.
  
 **P. ¿Se admiten los grupos de distribución anidados?**
  
R. Sí, se expanden 25 niveles de grupos de distribución anidados.
  
 **P. ¿Dónde se puede ver la información de los destinatarios del grupo de distribución expandido y CCO?**
  
R. La información de los destinatarios CCO y del grupo de distribución expandido aparece visible para los responsables del cumplimiento normativo cuando se realiza una búsqueda de exhibición de documentos electrónicos. Los destinatarios CCO y del grupo de distribución expandido se incluyen en los resultados de la búsqueda que se hayan copiado en un buzón de correo de detección o se hayan exportado a un archivo PST y en el registro de exhibición de documentos electrónicos incluidos en los resultados de la búsqueda. La información de los destinatarios CCO también se encuentra disponible en la vista previa de la búsqueda.
  
 **P. ¿Qué ocurre si se oculta un miembro de un grupo de distribución de lista global de direcciones de la organización (GAL)?**
  
R. No pasa nada. Si los destinatarios están ocultos de la GAL, aún se incluyen en la lista de destinatarios del grupo de distribución expandido.