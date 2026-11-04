---
layout: Conceptual
title: Application-based authentication in Teams PowerShell Module - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-powershell-application-authentication
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
ms.date: 2022-09-09T00:00:00.0000000Z
manager: sshastri
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: msteams-admin
ms.collection:
- M365-collaboration
description: Learn about application-based authentication in Teams PowerShell Module, used for administration of Microsoft Teams.
locale: en-us
document_id: 32304edf-550b-72a3-57df-6dcc29dba56d
document_version_independent_id: 32304edf-550b-72a3-57df-6dcc29dba56d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-powershell-application-authentication.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-powershell-application-authentication
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-powershell-application-authentication.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 5704bdef-9f71-b94b-5e2f-a4ed7ab0427e
---

# Application-based authentication in Teams PowerShell Module - Microsoft Teams | Microsoft Learn

Application-based authentication is supported now in Teams PowerShell Module with

- Versions 4.7.1-preview or later in commercial & GCC environments.
- Versions 5.0.1-preview or later in GCC High & DoD environments.

## Cmdlets Supported

All cmdlets are supported now, except for the cmdlets mentioned below.

- New-Team
- Set-CsOnlineApplicationInstance
- [Get|New|Sync]-CsOnlineApplicationInstance *(not supported only in GCC High & DoD environments)*
- \*PolicyPackage\*
- \*-CsTeamsShiftsConnection\*
- \*-CsBatchTeamsDeployment\*
- Get-MultiGeoRegion
- Get-AllM365TeamsApps
- [Get|Update]-M365TeamsApp
- Get-M365UnifiedCustomPendingApps
- [Get|Update]-M365UnifiedTenantSettings
- Update-M365UnifiedCustomPendingApp

## Examples

The following examples show how to use Teams PowerShell Module with the Microsoft Entra app-based authentication:

- Connect using a certificate thumbprint:

    ```powershell
    Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
    ```

    When you use the CertificateThumbprint parameter, the certificate needs to be installed on the computer where you're running the command. The certificate should be installed in the user certificate store.
- Connect using a certificate object:

    ```powershell
    Connect-MicrosoftTeams -Certificate <%X509Certificate2 object%> -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
    ```

    When you use the Certificate parameter, the certificate doesn't need to be installed on the computer where you're running the command. The certificate can be remotely stored & fetched when the script is run. The Certificate parameter is available from Teams PowerShell Module version 4.9.2-preview or later.
- Connect using Access Tokens:

    Access Tokens can be retrieved via the login.microsoftonline.com endpoint. It requires two Access Tokens – "MS Graph" and "Skype and Teams Tenant Admin API" resources.

    ```powershell
    $ClientSecret   = "…"
    $ApplicationID = "00000000-0000-0000-0000-000000000000"
    $TenantID = "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
    
    $graphtokenBody = @{   
       Grant_Type    = "client_credentials"   
       Scope         = "https://graph.microsoft.com/.default"   
       Client_Id     = $ApplicationID   
       Client_Secret = $ClientSecret   
    }  
    
    $graphToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $graphtokenBody | Select-Object -ExpandProperty Access_Token 
    
    $teamstokenBody = @{   
       Grant_Type    = "client_credentials"   
       Scope         = "48ac35b8-9aa8-4d74-927d-1f4a14a0b239/.default"   
       Client_Id     = $ApplicationID   
       Client_Secret = $ClientSecret 
    } 
    
    $teamsToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $teamstokenBody | Select-Object -ExpandProperty Access_Token 
    
    Connect-MicrosoftTeams -AccessTokens @("$graphToken", "$teamsToken")
    ```

## How does it work?

Teams PowerShell Module fetches the app-based token using the application ID, tenant ID and certificate thumbprint. The application object provisioned inside Microsoft Entra ID has a Directory Role assigned to it, which is returned in the access token. The session's role-based access control (RBAC) is configured using the directory role information that's available in the token.

## Setup Application-based authentication

An initial onboarding is required for authentication using application objects. Application and service principal are used interchangeably, but an application is like a class object while a service principal is like an instance of the class. You can learn more about these objects at [Application and service principal objects in Microsoft Entra ID](/en-us/azure/active-directory/develop/app-objects-and-service-principals).

Sample steps for creating applications in Microsoft Entra ID are mentioned below. For detailed steps, refer to this [article](/en-us/azure/active-directory/develop/howto-create-service-principal-portal).

1. Register the application in Microsoft Entra ID.
2. Assign API permissions to the application.

    | Cmdlets | Microsoft Graph API permission needed |
    | --- | --- |
    | All | `Organization.Read.All` |
    | Non \*-Cs cmdlets | `User.Read.All`, `Group.ReadWrite.All`, `AppCatalog.ReadWrite.All`, `TeamSettings.ReadWrite.All`, `Channel.Delete.All`, `ChannelSettings.ReadWrite.All`, `ChannelMember.ReadWrite.All` |
    | All (only when used with Administrative Units) | `RoleManagement.Read.Directory` |
    | \*-CsGroupPolicyAssignment, \*-CsGroupPolicyPackageAssignment (only when used with Administrative Units) | `GroupMember.Read.All` |

    Note

    There's no need to configure any API permission for "Skype and Teams Tenant Admin API". Configuring this permission might result in failures.
3. Generate a self-signed certificate.
4. Attach the certificate to the Microsoft Entra application.
5. Assign [Microsoft Entra roles](/en-us/microsoftteams/using-admin-roles#teams-roles-and-capabilities) to the application. Refer to this [Assign a role](/en-us/azure/active-directory/roles/manage-roles-portal#assign-a-role) procedure, but search for the application instead of a user.

The application needs to have the appropriate RBAC roles assigned. Because the apps are provisioned in Microsoft Entra ID, you can use any of the supported built-in roles.