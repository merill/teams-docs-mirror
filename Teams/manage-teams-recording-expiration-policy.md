---
layout: Conceptual
title: Manage Teams recording expiration policy - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/manage-teams-recording-expiration-policy
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn how to manage Teams recording expiration policies.
author: dj1298
manager: adam
ms.author: djball
ms.service: msteams
ms.topic: article
ms.date: 2026-05-06T00:00:00.0000000Z
ms.subservice: meetings
locale: en-us
document_id: 7bb309d5-750a-f266-95e4-1825e6ca4f92
document_version_independent_id: 7bb309d5-750a-f266-95e4-1825e6ca4f92
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/manage-teams-recording-expiration-policy.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: manage-teams-recording-expiration-policy
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/manage-teams-recording-expiration-policy.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/7428317a-e6c2-4461-ad3e-8a8ad3608734
- https://authoring-docs-microsoft.poolparty.biz/devrel/9d7be3ef-f27c-4c7f-9eba-67c3cd429995
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/e4f59707-f107-48f2-8d75-0afd91868cd7
- https://authoring-docs-microsoft.poolparty.biz/devrel/feeb50f3-b677-44f9-b3a6-5f2f58182b0d
platformId: 457e7d92-e76e-5936-3c58-d9dfd189f006
---

# Manage Teams recording expiration policy - Microsoft Teams | Microsoft Learn

Note

Expiration policies apply to meetings and events, such as webinars and town halls.

### Recordings and transcripts automatically expire

This setting allows you to manage storage by reducing the space that older recordings and transcripts use. OneDrive and SharePoint automatically monitor the expiration settings for all recordings and transcripts, moving them to the recycle bin once they reach their expiration date.

You can turn off the **Recordings and transcriptions automatically expire** setting in the Teams admin center under **Meetings** &gt; **Meeting policies** &gt; **Recording & transcription**.

### Default expiration time

This setting controls whether recordings and transcripts automatically expire. After turning on **Recordings and transcriptions automatically expire**, you'll get the option to set the **Default expiration time**, measured in days. Meeting recordings and transcripts have a default expiration time of 120 days.

Any changes to this setting only affect newly created recordings and transcripts. You can't change the expiration time on existing meeting recordings and transcripts.

The expiration value is an integer for days that you can set as follows:

- Minimum value: 1
- Maximum value: 99999
- -1 (PowerShell only) so the recordings and transcripts never expire

Note

The maximum default expiration time for A1 users is 30 days.

Published recordings for Teams events have an expiration of 30 days that's extendable to 90 days.

To set the expiration time using PowerShell, run the following command:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -NewMeetingRecordingExpirationDays <days>
```

### Recovering expired recordings

Users will see a banner message with "The recording is currently unavailable. Please check with organizer whether it’s still being uploaded, has expired, or has been deleted." on the meeting recap page once expired. Users may also report that the recording is missing or need assistance to recover a deleted recording.

The storage location depends on the meeting type:

- Non-channel meetings are stored in the meeting organizer’s OneDrive.
- Channel meetings are stored in the channel’s SharePoint site.

When the recording is expired, it will be moved to the Recycle Bin of where the recording was saved. Recovering files is time sensitive. Once recordings are purged from recycle, they **cannot** be recovered.

Note

If you're signed into OneDrive with a Microsoft personal account, items in the recycle bin are **automatically deleted 30 days** after they're put there. Files deleted from your Personal Vault will only show up in your recycling bin if your Personal Vault is unlocked before you check the recycle bin. You can use the Show Personal Vault items command in the recycle bin to unlock the Personal Vault and see those items. If you're signed in with a work or school account, items in the recycle bin are **automatically deleted after 93 days**, unless the administrator has changed the setting. See more information about how long deleted items are kept for work or school accounts.

#### Restore deleted files or folders from OneDrive

Determine which participant's OneDrive the recording was originally saved to. Generally, the recording is saved in the Organizer's OneDrive. For more details please review [Teams meeting recording and transcript storage and permissions in OneDrive and SharePoint](/en-us/microsoftteams/tmr-meeting-recording-change). That user can use the OneDrive recycle bin to recover deleted recordings. For additional details, please review [Restore deleted files or folders in OneDrive](https://support.microsoft.com/office/restore-deleted-files-or-folders-in-%20%20onedrive-949ada80-0026-4db3-a953-c99083e6a84f).

Go to the OneDrive website, and sign in with either your Microsoft account or your work or school account.

1. In the navigation pane, select Recycle bin.
2. Select the files or folders you want to restore by pointing to each item and clicking the circle check box that appears, and then click Restore.

#### Restore recordings that were deleted from OneDrive on your computer

If you deleted the files or folders from your OneDrive on your local computer, check your Recycle Bin (Windows) or Trash (Mac) to see if your files are there.

- To restore files from your Recycle Bin in Windows, open the Recycle Bin, select the files or folders you want to recover, then right-click them and select **Restore**. The file or folder will be restored to its original folder.
- To restore files from your Trash on a Mac, open the Trash, select the files or folders you want to recover, then right-click them and select **Put back**. The file or folder will be restored to its original folder.

#### Restore deleted files or folders from SharePoint Site

For Teams channel meetings, recordings are stored in SharePoint site. For additional details, please review [Use the SharePoint recycle bin.](https://support.microsoft.com/office/restore-items-in-the-recycle-bin-tha%20%20t-were-deleted-from-sharepoint-or-teams-6df466b6-55f2-4898-8d6e-c0dff851a0be)

You can restore items that you delete and items other people delete (as long as you have edit permissions).

1. Go to the SharePoint site that the items were deleted from. (In Microsoft Teams, from the Files tab at the top of your channel, select More &gt; Open in SharePoint.)
2. In the Quick Launch bar navigation on the bottom left of the screen, click Recycle bin.

    If you don't see the Recycle bin on the Quick Launch bar, follow these steps:

    1. Click Settings Office 365 Settings button, and then click Site contents.
    2. The recycle bin is in the top right portion of the Site Contents page.
3. On the Recycle bin page, click the box to the left of the items or files you want to restore.
4. Click **Restore**.
5. When an item is restored, it is restored to the same location that it was deleted from.

Note

If you don't see the item you're looking for, and it was deleted recently, a site collection administrator might be able to restore it from the site collection recycle bin. If you're the site collection administrator, see [Restore deleted items from the site collection recycle bin](https://support.microsoft.com/office/restore-deleted-items-from-the-site-collection-recycle-bin-5fa924ee-16d7-487b-9a0a-021b9062d14b).