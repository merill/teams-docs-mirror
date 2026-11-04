---
layout: Conceptual
title: Teams Rooms Pro Management Portal Incident Notification Webhook Integration - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/pmp-incident-webhook-integration
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: This article explains how the incident notification webhook integration from the Teams Rooms Pro Management Portal functions.
author: MattSlomka
ms.author: mattslomka
manager: kimmatlock
ms.service: msteams
ms.topic: feature-guide
ms.date: 2026-08-06T00:00:00.0000000Z
ms.subservice: itpro-rooms
locale: en-us
document_id: c175467f-940a-a1e6-3e12-229b33ca518b
document_version_independent_id: c175467f-940a-a1e6-3e12-229b33ca518b
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/pmp-incident-webhook-integration.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/pmp-incident-webhook-integration
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/pmp-incident-webhook-integration.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: b9a87543-d505-a2ee-e389-e56b9dfdea4b
---

# Teams Rooms Pro Management Portal Incident Notification Webhook Integration - Microsoft Teams | Microsoft Learn

## Overview

Modern enterprises rely on incident management systems to ensure rapid detection, response, and resolution of IT and operational issues. While many organizations use various incident management tools, integration across platforms is often limited. The Teams Rooms Pro Management portal **Incident Notification Webhook Integration** provides a universal, flexible mechanism to synchronize Teams Rooms Pro Management incident notifications to any endpoint you choose, enabling real-time automation, improved visibility, and streamlined workflows.

### Key Features

- **Universal Integration:** Works with any incident management or Information Technology Service Management (ITSM) tool that accepts incoming webhooks.
- **Customizable Incident Notification Event Subscriptions:** Choose which incident types, signals, and devices to subscribe to.
- **Flexible Webhook Architecture:** Webhook-based, event-driven notifications for incident creation, updates, and closure.
- **Secure & Scalable:** Supports POST authentication method and handles high event volumes.
- **Customized Payloads:** Map webhook data to your system’s schema (JSON/XML).
- **Comprehensive Logging:** Track delivery, failures, and retries in a dashboard.

### How It Works

1. **Teams Rooms Pro Management Incident Notification Occurs:** An incident is detected on one of your Teams Rooms devices.
2. **Integration Triggers:** The system sends an HTTP POST request (webhook) to a predefined endpoint that you choose with the incident data.
3. **Data Sent:** The request contains incident details (Incident ID, status, description, etc.) in JSON format.
4. **Receiver Processes Data:** Your receiving system processes the data and takes action.

Note

Customers host their own endpoint to receive and transform the payload for their specific tool and manage authentication.

### Limitations

- Only available in Commercial and Government Community Cloud (GCC). GCC-High and DoD aren't supported.
- Not available in the Teams Rooms Multitenant Management Portal.
- Only 10 integrations can be created from a single portal.

### Role-Based access control

Setting up an incident management integration is limited to specific roles:

- Teams Rooms Pro Manager
- Teams Administrator
- Microsoft 365 Global Administrator

## Setting Up an Incident Webhook Subscription

The Teams Rooms Pro management portal uses a wizard to define parameters to be added in the JSON payload object of your Incident alert notifications. These variables are used to dynamically populate specific values from the alert configuration in the notification payload. It includes things like the IncidentType that gives the current monitor status in the notification. When a notification is sent, your JSON payload includes the parameters selected through the setup wizard. Name of the alert in the delivered payload.

1. Access the [Teams Rooms Pro Management Portal](/en-us/microsoftteams/rooms/enrolling-mtrp-managed-service)
2. In the left navigation select **Settings** then **Integrations**.
3. Select **Create Incident Webhook**. A wizard is presented to step through creating the webhook subscription.
4. Under General, enter a Name and Description for this webhook subscription and press Next.
5. Enter a valid endpoint address. Only HTTPS (port 443) and HTTP (port 80) URLs are supported.
6. HTTP Method defaults to POST. Select **Next**.
7. Event Subscription section is where you decide to select the events you want included in the payload:

    | Event Subscription | Description | Values |
    | --- | --- | --- |
    | Device Type | Device Category | Teams Rooms on WindowsTeams Rooms on AndroidTouch Console (Teams Rooms on Android Console)Teams PanelIP PhoneSIPSIP Analog |
    | Ticket State | Incident State | NewInvestigatingResolvedClosed |
    | Ticket Severity | Defined Severity | CriticalImportantRecommendationWarning |

    1. Check the box next to each **Device Type** you want included.
    2. Check the box next to each Ticket state to include:
        1. **New:** Incident IDs that need to be remediated. These are issues that the Teams Rooms Pro management system has identified as requiring human intervention to remediate.
        2. **Resolved:** When the Teams Rooms Pro management system identifies that an active incident’s issue has been detected as being healthy again, the state of the Incident ID will be changed to Resolved. If the same issue for that signal presents itself again within a **seven (7)** day period, the ***same*** incident ID will be set to an Active state again. It repeats this step until the current issue has been resolved for more than seven days, in which case, the State will be set to Closed.
        3. **Closed:** An incident ID moves to a Closed state when the signal remains healthy for more than seven days. If a signal alerts for the same issue after the incident ID has been closed, a new Incident ID will be generated.
    3. If you're noticing that the same incident ID has an opening date that's more than seven days from the current date, the incident has been presenting itself within the seven day window resolved cycle since that incident ID’s create date. It means that the underlying issue isn't resolved.
8. Select the device types that you want to filter incidents by:

    1. Incident **state**: Select the ticket states that you want to filter incidents by.
    2. Incident **severity:** Select the ticket severities that you want to filter incidents by.
9. **Room group selection:** Select the rooms or room groups that you want to send to the webhook. You can choose multiple rooms or room groups. For more on room groups, [learn more.](/en-us/microsoftteams/rooms/rooms-pro-rbac)
10. **Signals selection:** Select the signals that you want to send to the webhook. You can choose multiple signals. For more on Teams Rooms Pro management signals [Learn more.](/en-us/microsoftteams/rooms/signals)
11. **Acknowledging Terms:** If you add an external webhook endpoint for your tenant, your Customer Data ([Product Terms](https://www.microsoft.com/licensing/terms)) will be handled and stored in accordance with their terms and conditions. By clicking Next, you acknowledge and accept full responsibility for all third-party services and their terms of use. Microsoft isn't responsible for the data that is transferred out of our systems to your endpoints.

## Testing the Payload

See webhook authentication guide.

### Sample Payload

```json
{
    "ID": "db5tadj8-8c7e-4dd9-9be8-a44f77c3217e",
    "eventType": "Incident",
    "data": "{\"ID\":\"BCDEFG-U73655\",	\"signal\":\"History of Poor Call Quality\",	\"category\":\"Connectivity\",	\"deviceType\":\"Mtr\",	\"description\":null,	\"severity\":\"Recommendation\",	\"state\":\"New\",	\"waitingOn\":\"Customer\",	\"createdAt\":\"2025-09-04T14:46:08Z\",	\"updatedAt\":\"2025-09-11T14:21:09Z\",	\"resolvedAt\":null,	\"closedAt\":null,	\"assignedTo\":{\"ID\":\"ba3d1d4f-5e9c-427d-9cae-83b0221b50e2\",	\"name\":\"Managed Rooms Service\",	\"email\":\"mgrooms@microsoft.com\"},	\"createdBy\":{\"ID\":\"ba3d1d4f-5e9c-427d-9cae-83b0221b50e2\",	\"name\":\"Managed Rooms Service\",	\"email\":\"mgrooms@microsoft.com\"},	\"devices\":[{\"ID\":\"fj2e6p-bd155b483c3a123c07502d5e163b5662ead5639fb270eaccaea9fc6bb9fa788d\",	\"displayName\":\"MTR VM - Dev Lab 37\",	\"hostname\":\"WPAD\",	\"roomAccount\":\"lab37_dev@devtest1234567890.onmicrosoft.com\",	\"deviceType\":\"CollabBar\"}],	\"linkedIncidents\":[],	\"conversation\":[{\"message\":\"A significant number of calls/meetings have been reported as Poor Call Quality events. Common causes include recurring transient network issues on media streams (audio, video or screen sharing), Firmware/driver issues in audio devices (audio frame capture/render), unexpected restarts/crashes of the MTR app mid-call.\\u003Cbr /\\u003EReview the \\u0027Call Quality\\u0027 section of the room for more details about the specific poor call issues.\\u003Cbr /\\u003E\\u003Cbr /\\u003EMore information how call records are classified can be found at \\u003Ca href=\\u0022https://learn.microsoft.com/en-us/microsoftteams/stream-classification-in-call-quality-dashboard\\u0022 target=\\u0022_blank\\u0022\\u003Ehttps://learn.microsoft.com/en-us/microsoftteams/stream-classification-in-call-quality-dashboard\\u003C/a\\u003E.\",	\"author\":{\"ID\":\"ba3d1d4f-5e9c-427d-9cae-83b0221b50e2\",	\"name\":\"Managed Rooms Service\",	\"email\":\"mgrooms@microsoft.com\"},	\"timestamp\":\"2025-09-04T14:46:08Z\"}],	\"closureSummary\":null,	\"@odata.type\":\"#teams.devicemgmt.incident\"	}",
    "timestamp": "2025-09-11T14:22:47.7740395Z",
    "_rid": "uXR2APCgu6sJAAAAAAAAAA==",
    "_self": "dbs/uXR2AA==/colls/uXR2APCgu6s=/docs/uXR2APCgu6sJAAAAAAAAAA==/",
    "_etag": "\"2600d368-0000-0800-0000-68c2db380000\"",
    "_attachments": "attachments/",
    "_ts": 1757600568
}
```

### Data Dictionary

| Data | Type | Values | Description | Examples |
| --- | --- | --- | --- | --- |
| ID | text | xxxxxx-xxxxxx | Incident number in the Pro Management Portal | FJ2E6P-XRBE9U |
| signal | text |  | Type of incident in the Pro Management portal. [Learn more](/en-us/microsoftteams/rooms/signals) for a list of all signals. |  |
| category | text | One of the following:<br>- AccountManagement<br>- ConfigurationAndSettings<br>- Connectivity<br>- Display<br>- HardwareAndPeripherals<br>- Security<br>- OsFirmwareAps<br>- Projection<br>- Other | There are nine signal categories that all Pro Management signals fall under: Account Management, Configuration and settings, Connectivity, Display, Hardware and peripherals, Security, OS, Firmware, and Apps, Projection, Other | HardwareAndPeripherals |
| deviceType | set | MTR | Microsoft Teams Rooms (MTR) on Windows device |  |
|  |  | CollabBar | Teams Rooms on Android compute device |  |
|  |  | TouchConsole | Teams Rooms on Android touch console |  |
|  |  | SurfaceHub | Legacy Surface Hub 1/2S (Team OS) |  |
|  |  | TeamsPanel | Teams Panel |  |
| description | text |  | Brief description of the incident type and it's importance. This is the same for any incident of the same type. | Example: "Triggered when the room is low on available disk space. When this alert is active, an automatic remediation job is executed outside business hours (between 9PM and 2AM of local room time zone) to remove cleanable files and free enough space to maintain daily operation." |
| severity | set | One of the following: |  |  |
|  |  | Critical | Used for types of issues that cause significant disruption. Any incident of this type marks the room as unhealthy in the Teams Rooms Pro portal. |  |
|  |  | Important | Used for types of issues that cause significant disruption. Any incident of this type marks the room as unhealthy in the Teams Rooms Pro portal. |  |
|  |  | Warning | Typically used for issues that don't require immediate attention but may configure potential risks. An incident with this severity doesn't cause the room to be unhealthy. |  |
|  |  | Security | Aligned with Warning impact, typically used for issues related to security vulnerabilities. Similar to Warning, an incident with this severity doesn't cause the room to be unhealthy. |  |
|  |  | Recommendation | Used for suggestions or best practices that can improve stability, user experience, or maintainability. |  |
| state | set | One of the following: |  |  |
|  |  | Watching | Transitory state that the ticket may be in before being activated. The underlying signal is reporting as unhealthy to the Pro management service. This state is only applicable to signals with a watching period, [Learn More](/en-us/microsoftteams/rooms/signals). |  |
|  |  | New | The incident was activated but hasn't been acted upon yet. The underlying signal is reporting as unhealthy to the Pro management service. |  |
|  |  | Investigating | The incident is currently being investigated (for example, scenarios where an automated diagnostic/remediation may still run.). The underlying signal is reporting as unhealthy to the Pro management service. |  |
|  |  | Resolved | The underlying signal is no longer reported as unhealthy, hence the signal has been marked as resolved. It will remain in that state for the next seven days, after which it transitions to Closed. |  |
|  |  | Closed | The incident has been closed, meaning no further action is expected or required. This represents the final state of the incident. |  |
| waitingOn | set | Microsoft | If Microsoft automation is scheduled to execute any initial remediation attempts. In the portal, the incident shows as *System Investigating*. |  |
|  |  | Customer | If the incident needs further investigation by the customer. In the portal, the incident shows as *Needs action*. |  |
| createdAt | (datetime) | mm-dd-yyyy 00:00:00 | Date when the issue was first detected. |  |
| updatedAt | (datetime) | mm-dd-yyyy 00:00:00 | Date when the incident was last updated. |  |
| resolvedAt | (datetime) | mm-dd-yyyy 00:00:00 | Date when it was last resolved. An incident can be resolved and reopened (New/Investigating state) if the underlying signal becomes unhealthy within seven days. If it hasn't been resolved, expect this to be null. |  |
| closeAt | (datetime) | mm-dd-yyyy 00:00:00 | Date when it was closed. If it hasn't been closed, expect this to be null. |  |
| devices |  | Each entry contains: | List of devices affected. NOTE: Currently, each ticket is currently applicable to only one room. |  |
| ID | string |  | Unique identifier of the device in Pro Management portal, for which this incident has been created. |  |
| displayName | string |  | Display name of the resource account signed in on the MTR system. In case there's none, it's be the device's hostname. |  |
| hostname | string |  | Device's hostname |  |
| roomAccount | string |  | Resource account user principal name (UPN) configured on the device. |  |
| linkedIncidents |  |  |  |  |
| conversation: |  | Each message contains: | List of messages posted to the incident by the Pro Management portal, including the initial message and any automated remediation messages posted by the system. |  |
|  | string | message | Text message added to the incident page. |  |
|  |  | author: |  |  |
|  | datetime | mm-dd-yyy 00:00:00 | date and time when the message was posted |  |
| closureSummary: |  |  | additional information of the incident closure (only applicable if the incident is in Closed state) |  |
| description | string |  | Brief description of the cause for closure. | Example: "Resolved without action after 168 hours (seven days)" |
| reasonCodes | list | One of the following: | List of reason codes that lead to incident closure. |  |
|  |  | DesiredConfiguration | When the customer suppresses/disables the incident type in the portal. |  |
|  |  | SelfResolved | When the incident remains in resolved state for more than seven days |  |

## Privacy Information

Microsoft Teams Rooms Pro Management incident webhook feature follows [Microsoft privacy](https://privacy.microsoft.com/) policies. Before you set up an incident integration, consider your privacy, security, and compliance requirements from the tenant organization.

### Audit Reporting

Teams Rooms Pro managers can run an audit log to identify the success of payload sessions and users who have incident integration permissions. Log history is available under **Settings/General**.

### Terms of use

Microsoft reserves the right to update and modify this feature at any time without notice to you. The current licensing model allows only 10 integrations from the Teams Rooms Pro management portal. See [Microsoft Terms of Use](https://www.microsoft.com/legal/terms-of-use)