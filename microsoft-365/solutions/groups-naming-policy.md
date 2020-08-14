---
title: Directiva de nomenclatura de grupos de 365 de Microsoft
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Obtenga información sobre cómo crear una directiva de nomenclatura para grupos de Microsoft 365.
ms.openlocfilehash: 0072abf4f249af544e8234fdedec584a71c214a7
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662840"
---
# <a name="microsoft-365-groups-naming-policy"></a>Directiva de nomenclatura de grupos de 365 de Microsoft

Puede usar una directiva de nomenclatura de grupos para aplicar una estrategia de nomenclatura coherente para los grupos creados por los usuarios de la organización. Una directiva de nomenclatura puede ayudarle a usted y a sus usuarios a identificar la función del grupo, la pertenencia, la región geográfica o el usuario que creó el grupo. La Directiva de nomenclatura también puede ayudar a clasificar los grupos de la libreta de direcciones. Puede usar la Directiva para bloquear palabras específicas para que no se usen en nombres de grupo y alias.

La Directiva de nomenclatura se aplica a los grupos que se crean en todas las cargas de trabajo de grupos (como Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.). Se aplica al nombre del grupo y al alias del grupo. Se aplica cuando un usuario crea un grupo y cuando se modifica el nombre o el alias del grupo para un grupo existente.

> [!TIP]
> Una directiva de nomenclatura de grupo de Microsoft 365 solo se aplica a los grupos de Microsoft 365. No se aplica a los grupos de distribución creados en Exchange Online. Para crear una directiva de nomenclatura para los grupos de distribución, consulte [Create a Distribution Group naming Policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).

La Directiva de nomenclatura de grupos consta de las siguientes características:

- **Directiva de nomenclatura de prefijo-sufijo**: puede usar prefijos o sufijos para definir la Convención de nomenclatura de grupos (por ejemplo: "US \_ My Group \_ Engineering"). Los prefijos/sufijos pueden ser cadenas fijas o atributos de usuario, como [Departamento], que se sustituirán según el usuario que cree el grupo.

- **Palabras bloqueadas personalizadas**: puede cargar un conjunto de palabras bloqueadas específicas de su organización que podrían bloquearse en grupos creados por los usuarios. (Por ejemplo: "CEO, nóminas, h").

## <a name="licensing-requirements"></a>Requisitos de licencia

El uso de la Directiva de nomenclatura de Azure AD para los grupos de Microsoft 365 requiere tener que poseer, pero no necesariamente, una licencia de Azure Active Directory Premium P1 o la licencia de Azure AD Basic EDU para cada usuario único (incluidos los invitados) que pertenezca a uno o varios grupos de Microsoft 365.

Esto también es necesario para el administrador que crea la Directiva de nomenclatura de grupos.

## <a name="prefix-suffix-naming-policy"></a>Directiva de nomenclatura prefix-Suffix

Los prefijos y los sufijos pueden ser cadenas fijas o atributos de usuario.

### <a name="fixed-strings"></a>Cadenas fijas

Puede usar cadenas cortas que pueden ayudarle a diferenciar los grupos de la GAL y la navegación izquierda de las cargas de trabajo de grupo. Algunos de los sufijos comunes son palabras clave como "nombre del GRP \_ ", " \# nombre", " \_ nombre".

### <a name="attributes"></a>Atributos

Puede usar atributos que ayuden a identificar quién ha creado el grupo como [Departamento] y dónde se ha creado desde like [país].

Ejemplos:

- Policy = "GRP [Nombredegrupo] [Departamento]"
- Departamento del usuario = ingeniería
- Nombre de grupo creado = "grupo de ingeniería de mi grupo"

Los atributos compatibles de Azure Active Directory (Azure AD) son [Departamento], [compañía], [Office], [StateOrProvince], [CountryOrRegion] y [cargo].

- Los atributos de usuario no admitidos se consideran cadenas fijas, por ejemplo [CódigoPostal].

- Los atributos de extensión y los atributos personalizados no son compatibles.

Se recomienda usar atributos que tengan valores rellenados para todos los usuarios de la organización y que no usen atributos que tengan valores más largos.

### <a name="things-to-look-out-for"></a>Aspectos que se deben tener en cuentan

- Durante la creación de la Directiva, la longitud total de las cadenas de prefijos y sufijos se limita a 53 caracteres.

- Los prefijos y los sufijos pueden contener caracteres especiales que se admiten en nombre de grupo y alias de grupo. Cuando los prefijos y los sufijos contienen caracteres especiales que no se permiten en el alias de grupo, solo se aplican al nombre del grupo. Por lo tanto, en este caso, los prefijos y los sufijos aplicados al nombre del grupo serían distintos de los que se aplican al alias del grupo.

  > [!NOTE]
  > Se permite un punto (.) o un guión (-) en cualquier lugar del nombre del grupo, excepto al principio o al final del nombre. Un carácter de subrayado (_) se permite en cualquier lugar del nombre del grupo, incluido al principio o al final del nombre.

- Si usa los grupos conectados de Yammer Office 365, evite usar los siguientes caracteres en su Directiva de nomenclatura: @, \# , \[ , \] , \<, and \> . Si estos caracteres están en la Directiva de nomenclatura, los usuarios normales de Yammer no podrán crear grupos.

> [!Tip]
> - Use cadenas cortas como sufijo.
> - Use atributos con valores.
> - No ser demasiado creativo, la longitud total del nombre tiene un máximo de 264 caracteres.
> - Cargar las palabras bloqueadas específicas de la organización para restringir el uso.

## <a name="custom-blocked-words"></a>Palabras bloqueadas personalizadas

Puede escribir una lista separada por comas de palabras bloqueadas que se bloquearán en nombres de grupo y alias.

No se realizan búsquedas de subcadenas; concretamente, se necesita una coincidencia exacta entre el nombre del usuario especificado y las palabras bloqueadas personalizadas para desencadenar un error.

**Aspectos que se deben tener en**cuentan:

- Las palabras bloqueadas no distinguen mayúsculas de minúsculas.

- Cuando un usuario escribe una palabra bloqueada, el cliente del grupo mostrará un mensaje de error con la palabra bloqueada.

- No hay restricciones de caracteres en las palabras bloqueadas que se usan.

- Hay un límite de 5000 palabras que se pueden establecer como palabras bloqueadas.

## <a name="admin-override"></a>Invalidación de administrador

Algunos administradores están exentos de estas directivas, en todas las cargas de trabajo y extremos de grupo, para que puedan crear grupos con estas palabras bloqueadas y con sus convenciones de nomenclatura deseadas. A continuación se muestra la lista de roles de administrador exentos de la Directiva de nomenclatura de grupos.

- Administrador global

- Soporte técnico de nivel 1 de asociado

- Soporte técnico de nivel 2 del asociado

- Administrador de cuentas de usuario

- Escritores de directorios

## <a name="how-to-set-up-the-naming-policy"></a>Cómo configurar la Directiva de nomenclatura

Para configurar una directiva de nomenclatura:

1. En [Azure Active Directory](https://aad.portal.azure.com), en **administrar**, haga clic en **grupos**.
2. En **configuración**, haga clic en **Directiva de nomenclatura**.
3. Seleccione la pestaña **Directiva de nomenclatura de grupos** .
4. En **Directiva actual**, elija si desea requerir un prefijo o un sufijo o ambos y active las casillas de verificación adecuadas.
5. Elija entre **atributo** y **cadena** para cada línea y, a continuación, especifique el atributo o la cadena.
6. Cuando haya agregado los prefijos y los sufijos que necesita, haga clic en **Guardar**.

![Captura de pantalla de la configuración de la Directiva de nomenclatura de grupos en Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>Temas relacionados

[Cmdlets de Azure Active Directory para configurar configuraciones de grupo](https://go.microsoft.com/fwlink/?linkid=868341)