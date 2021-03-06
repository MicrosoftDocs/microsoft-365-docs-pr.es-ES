---
title: Redirigir usuarios desde el Office 365 seguridad y cumplimiento al Centro de cumplimiento de Microsoft 365
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Obtenga información sobre cómo redirigir automáticamente Office 365 usuarios del Centro de seguridad y cumplimiento al Centro de cumplimiento de Microsoft 365..
ms.collection: M365-security-compliance
ms.openlocfilehash: 62fc302f9f065ac7bb0475a6e72dc240a56a1fe1
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339411"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a>Redirigir usuarios desde el Office 365 seguridad y cumplimiento al Centro de cumplimiento de Microsoft 365

En este artículo se explica cómo funciona la redirección automática para los usuarios que tienen acceso a soluciones de cumplimiento desde el Centro de seguridad y cumplimiento de Office 365 (protection.office.com) hasta el Centro de cumplimiento de Microsoft 365 (compliance.microsoft.com).

## <a name="what-to-expect"></a>Qué esperar

El redireccionamiento automático está habilitado de forma predeterminada para todos los usuarios que tengan acceso a las siguientes soluciones relacionadas con el cumplimiento en Office 365 seguridad y cumplimiento (protection.office.com):

- Prevención de pérdida de datos (DLP)
- Clasificación
- Información de gobierno
- Administración de registros
- Cumplimiento de comunicaciones (anteriormente "Supervisión")

Los usuarios se enruta automáticamente a las mismas soluciones de cumplimiento en el Centro de cumplimiento de Microsoft 365 (compliance.microsoft.com).

> [!NOTE]
> Para otras soluciones de cumplimiento incluidas en el Centro de seguridad y cumplimiento de Office 365, los usuarios seguirán administrando estas soluciones en el Centro de cumplimiento de Microsoft 365 o en el Centro de seguridad y cumplimiento de Office 365. La redirección automática de estas soluciones de cumplimiento estará disponible próximamente.

Esta característica y los controles asociados no habilitan la redirección automática de características de seguridad para Microsoft Defender para Office 365. Para habilitar el redireccionamiento de características de seguridad, vea [Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) para obtener más información.

## <a name="can-i-go-back-to-using-the-former-portal"></a>¿Puedo volver a usar el portal anterior?

Si algo no funciona para usted o si hay algo que no puede completar a través del portal de Centro de cumplimiento de Microsoft 365, puede deshabilitar temporalmente el redireccionamiento automático para todos los usuarios.

> [!IMPORTANT]
> El Centro de cumplimiento de Microsoft 365 es el portal de administración de reemplazo para soluciones de cumplimiento actualmente administradas en el centro de seguridad y cumplimiento Office 365 de cumplimiento. Todas Microsoft 365 de cumplimiento normativo se administrarán únicamente en el Centro de cumplimiento de Microsoft 365. Deshabilitar la redirección a la Centro de cumplimiento de Microsoft 365 debe ser una solución a corto plazo.

Para volver al Centro Office 365 seguridad y cumplimiento (protection.microsoft.com) para todos los usuarios, siga estos pasos:

1. Inicie sesión en el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) como administrador global o mediante cualquier cuenta con permisos de administrador de cumplimiento en Azure Active Directory.
2. Vaya **a** Configuración  >  **redirección del centro de cumplimiento**.
3. Alterna la opción Redirección automática a **Desactivado**.
4. Seleccione **Desactivar y** compartir comentarios cuando se le pida.

Una vez deshabilitado, los usuarios ya no se enrutarán a compliance.microsoft.com y se dirigirán al Centro de seguridad y cumplimiento de Office 365 (protection.microsoft.com). Los administradores globales o de cumplimiento pueden habilitar esta configuración de nuevo en cualquier momento.

## <a name="related-information"></a>Información relacionada

- [Centro de cumplimiento de Microsoft 365 información general](/microsoft-365/compliance/microsoft-365-compliance-center)
