---
layout: Conceptual
title: Manage join verification for external presenters in Teams events - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/events-external-presenter-join-verification
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: anahitab
ms.reviewer: kasimpso
ms.date: 2026-06-26T00:00:00.0000000Z
ms.topic: overview
ms.service: msteams
ms.subservice: meetings
audience: admin
f1.keywords:
- NOCSH
description: Learn how to manage whether external presenters are required to verify their identities before they join Teams events in your organization.
locale: en-us
document_id: 125742bf-4a77-df6b-ecb3-45ea7380e902
document_version_independent_id: 125742bf-4a77-df6b-ecb3-45ea7380e902
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/events-external-presenter-join-verification.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: events-external-presenter-join-verification
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/events-external-presenter-join-verification.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 876b4881-1b40-50f9-a7e8-3457acfbd333
---

# Manage join verification for external presenters in Teams events - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of an X for no](/en-us/office/media/icons/cancel-teams.png)Meetings ![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Events

## Overview

In Teams events hosted by your organization, external presenters whose identities aren't verified are treated as anonymous users in the event. This includes external presenters who aren’t signed in with a personal Microsoft account or a work or school account.

As an admin, you can control whether anonymous and unverified external presenters must verify their identity before joining events.

### Verification required for external presenters

When verification is required:

- External presenters who have a personal Microsoft account or a work or school account are asked to sign in before they join an event.
- If they don't have an account, external presenters receive a one-time passcode in email and must enter it to join. After joining, a **Verified** label is displayed next to their name.

Organizers can control access by using the following Meeting options settings:

- **Yes verify accounts, only allowing invited presenters to join**
- **Yes verify accounts, letting uninvited users with the link join the lobby** (Default)

Note

External presenters who join by signing in with a personal Microsoft account are always placed in the lobby when verification is required.

### Verification not required for external presenters

When verification isn't required, organizers can choose whether to require verification for external presenters by using the following Meeting options settings:

- **Yes verify accounts, only allowing invited presenters to join**
- **Yes verify accounts, letting uninvited users with the link join the lobby**
- **No verification needed** (Default)

## Manage join verification for external presenters

You can use the Teams admin center or PowerShell to manage verification for external presenters.

| Teams admin center policy value | PowerShell setting value | Behavior |
| --- | --- | --- |
| Yes, verify accounts | EOTP | When organizers with this policy create events, external presenters must verify their identity before joining by signing in to their personal Microsoft account or their work or school account, or by entering a one-time email passcode. |
| No verification needed | None | **This is the default value**. When organizers with this policy create events, they can decide whether external presenters must verify their identity before joining. |

### Using the Teams admin center

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Events policies**.
2. Select an existing policy or create a new one.
3. In the **Verify external presenters before joining an event** dropdown list, select **Yes verify accounts** or **No verification needed**.
4. Select **Save**.

### Using PowerShell

To manage verification for external presenters in events that organizers with this policy create, use the `-ExternalPresenterJoinVerification` parameter in the [CsTeamsEventsPolicy](/en-us/powershell/module/microsoftteams/set-csteamseventspolicy) PowerShell cmdlet.

To require external presenters to verify their identity before joining events created by organizers with this policy, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -ExternalPresenterJoinVerification EOTP
```

To allow organizers with this policy to decide whether verification is required for external presenters in events they create, run the following command:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -ExternalPresenterJoinVerification None
```