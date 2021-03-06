---
title: Qué incluyen las plantillas de directiva DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.DLPNewPolicyFromTemplate
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
recommendations: false
description: Obtenga información sobre las plantillas de directiva de prevención de pérdida de datos (DLP) del Centro de Office 365 seguridad & cumplimiento.
ms.openlocfilehash: afcc641e6e868c1988f6b30a286c082e960d056c
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086701"
---
# <a name="what-the-dlp-policy-templates-include"></a>Qué incluyen las plantillas de directiva DLP

La prevención de pérdida de datos (DLP) en el Centro de cumplimiento de seguridad incluye plantillas de directivas listas para usar que abordan los requisitos comunes de cumplimiento, como ayudarle a proteger la información confidencial sujeta a la Ley de seguros de salud de Estados Unidos (HIPAA), la Ley &amp; Gramm-Leach-Bliley (GLBA) o la Ley Patriota de Estados Unidos. En este tema se enumeran todas las plantillas de directiva, qué tipos de información confidencial buscan y cuáles son las condiciones y acciones predeterminadas. En este tema no se incluyen todos los detalles de cómo se configura cada plantilla de directiva; en su lugar, el tema presenta suficiente información para ayudarle a decidir qué plantilla es el mejor punto de partida para su escenario. Recuerde que puede personalizar estas plantillas de directiva para satisfacer sus requisitos específicos.
  
## <a name="australia-financial-data"></a>Datos financieros de Australia

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Financiero de Australia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  Número de expediente de impuestos de Australia: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de Australia: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Financiero de Australia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de expediente de impuestos de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="australia-health-records-act-hrip-act"></a>Ley de registros de salud de Australia (Ley HRIP)

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|HRIP de Australia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de expediente de impuestos de Australia: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta médica de Australia: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|HRIP de Australia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de expediente de impuestos de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta médica de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="australia-personally-identifiable-information-pii-data"></a>Datos de identificación personal (PII) de Australia

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PII de Australia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de expediente de impuestos de Australia: recuento mínimo 1, recuento máximo 9  <br/>  Número de permiso de conducción de Australia: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Australia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de expediente de impuestos de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de permiso de conducción de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="australia-privacy-act"></a>Ley de privacidad de Australia

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Privacidad de Australia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Australia: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de Australia: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Privacidad de Australia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte de Australia: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-financial-data"></a>Datos financieros de Canadá

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Datos financieros de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Datos financieros de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-health-information-act-hia"></a>Ley de información sobre salud (HIA) de Canadá

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|HIA de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número del seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de salud de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|HIA de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número del seguro social de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de servicio de salud de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-personal-health-act-phipa---ontario"></a>Ley sobre salud personal de Canadá (PHIPA) - Ontario

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PHIPA de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número del seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de salud de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PHIPA de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número del seguro social de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de servicio de salud de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-personal-health-information-act-phia---manitoba"></a>Ley de información sobre salud personal de Canadá (PHIA) - Manitoba

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PHIA de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número del seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de salud de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PHIA de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número del seguro social de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de servicio de salud de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-personal-information-protection-act-pipa"></a>Ley de protección de información personal de Canadá (PIPA)

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PIPA de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número del seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de salud de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PIPA de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de pasaporte de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número del seguro social de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de servicio de salud de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-personal-information-protection-act-pipeda"></a>Ley de protección de información personal de Canadá (PIPEDA)

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PIPEDA de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número del seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de salud de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PIPEDA de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número del seguro social de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de servicio de salud de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="canada-personally-identifiable-information-pii-data"></a>Datos de identificación personal de Canadá (PII)

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PII de Canadá: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número del seguro social de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de salud de Canadá: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Canadá: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número del seguro social de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de servicio de salud de Canadá: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación sanitaria personal de Canadá (PHIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="france-data-protection-act"></a>Ley de protección de datos de Francia

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|DPA de Francia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Documento de identificación nacional (CNI) de Francia: recuento mínimo 1, recuento máximo 9  <br/>  Número de la seguridad social de Francia (INSEE): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|DPA de Francia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Documento de identificación nacional (CNI) de Francia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de la seguridad social de Francia (INSEE): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="france-financial-data"></a>Datos financieros de Francia

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Financiero de Francia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Financiero de Francia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="france-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) de Francia

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PII de Francia: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de la seguridad social de Francia (INSEE): recuento mínimo 1, recuento máximo 9  <br/>  Número de permiso de conducción de Francia: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de Francia: recuento mínimo 1, recuento máximo 9  <br/>  Documento de identificación nacional (CNI) de Francia: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Francia: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de la seguridad social de Francia (INSEE): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de permiso de conducción de Francia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte de Francia: recuento mínimo 10, recuento máximo cualquiera  <br/>  Documento de identificación nacional (CNI) de Francia: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="general-data-protection-regulation-gdpr"></a>Reglamento general de protección de datos (RGPD)

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Contenido confidencial de la UE de bajo volumen encontrado  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Número de licencia de conducir de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación nacional de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguridad social de la UE (SSN) o identificador equivalente: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación fiscal de la UE (TIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar informes de incidentes al administrador  <br/> |
|Alto volumen de contenido confidencial de la UE encontrado  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Número de licencia de conducir de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación nacional de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguridad social de la UE (SSN) o identificador equivalente: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación fiscal de la UE (TIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Restringir el acceso de usuarios externos al contenido  <br/>  Notificar a los usuarios con sugerencias de directiva y correo electrónico  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informes de incidentes al administrador  <br/> |
   
## <a name="germany-financial-data"></a>Datos financieros de Alemania

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Datos financieros de Alemania: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Datos financieros de Alemania: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="germany-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) de Alemania

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PII de Alemania: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Alemania: recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte de Alemania: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Alemania: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de permiso de conducción de Alemania: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte de Alemania: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="israel-financial-data"></a>Datos financieros de Israel

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Datos financieros de Israel: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de cuenta bancaria de Israel: recuento mínimo 1, recuento máximo 9  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Datos financieros de Israel: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de cuenta bancaria de Israel: recuento mínimo 10, recuento máximo cualquiera  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="israel-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) de Israel

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PII de Israel: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Identificación nacional de Israel: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Israel: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Identificación nacional de Israel: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="israel-protection-of-privacy"></a>Protección de privacidad en Israel

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Privacidad de Israel: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Identificación nacional de Israel: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de Israel: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Privacidad de Israel: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Identificación nacional de Israel: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de Israel: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="japan-financial-data"></a>Datos financieros de Japón

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Financiero de Japón: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de cuenta bancaria de Japón: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Financiero de Japón: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de cuenta bancaria de Japón: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="japan-personally-identifiable-information-pii-data"></a>Datos de identificación personal (PII) de Japón

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PII de Japón: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de registro de residente de Japón: recuento mínimo 1, recuento máximo 9  <br/>  Número del seguro social de Japón (SIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Japón: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de registro de residente de Japón: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número del seguro social de Japón (SIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="japan-protection-of-personal-information"></a>Protección de información personal de Japón

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PPI de Japón: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de registro de residente de Japón: recuento mínimo 1, recuento máximo 9  <br/>  Número del seguro social de Japón (SIN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PPI de Japón: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de registro de residente de Japón: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número del seguro social de Japón (SIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="pci-data-security-standard-pci-dss"></a>Estándar de seguridad de datos PCI (PCI DSS)

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PCI DSS: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PCI DSS: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="saudi-arabia---anti-cyber-crime-law"></a>Ley contra el crimen cibernético de Arabia Saudí

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|ACC de Arabia Saudí: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria internacional (IBAN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|ACC de Arabia Saudí: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria internacional (IBAN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="saudi-arabia-financial-data"></a>Datos financieros de Arabia Saudí

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Financiero de Arabia Saudí: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria internacional (IBAN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Financiero de Arabia Saudí: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria internacional (IBAN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="saudi-arabia-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) de Arabia Saudí

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PII de Arabia Saudí: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Identificación nacional de Arabia Saudí: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Arabia Saudí: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Identificación nacional de Arabia Saudí: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-access-to-medical-reports-act"></a>Ley de acceso a informes médicos del Reino Unidos

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|AMRA de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de servicio de salud nacional del Reino Unido: recuento mínimo 1, recuento máximo 9  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|AMRA de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de servicio de salud nacional del Reino Unido: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-data-protection-act"></a>Ley de protección de datos del Reino Unido

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|DPA de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte R.U./EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|DPA de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte R.U./EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-financial-data"></a>Datos financieros del Reino Unido

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Financiero de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 1, recuento máximo 9  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Financiero de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de tarjeta de débito de la UE: recuento mínimo 10, recuento máximo cualquiera  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-personal-information-online-code-of-practice-piocp"></a>Código de prácticas en línea de información personal (PIOCP) del Reino Unido

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PIOCP de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 1, recuento máximo 9  <br/>  Número de servicio de salud nacional del Reino Unido: recuento mínimo 1, recuento máximo 9  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PIOCP de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de servicio de salud nacional del Reino Unido: recuento mínimo 10, recuento máximo cualquiera  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) del Reino Unido

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PII de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte R.U./EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de seguro nacional del Reino Unido (NINO): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte R.U./EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="uk-privacy-and-electronic-communications-regulations"></a>Normas de comunicaciones electrónicas y privacidad del Reino Unido

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PECR de Reino Unido: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PECR de Reino Unido: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Código SWIFT: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-federal-trade-commission-ftc-consumer-rules"></a>Normas del consumidor de la Comisión Federal de Comercio de los EE.UU.

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Reglas de la FTC de Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de enrutamiento ABA: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Reglas de la FTC de Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de enrutamiento ABA: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-financial-data"></a>Datos financieros de EE.UU.

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Datos financieros - Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de enrutamiento ABA: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Datos financieros - Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de enrutamiento ABA: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-gramm-leach-bliley-act-glba"></a>Ley Gramm-Leach-Bliley (GLBA) de EE.UU.

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|GLBA de Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación de contribuyente individual EE.UU. (ITIN): recuento mínimo 1, recuento máximo 9  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|GLBA de Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación de contribuyente individual EE.UU. (ITIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-health-insurance-act-hipaa"></a>Ley de seguros de salud (HIPAA) de los EE. UU.

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|El contenido coincide con la HIPAA de EE. UU.  <br/> | Contiene cualquiera de las siguientes informaciones confidenciales:  <br/>  Número de seguridad social (SSN) de EE. UU.: recuento mínimo 1, recuento máximo cualquiera  <br/>  Número de agencia antidrogas (DEA): recuento mínimo 1, recuento máximo cualquiera  <br/> **Y** <br/>  El contenido contiene cualquiera de estos términos:  <br/>  Clasificación internacional de las enfermedades (ICD-9-CM): recuento mínimo 1, recuento máximo cualquiera  <br/>  Clasificación internacional de las enfermedades (ICD-10-CM): recuento mínimo 1, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
   
## <a name="us-patriot-act"></a>Ley Patriota de los EE.UU.

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Ley Patriota de los EE.UU.: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de identificación de contribuyente individual EE.UU. (ITIN): recuento mínimo 1, recuento máximo 9  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Ley Patriota de los EE.UU.: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de identificación de contribuyente individual EE.UU. (ITIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-personally-identifiable-information-pii-data"></a>Información de identificación personal (PII) de Estados Unidos

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|PII de Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de identificación de contribuyente individual EE.UU. (ITIN): recuento mínimo 1, recuento máximo 9  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 1, recuento máximo 9  <br/>  Número de pasaporte R.U./EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|PII de Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de identificación de contribuyente individual EE.UU. (ITIN): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de pasaporte R.U./EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-state-breach-notification-laws"></a>Leyes de notificación de incumplimiento estatal de EE.UU.

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Incumplimientos estatales de Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 1, recuento máximo 9  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de permiso de conducción de EE. UU.: recuento mínimo 1, recuento máximo 9  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Incumplimientos estatales de Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de tarjeta de crédito: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de cuenta bancaria de EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de permiso de conducción de EE. UU.: recuento mínimo 10, recuento máximo cualquiera  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   
## <a name="us-state-social-security-number-confidentiality-laws"></a>Leyes de confidencialidad sobre el número de Seguridad Social de EE.UU.

|**Nombre de la regla**|**Condiciones  <br/> (incluidos los tipos de información confidencial)**|**Actions**|
|:-----|:-----|:-----|
|Leyes sobre el SSN de Estados Unidos: Examinar el contenido compartido fuera - conteo bajo  <br/> | El contenido contiene información confidencial:  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 1, recuento máximo 9  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> |Enviar una notificación  <br/> |
|Leyes sobre el SSN de Estados Unidos: Examinar el contenido compartido fuera - conteo alto  <br/> | El contenido contiene información confidencial:  <br/>  Número de la seguridad social EE.UU. (SSN): recuento mínimo 10, recuento máximo cualquiera  <br/>  El contenido se comparte con:  <br/>  Personas ajenas a mi organización  <br/> | Bloquear acceso al contenido  <br/>  Enviar una notificación  <br/>  Permitir invalidación  <br/>  Requerir justificación del negocio  <br/>  Enviar informe de incidentes  <br/> |
   

