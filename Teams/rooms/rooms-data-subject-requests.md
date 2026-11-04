---
layout: Conceptual
title: Respond to Data Subject Requests (DSRs) for Microsoft Teams Rooms Pro Management - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/rooms-data-subject-requests
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Respond to Data Subject Requests (DSRs) for Microsoft Teams Rooms Pro Management
author: srpall
ms.author: srpall
ms.service: msteams
ms.topic: best-practice
ms.date: 2026-05-13T00:00:00.0000000Z
ms.subservice: itpro-rooms
locale: en-us
document_id: 1c0660a9-71ff-3d11-f6a5-1bce7105fbed
document_version_independent_id: 1c0660a9-71ff-3d11-f6a5-1bce7105fbed
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/rooms-data-subject-requests.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/rooms-data-subject-requests
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/rooms-data-subject-requests.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 48a7f1d6-d714-1f81-9b9a-443e674a7c06
---

# Respond to Data Subject Requests (DSRs) for Microsoft Teams Rooms Pro Management - Microsoft Teams | Microsoft Learn

#### Overview

Microsoft Teams Rooms Pro Management (PMP) is a cloud-based management service for monitoring, managing, and operating Microsoft Teams Rooms devices and peripherals. The service provides proactive monitoring, incident detection, update management, operational insights, and remote management capabilities for supported Teams Rooms devices.

This document explains how organizations can respond to Data Subject Requests (DSRs), including requests to access, export, or delete personal data processed by Teams Rooms Pro Management, in accordance with privacy regulations such as GDPR and similar laws.

In most cases, the customer organization acts as the data controller and Microsoft acts as the data processor for customer data processed within Teams Rooms Pro Management.

#### Types of Data Processed by Teams Rooms Pro Management

Teams Rooms Pro Management primarily processes operational and device-related data associated with meeting room systems, including:

- Device health and telemetry
- Peripheral inventory and firmware details
- Configuration and policy data
- Room resource account information
- Incident and remediation history
- Device activity and operational logs
- Update deployment status
- Service diagnostics and monitoring data

The service is designed around room and device management rather than individual user profiling. Incidental references to users may appear in operational logs or diagnostic records during device usage.

#### Responding to Data Subject Requests

Organizations may receive DSRs requesting:

- Access to personal data
- Export of personal data
- Correction of inaccurate data
- Restriction of processing
- Deletion of personal data

As the data controller, the customer organization is responsible for evaluating and fulfilling DSR requests.

#### Discovering Personal Data

Personal data related to Teams Rooms Pro Management may exist in:

- Device inventory records
- Operational activity logs
- Incident history
- Audit records
- Resource account configurations
- Service integration logs
- Support and diagnostic records

Organizations can use Microsoft Purview eDiscovery, Microsoft 365 audit logs, Teams Admin Center, Microsoft Entra ID audit logs, and PMP reporting/export capabilities to identify relevant data.

#### Accessing and Exporting Data

Administrators can export operational and device data from Teams Rooms Pro Management using built-in reporting and export capabilities available in the portal. Exported data may include device inventory details, incident records, monitoring history, configuration state, update deployment status, and activity/audit information.

#### Deleting Personal Data

Deletion scenarios may include:

- Removing room resource accounts
- Decommissioning Teams Rooms devices
- Deleting operational logs according to retention policies
- Removing diagnostic or support records
- Deleting exported data maintained by the organization

Certain operational and security logs may be retained for limited periods to support service reliability, security monitoring, compliance obligations, and incident investigation.

#### Remote Access and Diagnostic Data

Teams Rooms Pro Management may allow authorized Microsoft personnel or support workflows to remotely access managed room devices for troubleshooting and remediation purposes.

Organizations should ensure appropriate administrative access controls are configured, audit logging is enabled, RBAC policies are enforced, and support access follows organizational compliance policies.

#### Data Residency and Compliance

Teams Rooms Pro Management operates within Microsoft cloud environments and inherits many compliance, privacy, and security commitments applicable to Microsoft 365 and Microsoft Teams services.

Microsoft provides compliance capabilities supporting GDPR, data residency commitments, audit logging, encryption, RBAC, and retention/lifecycle management.

#### Customer Responsibilities

Customers using Teams Rooms Pro Management are responsible for:

- Determining lawful basis for processing
- Managing user notices and consent where required
- Configuring retention and compliance policies
- Responding to DSR requests
- Managing administrator access
- Governing exported operational data
- Reviewing integrations with third-party systems

#### Related Documentation

[Microsoft Teams Rooms Pro Management Documentation](/en-us/microsoftteams/rooms/rooms-pro-management)

[Microsoft GDPR Overview](/en-us/compliance/regulatory/gdpr)

[Office 365 Data Subject Requests for GDPR and CCPA](/en-us/compliance/regulatory/gdpr-dsr-office365)

[Microsoft Trust Center Privacy Overview](https://www.microsoft.com/trust-center/privacy)