---
layout: Conceptual
title: Partner management for customers - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/multi-tenant-management-customer
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: kimmatlock
ms.date: 2025-01-27T00:00:00.0000000Z
ms.topic: how-to
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier1
ms.localizationpriority: medium
search.appverid: MET150
description: partner management for customers.
f1keywords: 
locale: en-us
document_id: 8e563c14-36f9-bfe2-2e05-4285284c5cdd
document_version_independent_id: 8e563c14-36f9-bfe2-2e05-4285284c5cdd
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/multi-tenant-management-customer.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/multi-tenant-management-customer
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/multi-tenant-management-customer.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 6b3890b0-6113-ea5f-229d-deb5a9ff741c
---

# Partner management for customers - Microsoft Teams | Microsoft Learn

Partner management in the Teams Rooms Pro Management service enables customers to seamlessly delegate access and responsibilities to one or many partner organizations. Partners can only manage rooms that they're assigned to manage.

## On-boarding partners

Invite partners through the Teams Rooms Pro Management portal to establish the relationship between your organization and the partner organization’s tenant.

Note

The partner needs to satisfy the prerequisites in [Multi-tenant Management for Partners](multi-tenant-management-partner).

### Invitation to partner

In this method, you should know the domain name of the partner (such as Contoso.com).

**To initiate the invite**

1. Sign in to the Teams Rooms Pro Management portal as a Teams Rooms Pro Manager.
2. Go to **Settings &gt;** **Partners**, then select **Add partner.**
3. Enter the domain name in the first row.
4. Configure the number of days until the invitation expires by entering an integer from 1-30.
5. Configure the events that require a change control approval. By default, all controls are set to **Auto approval.**

    Note

    *Only autoapprove is currently available for now.*

    1. *Manual approval:* When the partner performs the action, an approval request is generated for the customer to review and approve. The action isn't implemented until the request has been approved.
    2. *Auto- approval:* When the partner performs the action, no approval request is generated and the action is implemented immediately.
6. Select **Next.**
7. Assign rooms the partner manages, then select **Next.**
8. To continue, review the terms and select **I agree.**
9. Review the details of the invitation.
10. Select **Add partner** to send the invitation.

The invitation is sent to the Tenant managers in the partner instance for review. The first partner user that accepts the invitation establishes the link between the Partner and your tenant and assign Primary admins. There is no special association with the user that establishes the link, which allows flexibility should the user be reassigned. There must always be at least one user in the primary admin role.

To manage users in the primary admin role, see [Multi-tenant Management for Partners](multi-tenant-management-partner).

## Off-boarding partners

**To remove a partner**

1. Sign in to the Teams Rooms Pro Management-Multi-tenant Management (MTM) portal as a Teams Rooms Pro Manager.
2. Navigate Go to **Settings &gt; Partners.**
3. Select the partner you wish to remove.
4. In the customer detail pane, select **Remove partner.**
5. Select **Delete**.
6. At the confirmation prompt to terminate the association between you and the customer tenant, select **Delete**.

## Managing partner roles

Partner roles allow for your partner to more granularly delegate responsibilities to additional personnel. The concept of these roles is the same as described in [Role-based access control](rooms-pro-rbac). It's important to note that partner roles are distinct from your custom roles.

The **Primary admin** role is the only built-in role for each partner you add. This role has almost all permissions to the rooms you assigned that partner for the TRM service (see Table 1). For example, if you have rooms across the globe and assign a partner to manage All US rooms, the primary admin would only be able to manage and delegate permissions for those rooms. In this case, the primary admins for this Partner have no visibility to any rooms outside of the US.

### Adding Primary admins to partner

If you already sent an invitation to a partner and wish to delegate more rooms, you can add rooms to the partner admin role.

**To add new rooms to an existing partner**

1. Sign in to the Teams Rooms Pro Management-MTM portal as a Teams Rooms Pro Manager.
2. Go to **Settings &gt; Roles.**
3. Select **Partner roles.**
4. Select the **Primary admin** role for the corresponding partner name.
5. In the role pane, select **Assignments**.
6. Select the **Assigned admins** assignment.
7. In the Assigned admins assignment pane, select **Scope**.
8. Select **Edit**.
9. Search for the rooms you wish to add and select the desired room.
10. To confirm the changes, select **Save**.

### Table 1

| Feature | Permission | **Teams Rooms Pro Manager** | **Site Lead** | **Site Tech** | **Partner admin** |
| --- | --- | --- | --- | --- | --- |
| Rooms | View | ✔ | ✔ | ✔ | ✔ |
|  | Modify | ✔ | ✔ | ✔ | ✔ |
|  | Reset key | ✔ |  |  |  |
|  | Download key | ✔ | ✔ | ✔ |  |
|  | Unenroll | ✔ | ✔ | ✔ |  |
|  | Create | ✔ | ✔ |  |  |
| Group management | View | ✔ | ✔ |  | ✔ |
|  | Modify | ✔ | ✔ |  |  |
|  | Create | ✔ | ✔ |  |  |
| Update ring management | View | ✔ | ✔ |  | ✔ |
|  | Modify | ✔ | ✔ |  | ✔ |
| Reports | View | ✔ | ✔ |  | ✔ |
|  | Create customer incident | ✔ | ✔ | ✔ | ✔ |
| Tickets Management | View | ✔ | ✔ | ✔ | ✔ |
|  | Update | ✔ | ✔ | ✔ | ✔ |
| Pro Management Settings | View | ✔ |  |  |  |
|  | Modify | ✔ |  |  |  |
| Role management | View | ✔ |  |  | ✔ |
|  | Modify | ✔ |  |  | ✔ |

## Security

As the end customer, you retain control over access to your data and can completely remove a partner at any time.

With the delegated access feature, a partner doesn't gain any other privileges outside of the Teams Rooms Pro Management portal. However, any data present in the Teams Rooms Pro Management service derived from other Microsoft products is considered data in the service. As an example, while call quality reports are derived from Teams call quality data, any data in the Teams Rooms Pro Management portal is in the permission scope.

No permissions are granted to Microsoft Entra ID or the Teams Admin Center or any other Microsoft product. Furthermore, partners don't have any access to view or modify rooms not defined in the invitation scope.

Data resides in the customer’s tenant and isn't copied to the partner’s tenant.

The MTM portal uses Microsoft Entra authentication to validate the sign in credentials of the partner. At this time, the customer’s authentication policies don't apply to the partner. For example, if the customer has a multifactor authentication policy, it doesn't translate to the partner.

To pull logs on partner activity, see [Auditing](multi-tenant-auditing).

Note

Microsoft Entra auditing and O365 auditing don't capture logs from the Teams Rooms Pro Management portal.