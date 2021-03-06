---
title: Usar un script para agregar usuarios a una retención en un caso de exhibición de documentos electrónicos principal
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo ejecutar un script para agregar buzones & OneDrive para la Empresa sitios a una nueva retención asociada a un caso de exhibición de documentos electrónicos en el centro de Microsoft 365 cumplimiento.
ms.openlocfilehash: d6e6ff1ca053fd8c729054490e78ef42dc64e829
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909920"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>Usar un script para agregar usuarios a una retención en un caso de exhibición de documentos electrónicos principal

PowerShell & Centro de seguridad y cumplimiento proporciona cmdlets que le permiten automatizar tareas que consumen mucho tiempo relacionadas con la creación y administración de casos de exhibición de documentos electrónicos. Actualmente, el uso del caso de exhibición de documentos electrónicos principal en el Centro de seguridad y cumplimiento de & para poner un gran número de ubicaciones de contenido de custodia en espera lleva tiempo y preparación. Por ejemplo, antes de crear una retención, debe recopilar la dirección URL de cada OneDrive para la Empresa sitio que desee poner en espera. A continuación, para cada usuario que desee poner en espera, debe agregar su buzón y su OneDrive para la Empresa sitio a la retención. Puede usar el script de este artículo para automatizar este proceso.
  
El script le pide el nombre del dominio de Mi sitio de su organización (por ejemplo, en la dirección URL , el nombre de un caso de exhibición de documentos electrónicos existente, el nombre de la nueva retención asociada al caso, una lista de direcciones de correo electrónico de los usuarios que desea poner en espera y una consulta de búsqueda que se usará si desea crear una retención basada en `contoso` https://contoso-my.sharepoint.com) consultas. A continuación, el script obtiene la dirección URL del sitio de OneDrive para la Empresa para cada usuario de la lista, crea la nueva retención y, a continuación, agrega el buzón y el sitio OneDrive para la Empresa para cada usuario de la lista a la retención. El script también genera archivos de registro que contienen información sobre la nueva retención.
  
Estos son los pasos para que esto suceda:
  
[Paso 1: Instalar el Shell de administración de SharePoint Online](#step-1-install-the-sharepoint-online-management-shell)
  
[Paso 2: Generar una lista de usuarios](#step-2-generate-a-list-of-users)
  
[Paso 3: Ejecutar el script para crear una retención y agregar usuarios](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>Antes de agregar usuarios a una retención

- Debe ser miembro del grupo de roles administrador de exhibición de documentos electrónicos en el Centro de seguridad y cumplimiento de & y administrador de SharePoint Online para ejecutar el script en el paso 3. Para obtener más información, vea [Assign eDiscovery permissions in the Office 365 Security & Compliance Center](assign-ediscovery-permissions.md).

- Se puede agregar un máximo de 1.000 buzones y 100 sitios a una retención asociada a un caso de exhibición de documentos electrónicos en el Centro de seguridad & cumplimiento. Suponiendo que todos los usuarios que desee poner en espera tienen un sitio de OneDrive para la Empresa, puede agregar un máximo de 100 usuarios a una retención mediante el script de este artículo.

- Asegúrese de guardar la lista de usuarios que cree en el paso 2 y el script del paso 3 en la misma carpeta. Esto facilitará la ejecución del script.

- El script agrega la lista de usuarios a una nueva retención asociada a un caso existente. Asegúrese de que el caso con el que desea asociar la retención se crea antes de ejecutar el script.

- El script de este artículo admite la autenticación moderna al conectarse a PowerShell del Centro de seguridad & cumplimiento y SharePoint Shell de administración en línea. Puede usar el script tal como está si es un Microsoft 365 o una Microsoft 365 GCC organización. Si es una organización de Office 365 Alemania, una organización de Microsoft 365 GCC High o una organización de Microsoft 365 DoD, tendrá que editar el script para ejecutarlo correctamente. En concreto, debe editar la línea y usar los parámetros ConnectionUri y `Connect-IPPSSession` *AzureADAuthorizationEndpointUri* (y los valores adecuados para el tipo de organización) para conectarse a *PowerShell* del Centro de seguridad & cumplimiento. Para obtener más información, vea los ejemplos de [Conectar a PowerShell del Centro de & seguridad.](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)

- El script se desconecta automáticamente de PowerShell & Centro de seguridad y cumplimiento y SharePoint Shell de administración en línea.

- El script incluye un control de errores mínimo. Su objetivo principal es poner de forma rápida y sencilla el buzón y el OneDrive para la Empresa sitio de cada usuario en espera.

- Los scripts de ejemplo que se proporcionan en este tema no son compatibles con ningún servicio o programa de soporte técnico estándar de Microsoft. Los scripts de ejemplo se proporcionan tal cual, sin garantía de ningún tipo. Además, Microsoft se exime de todas las garantías implícitas, incluidas (sin limitación) las garantías implícitas de comerciabilidad o idoneidad para un propósito específico. El usuario asume todos los riesgos derivados del uso o del rendimiento de los scripts de ejemplo y la documentación. Microsoft, sus autores o cualquier persona relacionada con la creación, producción o entrega de los scripts no serán en ningún caso responsables de cualesquiera daños (incluidos, sin limitación, los daños producidos por la pérdida de beneficios comerciales, interrupción de la actividad comercial, pérdida de información empresarial u otras pérdidas económicas) derivados del uso o de la imposibilidad de uso de los scripts de ejemplo o la documentación, incluso aunque Microsoft tenga constancia de la posibilidad de que dichos daños se produzcan.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Paso 1: Instalar el Shell de administración de SharePoint Online

El primer paso es instalar el Shell SharePoint administración en línea si aún no está instalado en el equipo local. No es necesario usar el shell en este procedimiento, pero debe instalarlo porque contiene los requisitos previos requeridos por el script que ejecuta en el paso 3. Estos requisitos previos permiten que el script se comunique con SharePoint Online para obtener las direcciones URL de los OneDrive para la Empresa web.
  
Vaya [a Configurar el](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) entorno Windows PowerShell del Shell de administración en línea de SharePoint y realice los pasos 1 y 2 para instalar el Shell de administración en línea de SharePoint en el equipo local.

## <a name="step-2-generate-a-list-of-users"></a>Paso 2: Generar una lista de usuarios

El script del paso 3 creará una retención asociada a un caso de exhibición de documentos electrónicos y agregará los buzones y los sitios OneDrive para la Empresa de una lista de usuarios a la retención. Solo puede escribir las direcciones de correo electrónico en un archivo de texto o puede ejecutar un comando en Windows PowerShell para obtener una lista de direcciones de correo electrónico y guardarlas en un archivo (ubicado en la misma carpeta en la que guardará el script en el paso 3).
  
Este es un comando de PowerShell (que se ejecuta mediante PowerShell remoto conectado a la organización de Exchange Online) para obtener una lista de direcciones de correo electrónico para todos los usuarios de la organización y guardarlo en un archivo de texto denominado HoldUsers.txt.
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

Después de ejecutar este comando, abra el archivo de texto y quite el encabezado que contiene el nombre de la propiedad,  `PrimarySmtpAddress` . A continuación, quite todas las direcciones de correo electrónico excepto las de los usuarios que desea agregar a la retención que creará en el paso 3. Asegúrese de que no hay filas en blanco antes o después de la lista de direcciones de correo electrónico.
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>Paso 3: Ejecutar el script para crear una retención y agregar usuarios

Al ejecutar el script en este paso, se le pedirá la siguiente información. Asegúrese de tener esta información lista antes de ejecutar el script.
  
- **Sus credenciales de usuario:** El script usará sus credenciales para conectarse al Centro de seguridad & cumplimiento con PowerShell. También usará estas credenciales para obtener acceso a SharePoint Online para obtener las OneDrive para la Empresa url de la lista de usuarios.

- **Nombre del dominio SharePoint:** El script le pide que escriba este nombre para que pueda conectarse al centro SharePoint administración. También usa el nombre de dominio para las direcciones ONEDRIVE url de la organización. Por ejemplo, si la dirección URL del centro de administración es y la dirección URL de OneDrive es , escribiría cuando el script le pida `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` el nombre de `contoso` dominio.

- **Nombre del caso:** Nombre de un caso existente. El script creará una nueva retención asociada a este caso.

- **Nombre de la retención:** El nombre de la retención que el script creará y asociará con el caso especificado.

- **Consulta de búsqueda para una retención basada en consulta:** Puede crear una retención basada en consultas para que solo se mantenga en espera el contenido que cumpla los criterios de búsqueda especificados. Para poner todo el contenido en espera, simplemente presione **ENTRAR** cuando se le pida una consulta de búsqueda.

- **Activar o no la retención:** Puede hacer que el script se active después de crearlo o que el script cree la retención sin habilitarlo. Si no tiene el script en espera, puede activarlo más adelante en el Centro de seguridad y cumplimiento de & o ejecutando los siguientes comandos de PowerShell:

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **Nombre del archivo de texto con** la lista de usuarios: el nombre del archivo de texto del paso 2 que contiene la lista de usuarios que se agregarán a la retención. Si este archivo se encuentra en la misma carpeta que el script, simplemente escriba el nombre del archivo (por ejemplo, HoldUsers.txt). Si el archivo de texto está en otra carpeta, escriba el nombre de ruta de acceso completo del archivo.

Después de recopilar la información que el script le pedirá, el paso final es ejecutar el script para crear la nueva retención y agregarle usuarios.
  
1. Guarde el texto siguiente en un archivo Windows PowerShell script mediante un sufijo de nombre de archivo de `.ps1` . Por ejemplo, `AddUsersToHold.ps1`.

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

# Load the SharePoint assemblies from the SharePoint Online Management Shell
# To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
{
    $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
    $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
    $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
    if (!$SharePointClient)
    {
        Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
        return;
    }
}

# Get other required information
do{
$casename = Read-Host "Enter the name of the case"
$caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
if($caseexists -ne 'True')
{""
write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
""}
}While($caseexists -ne 'True')
""
do{
$holdName = Read-Host "Enter the name of the new hold"
$holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
if($holdexists -eq 'True')
{""
write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
""}
}While($holdexists -eq 'True')
""
$holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
""
$holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
do{
""
$inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
""
$fileexists = test-path -path $inputfile
if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
}while($fileexists -ne 'True')
#Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
    #in the list are unique.
  [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
  [int]$dupl = $emailAddresses.count
  [array]$emailAddresses = $emailAddresses | select-object -unique
  $dupl -= $emailAddresses.count
#Validate email addresses so the hold creation does not run in to an error.
if($emailaddresses.count -gt 0){
write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
""
Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
""
$finallist =@()
foreach($emailAddress in $emailAddresses)
{
if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
{$finallist += $emailaddress}
else {"Unable to find the user $emailaddress"
[array]$excludedlist += $emailaddress}
}
""
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
""
Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
}
else{
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
}
""
}
else {"No valid locations were identified. Therefore, the hold wasn't created."}
#write log files (if needed)
$newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
$newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
{
Write-Host "Generating output files..." -foregroundColor Yellow
if($ODAdded.count -gt 0){
"OneDrive Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
if($ODExluded.count -gt 0){ 
"Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
"================================" | add-content .\LocationsNotOnHold.txt
$ODExluded | add-content .\LocationsNotOnHold.txt}
if($finallist.count -gt 0){
" " | add-content .\LocationsOnHold.txt
"Exchange Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
if($excludedlist.count -gt 0){
" "| add-content .\LocationsNotOnHold.txt
"Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
"===============================" | add-content .\LocationsNotOnHold.txt
$excludedlist | add-content .\LocationsNotOnHold.txt}
$FormatEnumerationLimit=-1
if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
}
}
else {"The hold wasn't created because no valid entries were found in the text file."}
""
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. En el equipo local, abra Windows PowerShell y vaya a la carpeta donde guardó el script.

3. Ejecute el script; por ejemplo:

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. Escriba la información que el script le pida.

   El script se conecta a PowerShell del Centro de seguridad & cumplimiento y, a continuación, crea la nueva retención en el caso de exhibición de documentos electrónicos y agrega los buzones y OneDrive para la Empresa para los usuarios de la lista. Puede ir al caso en la página **exhibición** de documentos electrónicos del Centro de seguridad y & cumplimiento para ver la nueva retención.

Una vez que el script ha terminado de ejecutarse, crea los siguientes archivos de registro y los guarda en la carpeta donde se encuentra el script.
  
- **LocationsOnHold.txt:** Contiene una lista de buzones y sitios OneDrive para la Empresa que el script colocó correctamente en espera.

- **LocationsNotOnHold.txt:** Contiene una lista de buzones y OneDrive para la Empresa sitios que el script no ha puesto en espera. Si un usuario tiene un buzón, pero no un sitio OneDrive para la Empresa, el usuario se incluiría en la lista de sitios OneDrive para la Empresa que no se colocaron en espera.

- **GetCaseHoldPolicy.txt:** Contiene el resultado del cmdlet **Get-CaseHoldPolicy** para la nueva retención, que el script ejecutó después de crear la nueva retención. La información devuelta por este cmdlet incluye una lista de usuarios cuyos buzones y sitios OneDrive para la Empresa se colocaron en espera y si la retención está habilitada o deshabilitada. 

- **GetCaseHoldRule.txt:** Contiene el resultado del cmdlet **Get-CaseHoldRule** para la nueva retención, que el script ejecutó después de crear la nueva retención. La información devuelta por este cmdlet incluye la consulta de búsqueda si usó el script para crear una retención basada en consultas.