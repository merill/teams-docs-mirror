---
layout: Conceptual
title: Remove an external chat from a user's view in Microsoft Teams (admin) - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/security-remove-external-chat
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: Dansimp
ms.author: dansimp
manager: dansimp
ms.date: 2023-12-01T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
ms.reviewer: 
audience: admin
ms.collection:
- trust-pod
description: Admin instructions for how to remove chat from a user external to an organization
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
locale: en-us
document_id: 92132c8d-8a5f-7e78-313a-c2521b248c3d
document_version_independent_id: 92132c8d-8a5f-7e78-313a-c2521b248c3d
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/security-remove-external-chat.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: security-remove-external-chat
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/security-remove-external-chat.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/12ed19f9-ebdf-4c8a-8bcd-7a681836774d
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/3a764584-4f97-452b-8f1d-36f19b12f6ae
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 2f4b01cc-bcc2-eb30-1b1f-439ad7e9e1dc
---

# Remove an external chat from a user's view in Microsoft Teams (admin) - Microsoft Teams | Microsoft Learn

As a tenant administrator, you can use the new [RemoveAllAccessForUser](/en-us/graph/api/chat-removeallaccessforuser) Graph API to remove an externally initiated chat from your user’s view.

Microsoft Teams admins might need to remove user chats created by people outside of your organization. For example, one of your users received a chat request from someone outside of your company. That chat could contain inappropriate or malicious content, and, as an admin, you can remove that chat to help protect your user.

To use the RemoveAllAccessForUser Graph API, you need to provide three parameters: the **tenantId**, the **userId**, and the **chatsId/threadId**. The **tenantId** is the unique identifier of your Teams tenant. The **userId** is the unique identifier of your user that you want to remove the chat for. The **chatsId/threadId** is the unique identifier of the Teams chat thread that you want to remove your user from.

You can obtain these three parameters from the new Unified Audit Log (UAL) events that are generated when an external user communicates with a user in your tenant. The UAL events contain information about the sender, the recipient, the chat thread, and the message. You can use the UAL events to identify the chat thread that you want to revoke access from, and then extract the **tenantId**, the **userId**, and the **chatsId/threadId** from the event details.

## Steps to use the RemoveAllAccessForUser Graph API

- Step 1: Search for the [UAL events](/en-us/purview/audit-teams-audit-log-events) that match your criteria. If you want to find all events where a user was added to a chat, you can use the "MemberAdded" event in your search query.
- Step 2: Extract the **tenantId**, the **userId**, and the **chatsId/threadId** from the UAL event details
- Step 3: Call the RemoveAllAccessForUser Graph API with the desired parameters

### Step 1: Search for UAL events

To search for specific UAL events, you can use the Search-UnifiedAuditLog graph API, or you can use the audit log search feature in the Microsoft Purview portal. The following instructions use the Microsoft Purview portal. Perform the following steps:

1. Sign in to https://purview.microsoft.com as an audit log administrator.
2. In the left navigation, select **Audit**.
3. On the Audit log search page, specify the following criteria:

    - On the Audit page, select Search.
    - Activities: Select MemberAdded (and optionally MessageReceived) from the **Activities – operation names** field and choose **MicrosoftTeams** for the **Workload**.
    - Date range: Select a date range that covers the time period when the external user communicated with the user in your tenant. (optional) Users: Enter the UPN of the user in your tenant who you are interested in.
4. Select **Search**. This command queues a search to run in the background.

Once complete, review the search results and identify the UAL events that involve the chat and user that you're interested in (Step 3 below).

### Step 2: Extract the tenantId, the userId, and the chatsId/threadId from the UAL event details

To extract the **tenantId**, the **userId**, and the **chatsId/threadId** from the UAL event details, you can use the **OrganizationId**, **UserKey**, and **ChatThreadId** fields of the event. If you searched for the **MemberAdded** event, you might see events where your users were added to an external chat and also where your users added an external user to a chat. Find the events where your user in your tenant is in the **Members** detail section (indicates that this is the user that was added—see figure 2 below). To do this, follow these steps:

1. Select one of the UAL events that involve the external user that you want to revoke access from.
2. On the Event details pane:

    - Copy the value of the **OrganizationId** field. This value is the **tenantId** of your Teams tenant.
    - Copy the value of the **UserKey** field. This value is the **userId** of the user in your tenant that was added to the chat.
    - Copy the value of the **ChatThreatId** field. This value is the **chatsId/threadId** of the Teams chat thread that the message belongs to.

See the following screenshot showing an example of a Purview search result detail:

![Microsoft Purview search details](media/graph-delete-purview-search-detail.png)*Figure 1 (details from UAL MemberAdded event)*

![Microsoft Purview member details](media/graph-delete-purview-member-detail.png)*Figure 2 (Members detail from MemberAdded UAL event)*

### Step 3: Call the RemoveAllAccessForUser Graph API with the desired parameters

To call the RemoveAllAccessForUser Graph API with the parameters, you need to use an HTTP POST request to the graph API:

```http
POST https://graph.microsoft.com/beta/chats/{chatsId}/removeAllAccessForUser 
```

Replace **{chatsId}** with the **Id** of the chat you want to act on. The request body should contain a JSON **user** object with the following properties:

- **tenantId**: The tenantID of your Teams tenant.
- **Id**: The userID of the user in your tenant that you want to move the chat from.

For example, a request might look like this:

```http
POST https://graph.microsoft.com/beta/chats/19:7d8980.........f94061cf8c2@unq.gbl.spaces/removeAllAccessForUser 
Content-Type: application/json 

{ 
  "user": { 
    "id" : "d864e79f-……..-0eeb4d61fdc2", 
    "tenantId": "2a690434-………-13600199a" 
  } 
} 
```

To authenticate the request, you need to provide a valid access token in the Authorization header. The access token should have the Chat.ReadWrite.All permissions. To obtain the access token, you can use the Azure AD OAuth 2.0 endpoint. For more information, see [Microsoft Graph - Get access on behalf of a user](/en-us/graph/auth-v2-user).

If the request is successful, the response has a status code of “204 No Content” and an empty body. If the request fails, the response has an error code and a message that explains the reason for the failure.

There are many ways to call a Microsoft Graph API – if you're unfamiliar with the process, start with an interactive tool such as [Graph Explorer](/en-us/graph/graph-explorer/graph-explorer-overview). Some admins create an app or use PowerShell to interact with Graph APIs.

### Sample Code

The following PowerShell code can be used as a starting point. This code shows how to acquire the User token, create a client App that has the necessary permissions, and how to use that client App to call the Graph API to remove the message.

```powershell
param(
    # Tenant id for the user whom the chat access is going to be removed
    [Parameter(Mandatory=$true)]
    [String]
    $TenantId,
 
    # User id for the user whom the chat access is going to be removed
    [Parameter(Mandatory=$true)]
    [String]
    $UserId,
 
    # Id of the chat that from which access will be removed
    [Parameter(Mandatory=$true)]
    [String]
    $ThreadId
)

# These may not all be necessary in your environment
# Install Microsoft.Graph.Authentication module for all users (requires admin rights)
if (Get-Module -ListAvailable -Name Microsoft.Graph.Authentication) {
    Write-Host "Microsoft.Graph.Authentication module found." -ForegroundColor "Green"
} 
else {
    Write-Host "Microsoft.Graph.Authentication module not found. Installing"
    Install-Module Microsoft.Graph.Authentication -Scope AllUsers -Force 
}
 
# Install Microsoft.Graph.Applications module for all users (requires admin rights)
if (Get-Module -ListAvailable -Name Microsoft.Graph.Applications) {
    Write-Host "Microsoft.Graph.Applications module found." -ForegroundColor "Green"
} 
else {
    Write-Host "Microsoft.Graph.Application module not found. Installing"
    Install-Module Microsoft.Graph.Applications -Scope AllUsers -Force 
}
 
# Install MSAL.PS module for all users (requires admin rights)
if (Get-Module -ListAvailable -Name MSAL.PS) {
    Write-Host "MSAL module found."  -ForegroundColor "Green"
} 
else {
    Write-Host "MSAL module not found. Installing"
    Install-Module MSAL.PS -Scope AllUsers -Force 
}

# Connect to graph and verify that a client application exists for this purpose - if not, create one
Connect-MgGraph -Scopes "Application.ReadWrite.All", "DelegatedPermissionGrant.ReadWrite.All"
 
# Get client app info
$App = Get-MgApplication -Filter "DisplayName eq 'RemoveAllAccessForUserApp'"
$createAppParams = @{
    publicClient = @{	redirectUris = "https://login.microsoftonline.com/common/oauth2/nativeclient"}
}
 
# If client app is not found. Create it
if ($null -eq $App)
{
    Write-Host "Client app not found. Creating new one." -ForegroundColor "Yellow"
    $App = New-MgApplication -DisplayName 'RemoveAllAccessForUserApp' @createAppParams
    Write-Host "Client app created. Waiting for 5 seconds before continuing." -ForegroundColor "Yellow"
    Start-Sleep -Seconds 5
}
else 
{
    $AppId = $App.AppId
    Write-Host "Client app with id '$AppId' found'" -ForegroundColor "Green"
}

$ClientId = $App.AppId
 
# Now that we have the ID for our client application, we can call the RemoveAccessForUser API...
# Msal parameters required to get access token.
$MsalParams = @{
    ClientId = $ClientId
    TenantId = $TenantId
    Scopes   = 'Chat.ReadWrite.All'
}

# Get access token, it will prompt for interactive login   
$MsalResponse = Get-MsalToken @MsalParams
$AccessToken  = $MsalResponse.AccessToken

# Request authorization header containing the access token
$AuthHeader = @{
    Authorization = "Bearer $AccessToken"
}
 
# Request url
$apiUrl = "https://graph.microsoft.com/beta/chats/$ThreadId/removeAllAccessForUser"
 
# Prepare request body
$Body = @{user = @{	id = "$UserId"	tenantId = "$TenantId"}
}
 
$Body = $Body | ConvertTo-Json
 
# Execute request
Write-Host "Executing RemoveAllAccessForUser request."
 
try {
    Invoke-RestMethod  -Headers $AuthHeader -Uri $apiUrl -Method POST -ContentType 'application/json' -Body $Body 
    Write-Host "Rquest to RemoveAllAccessForUser api succeeded." -ForegroundColor "Green"
} catch {
    Write-Host "Request to RemoveAllAccessForUser api failed." -ForegroundColor "Red"
    Write-Host "StatusCode:" $_.Exception.Response.StatusCode.value__ 
    Write-Host "StatusDescription:" $_.Exception.Response.StatusDescription
    $receiveStream = $_.Exception.Response.GetResponseStream();
    Write-Host ([System.Text.Encoding]::ASCII).GetString($receiveStream.ToArray())
}
 
Write-Host "Disconnecting from Microsoft Graph!"
Disconnect-MgGraph
```