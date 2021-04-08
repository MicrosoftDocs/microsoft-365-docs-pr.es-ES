---
title: Establecer preferencias para ATP de Microsoft Defender para Mac
description: Configurar ATP de Microsoft Defender para Mac en organizaciones empresariales.
keywords: microsoft, defender, atp, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 578830d44a9a69c3ccafd78ceaf59ddfe100e43f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076931"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-mac"></a>Establecer preferencias para Microsoft Defender para Endpoint para Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para endpoint para Mac](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
>Este artículo contiene instrucciones sobre cómo establecer preferencias para Microsoft Defender para Endpoint para Mac en organizaciones empresariales. Para configurar Microsoft Defender para Endpoint para Mac mediante la interfaz de línea de comandos, vea [Resources](mac-resources.md#configuring-from-the-command-line).

## <a name="summary"></a>Resumen

En organizaciones empresariales, Microsoft Defender para Endpoint para Mac se puede administrar a través de un perfil de configuración que se implementa mediante una de varias herramientas de administración. Las preferencias administradas por el equipo de operaciones de seguridad tienen prioridad sobre las preferencias que se establecen localmente en el dispositivo. Cambiar las preferencias que se establecen a través del perfil de configuración requiere privilegios escalados y no está disponible para usuarios sin permisos administrativos.

En este artículo se describe la estructura del perfil de configuración, se incluye un perfil recomendado que puede usar para empezar y se proporcionan instrucciones sobre cómo implementar el perfil.

## <a name="configuration-profile-structure"></a>Estructura de perfiles de configuración

El perfil de configuración es un *archivo .plist* que consta de entradas identificadas por una clave (que indica el nombre de la preferencia), seguido de un valor, que depende de la naturaleza de la preferencia. Los valores pueden ser simples (como un valor numérico) o complejos, como una lista anidada de preferencias.

>[!CAUTION]
>El diseño del perfil de configuración depende de la consola de administración que se use. Las secciones siguientes contienen ejemplos de perfiles de configuración para JAMF e Intune.

El nivel superior del perfil de configuración incluye las preferencias de todo el producto y las entradas para las subáreas de Microsoft Defender para endpoint, que se explican con más detalle en las secciones siguientes.

### <a name="antivirus-engine-preferences"></a>Preferencias del motor antivirus

La *sección antivirusEngine* del perfil de configuración se usa para administrar las preferencias del componente antivirus de Microsoft Defender para endpoint.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | antivirusEngine |
| **Tipo de datos** | Diccionario (preferencia anidada) |
| **Comments** | Vea las secciones siguientes para obtener una descripción del contenido del diccionario. |

#### <a name="enable--disable-real-time-protection"></a>Habilitar o deshabilitar la protección en tiempo real

Especifique si se va a habilitar la protección en tiempo real, que examina los archivos a medida que se accede a ellos.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | enableRealTimeProtection |
| **Tipo de datos** | Booleano |
| **Posibles valores** | true (valor predeterminado) <br/> false |

#### <a name="enable--disable-passive-mode"></a>Habilitar o deshabilitar el modo pasivo

Especifique si el motor antivirus se ejecuta en modo pasivo. El modo pasivo tiene las siguientes implicaciones: 
- La protección en tiempo real está desactivada
- El examen a petición está activado
- La corrección automática de amenazas está desactivada
- Las actualizaciones de inteligencia de seguridad están activadas
- El icono del menú Estado está oculto

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | passiveMode |
| **Tipo de datos** | Booleano |
| **Posibles valores** | false (predeterminado) <br/> true |
| **Comments** | Disponible en Microsoft Defender para endpoint versión 100.67.60 o posterior. |

#### <a name="exclusion-merge-policy"></a>Directiva de combinación de exclusión

Especifique la directiva de combinación para exclusiones. Puede ser una combinación de exclusiones definidas por el administrador y definidas por el usuario ( ) o solo `merge` exclusiones definidas por el administrador ( `admin_only` ). Esta configuración se puede usar para restringir que los usuarios locales definan sus propias exclusiones.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | exclusionsMergePolicy |
| **Tipo de datos** | Cadena |
| **Posibles valores** | merge (valor predeterminado) <br/> admin_only |
| **Comments** | Disponible en Microsoft Defender para endpoint versión 100.83.73 o posterior. |

#### <a name="scan-exclusions"></a>Exclusiones de examen

Especifique las entidades que no se han analizado. Las exclusiones se pueden especificar por rutas de acceso completas, extensiones o nombres de archivo.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | exclusiones |
| **Tipo de datos** | Diccionario (preferencia anidada) |
| **Comments** | Vea las secciones siguientes para obtener una descripción del contenido del diccionario. |

##### <a name="type-of-exclusion"></a>Tipo de exclusión

Especifique el contenido excluido de ser examinado por tipo.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | $type |
| **Tipo de datos** | Cadena |
| **Posibles valores** | excludedPath <br/> excludedFileExtension <br/> excludedFileName |

##### <a name="path-to-excluded-content"></a>Ruta de acceso al contenido excluido

Especifique el contenido excluido de ser examinado por la ruta de acceso de archivo completa.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | path |
| **Tipo de datos** | Cadena |
| **Posibles valores** | rutas de acceso válidas |
| **Comments** | Aplicable solo *si $type* *se excluyePath* |

##### <a name="path-type-file--directory"></a>Tipo de ruta de acceso (archivo/directorio)

Indica si la *propiedad path* hace referencia a un archivo o directorio. 

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | isDirectory |
| **Tipo de datos** | Booleano |
| **Posibles valores** | false (predeterminado) <br/> true |
| **Comments** | Aplicable solo *si $type* *se excluyePath* |

##### <a name="file-extension-excluded-from-the-scan"></a>Extensión de archivo excluida del examen

Especifique el contenido excluido de la extensión de archivo.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | extensión |
| **Tipo de datos** | Cadena |
| **Posibles valores** | extensiones de archivo válidas |
| **Comments** | Aplicable solo *si $type* *se excluyeFileExtension* |

##### <a name="process-excluded-from-the-scan"></a>Proceso excluido del examen

Especifique un proceso para el que se excluya toda la actividad de archivo del examen. El proceso puede especificarse por su nombre (por ejemplo) o por la ruta de acceso `cat` completa (por ejemplo, `/bin/cat` ).

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | name |
| **Tipo de datos** | Cadena |
| **Posibles valores** | cualquier cadena |
| **Comments** | Aplicable solo *si $type* *se excluyeFileName* |

#### <a name="allowed-threats"></a>Amenazas permitidas

Especifica las amenazas por nombre que Defender for Endpoint for Mac no bloquee. Estas amenazas podrán ejecutarse.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | allowedThreats |
| **Tipo de datos** | Matriz de cadenas |

#### <a name="disallowed-threat-actions"></a>Acciones de amenazas no permitidos

Restringe las acciones que el usuario local de un dispositivo puede realizar cuando se detectan amenazas. Las acciones incluidas en esta lista no se muestran en la interfaz de usuario.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | disallowedThreatActions |
| **Tipo de datos** | Matriz de cadenas |
| **Posibles valores** | permitir (restringe a los usuarios permitir amenazas) <br/> restore (restringe a los usuarios la restauración de amenazas desde la cuarentena) |
| **Comments** | Disponible en Microsoft Defender para endpoint versión 100.83.73 o posterior. |

#### <a name="threat-type-settings"></a>Configuración del tipo de amenaza

Especifica cómo controla Microsoft Defender para Endpoint para Mac determinados tipos de amenazas.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | threatTypeSettings |
| **Tipo de datos** | Diccionario (preferencia anidada) |
| **Comments** | Vea las secciones siguientes para obtener una descripción del contenido del diccionario. |

##### <a name="threat-type"></a>Tipo de amenaza

Especifique tipos de amenazas.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | clave |
| **Tipo de datos** | Cadena |
| **Posibles valores** | potentially_unwanted_application <br/> archive_bomb |

##### <a name="action-to-take"></a>Acción que puede realizar

Especifique qué acción realizar cuando se detecte una amenaza del tipo especificado en la sección anterior. Seleccione una de las opciones siguientes:

- **Auditoría:** el dispositivo no está protegido contra este tipo de amenaza, pero se registra una entrada sobre la amenaza.
- **Bloquear:** el dispositivo está protegido contra este tipo de amenaza y se te notificará en la interfaz de usuario y en la consola de seguridad.
- **Desactivado:** el dispositivo no está protegido contra este tipo de amenaza y no se registra nada.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | valor |
| **Tipo de datos** | Cadena |
| **Posibles valores** | auditoría (valor predeterminado) <br/> bloque <br/> off |

#### <a name="threat-type-settings-merge-policy"></a>Directiva de combinación de configuración de tipo de amenaza

Especifique la directiva de combinación para la configuración del tipo de amenaza. Puede ser una combinación de opciones definidas por el administrador y definidas por el usuario ( ) o solo opciones definidas `merge` por el administrador ( `admin_only` ). Esta configuración se puede usar para restringir que los usuarios locales definan su propia configuración para diferentes tipos de amenazas.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | threatTypeSettingsMergePolicy |
| **Tipo de datos** | Cadena |
| **Posibles valores** | merge (valor predeterminado) <br/> admin_only |
| **Comments** | Disponible en Microsoft Defender para endpoint versión 100.83.73 o posterior. |

#### <a name="antivirus-scan-history-retention-in-days"></a>Retención del historial de examen antivirus (en días)

Especifica el número de días que los resultados se conservan en el historial de examen del dispositivo. Los resultados del examen antiguos se quitan del historial. Archivos antiguos en cuarentena que también se quitan del disco.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | scanResultsRetentionDays |
| **Tipo de datos** | Cadena |
| **Posibles valores** | 90 (valor predeterminado). Los valores permitidos van de 1 día a 180 días. |
| **Comments** | Disponible en Microsoft Defender para endpoint versión 101.07.23 o posterior. |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Número máximo de elementos en el historial de examen antivirus

Especifique el número máximo de entradas que se deben conservar en el historial de examen. Las entradas incluyen todos los exámenes a petición realizados en el pasado y todas las detecciones de antivirus.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | scanHistoryMaximumItems |
| **Tipo de datos** | Cadena |
| **Posibles valores** | 10000 (valor predeterminado). Los valores permitidos van de 5000 elementos a 15000 elementos. |
| **Comments** | Disponible en Microsoft Defender para endpoint versión 101.07.23 o posterior. |

### <a name="cloud-delivered-protection-preferences"></a>Preferencias de protección entregadas en la nube

Configure las características de protección controlada por la nube de Microsoft Defender para Endpoint para Mac.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | cloudService |
| **Tipo de datos** | Diccionario (preferencia anidada) |
| **Comments** | Vea las secciones siguientes para obtener una descripción del contenido del diccionario. |

#### <a name="enable--disable-cloud-delivered-protection"></a>Habilitar o deshabilitar la protección entregada en la nube

Especifica si se va a habilitar la protección entregada en la nube del dispositivo o no. Para mejorar la seguridad de los servicios, se recomienda mantener activada esta característica.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | habilitado |
| **Tipo de datos** | Booleano |
| **Posibles valores** | true (valor predeterminado) <br/> false |

#### <a name="diagnostic-collection-level"></a>Nivel de colección de diagnóstico

Los datos de diagnóstico se usan para mantener Microsoft Defender for Endpoint seguro y actualizado, detectar, diagnosticar y corregir problemas y también realizar mejoras en el producto. Esta configuración determina el nivel de diagnóstico enviado por Microsoft Defender para Endpoint a Microsoft.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | diagnosticLevel |
| **Tipo de datos** | Cadena |
| **Posibles valores** | opcional (predeterminado) <br/> necesario |

#### <a name="enable--disable-automatic-sample-submissions"></a>Habilitar o deshabilitar envíos de ejemplo automáticos

Determina si se envían muestras sospechosas (que probablemente contengan amenazas) a Microsoft. Se le preguntará si es probable que el archivo enviado contenga información personal.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | automaticSampleSubmission |
| **Tipo de datos** | Booleano |
| **Posibles valores** | true (valor predeterminado) <br/> false |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Habilitar o deshabilitar actualizaciones automáticas de inteligencia de seguridad

Determina si las actualizaciones de inteligencia de seguridad se instalan automáticamente:

|||
|:---|:---|
| **Clave** | automaticDefinitionUpdateEnabled |
| **Tipo de datos** | Booleano |
| **Posibles valores** | true (valor predeterminado) <br/> false |

### <a name="user-interface-preferences"></a>Preferencias de la interfaz de usuario

Administrar las preferencias de la interfaz de usuario de Microsoft Defender para Endpoint para Mac.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | userInterface |
| **Tipo de datos** | Diccionario (preferencia anidada) |
| **Comments** | Vea las secciones siguientes para obtener una descripción del contenido del diccionario. |

#### <a name="show--hide-status-menu-icon"></a>Mostrar u ocultar icono de menú de estado

Especifique si desea mostrar u ocultar el icono del menú de estado en la esquina superior derecha de la pantalla.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | hideStatusMenuIcon |
| **Tipo de datos** | Booleano |
| **Posibles valores** | false (predeterminado) <br/> true |

#### <a name="show--hide-option-to-send-feedback"></a>Mostrar u ocultar opción para enviar comentarios

Especifica si los usuarios pueden enviar comentarios a Microsoft yendo a `Help`  >  `Send Feedback` .

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | userInitiatedFeedback |
| **Tipo de datos** | Cadena |
| **Posibles valores** | habilitado (predeterminado) <br/> deshabilitado |
| **Comments** | Disponible en Microsoft Defender para endpoint versión 101.19.61 o posterior. |

### <a name="endpoint-detection-and-response-preferences"></a>Preferencias de detección y respuesta de extremos

Administrar las preferencias del componente de detección y respuesta de puntos de conexión (EDR) de Microsoft Defender para Endpoint para Mac.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | edr |
| **Tipo de datos** | Diccionario (preferencia anidada) |
| **Comments** | Vea las secciones siguientes para obtener una descripción del contenido del diccionario. |

#### <a name="device-tags"></a>Etiquetas de dispositivo

Especifique un nombre de etiqueta y su valor. 

- La etiqueta GROUP, etiqueta el dispositivo con el valor especificado. La etiqueta se refleja en el portal en la página del dispositivo y se puede usar para filtrar y agrupar dispositivos.

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | tags |
| **Tipo de datos** | Diccionario (preferencia anidada) |
| **Comments** | Vea las secciones siguientes para obtener una descripción del contenido del diccionario. |

##### <a name="type-of-tag"></a>Tipo de etiqueta

Especifica el tipo de etiqueta

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | clave |
| **Tipo de datos** | Cadena |
| **Posibles valores** | `GROUP` |

##### <a name="value-of-tag"></a>Valor de etiqueta

Especifica el valor de la etiqueta

|||
|:---|:---|
| **Dominio** | `com.microsoft.wdav` |
| **Clave** | valor |
| **Tipo de datos** | Cadena |
| **Posibles valores** | cualquier cadena |

> [!IMPORTANT]  
> - Solo se puede establecer un valor por tipo de etiqueta.
> - El tipo de etiquetas es único y no debe repetirse en el mismo perfil de configuración.

## <a name="recommended-configuration-profile"></a>Perfil de configuración recomendado

Para empezar, se recomienda la siguiente configuración para que la empresa aproveche todas las características de protección que proporciona Microsoft Defender para endpoint.

El siguiente perfil de configuración (o, en el caso de JAMF, una lista de propiedades que podría cargarse en el perfil de configuración de configuración personalizada) será:
- Habilitar la protección en tiempo real (RTP)
- Especifique cómo se controlan los siguientes tipos de amenazas:
  - **Las aplicaciones potencialmente no deseadas (PUA)** están bloqueadas
  - **Las bombas de archivo** (archivo con una tasa de compresión alta) se auditan en Microsoft Defender para los registros de punto de conexión
- Habilitar actualizaciones automáticas de inteligencia de seguridad
- Habilitar la protección de entrega en la nube
- Habilitar el envío automático de muestra

### <a name="property-list-for-jamf-configuration-profile"></a>Lista de propiedades para el perfil de configuración de JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Perfil de Intune

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a>Ejemplo de perfil de configuración completa

Las siguientes plantillas contienen entradas para todas las configuraciones descritas en este documento y se pueden usar para escenarios más avanzados en los que quieras tener más control sobre Microsoft Defender para Endpoint para Mac.

### <a name="property-list-for-jamf-configuration-profile"></a>Lista de propiedades para el perfil de configuración de JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Perfil de Intune

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a>Validación de lista de propiedades

La lista de propiedades debe ser un archivo *.plist* válido. Esto se puede comprobar ejecutando:

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

Si el archivo está bien formado, el comando anterior genera `OK` y devuelve un código de salida de `0` . De lo contrario, se muestra un error que describe el problema y el comando devuelve un código de salida de `1` .

## <a name="configuration-profile-deployment"></a>Implementación de perfiles de configuración

Una vez que haya creado el perfil de configuración para su empresa, puede implementarlo a través de la consola de administración que usa su empresa. En las secciones siguientes se proporcionan instrucciones sobre cómo implementar este perfil con JAMF e Intune.

### <a name="jamf-deployment"></a>Implementación de JAMF

En la consola JAMF, abra **Perfiles** de configuración de equipos, vaya al perfil de configuración que desea usar y, a  >  continuación, seleccione **Configuración personalizada**. Cree una entrada con `com.microsoft.wdav` como dominio de preferencia y cargue el *.plist* generado anteriormente.

>[!CAUTION]
>Debes escribir el dominio de preferencia correcto ( ); de lo contrario, Microsoft Defender no reconocerá las `com.microsoft.wdav` preferencias para endpoint.

### <a name="intune-deployment"></a>Implementación de Intune

1. Abra **Administrar configuración** de  >  **dispositivo**. Seleccione **Administrar**  >  **perfiles Crear**  >  **perfil**.

2. Elija un nombre para el perfil. Cambiar **Platform=macOS** a **Profile type=Custom**. Seleccione Configurar.

3. Guarde el .plist generado anteriormente como `com.microsoft.wdav.xml` .

4. Escriba `com.microsoft.wdav` como el nombre del perfil de configuración **personalizado**.

5. Abra el perfil de configuración y cargue el `com.microsoft.wdav.xml` archivo. (Este archivo se creó en el paso 3).

6. Seleccione **Aceptar**.

7. Seleccione **Administrar**  >  **asignaciones**. En la **pestaña Incluir,** seleccione **Asignar a todos los usuarios & Todos los dispositivos**.

>[!CAUTION]
>Debe escribir el nombre del perfil de configuración personalizado correcto; de lo contrario, Microsoft Defender no reconocerá estas preferencias para endpoint.

## <a name="resources"></a>Recursos

- [Referencia de los perfiles de configuración (documentación para desarrolladores de Apple)](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)