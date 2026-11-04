---
layout: Conceptual
title: Manage Copilot for Teams phones - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/phones/copilot-teams-phones
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
description: Learn how to manage Microsoft Copilot in Teams for Teams phone devices with summarized call transfers and in-call Copilot.
author: mkbond007
manager: dansimp
ms.author: mabond
ms.reviewer: prashibadkur
ms.service: msteams
ms.topic: tutorial
ms.date: 2025-07-30T00:00:00.0000000Z
ms.subservice: itpro-devices
audience: Admin
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier1
- teams-copilot
- magic-ai-copilot
locale: en-us
document_id: 88e53fbd-cea1-73b6-0eca-9d6bb5b2ccae
document_version_independent_id: 88e53fbd-cea1-73b6-0eca-9d6bb5b2ccae
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/phones/copilot-teams-phones.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: phones/copilot-teams-phones
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/phones/copilot-teams-phones.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/46e3c7c4-fe77-4a6e-b40a-44c569819fa5
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/d0c6fab8-2d7d-4bb0-bf40-589e08d7c132
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 73ce45eb-2334-e63b-2307-ea7e0490379a
---

# Manage Copilot for Teams phones - Microsoft Teams | Microsoft Learn

Microsoft Copilot on Teams phone devices brings AI-powered assistance directly into your calling experience. Copilot is supported in:

- Call transfers: AI generated summaries that provide transferees with essential context after they accept a transferred call.
- In-call copilot: Real-time assistance during 1:1 and group calls for summary, recap, and other insights.

## Copilot in Call Transfers

When a user is on a Teams call and needs to transfer it to another colleague—whether for an escalation, further expertise, or availability—the call transfer summary feature in Copilot ensures a seamless handoff. The user can enable the **Generate call summary** option before completing the transfer, which allows Copilot to create a concise, AI-generated summary of the conversation. This summary includes key details such as the caller's name, the reason for the call, actions already taken, and suggested next steps. Once the call is transferred, the recipient sees the call topic on the incoming call screen and a call summary in the call window after answering, enabling them to greet the caller with full context and continue the conversation without requiring the caller to repeat information. This feature enhances the quality of support and collaboration by preserving context across participants.

Important

To ensure full call context is captured, we recommend that your users start transcription or recording at the beginning of the call. Delaying transcription until later in the conversation might result in the loss of important early call details. Copilot doesn't generate a summary if transcription or recording isn't turned on.

## In-call Copilot

When a user is in a call, Copilot provides real-time support through in-call assistance. By selecting the Copilot button during the call, users can access AI-generated insights such as summary, action items, and other follow ups. This feature allows participants to stay focused on the conversation while Copilot captures key points and action items in the background. The feature is especially useful in dynamic or fast-paced discussions, where manual note-taking may be impractical. In-call Copilot ensures that important context is preserved and easily accessible, enhancing collaboration and reducing the need for post-call clarification.

Important

To retain these insights after the call ends, we recommended to enable transcription or recording at the beginning of the conversation.

## Configure Copilot on Teams phones

### Step 1: Assign licenses

For Copilot features on work on Teams phones, you must assign the following licenses to your users:

- A Microsoft 365 subscription that includes Teams or a Microsoft 365 (no Teams) subscription with a separate Teams license.
- For Public Switched Telephone Network (PSTN) calls, you must also assign a Teams Phone license and have a calling plan for your users. For information on Teams Phone licensing, see [Microsoft Teams add-on licenses](/en-us/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing). To learn more about PSTN connectivity options, see [PSTN connectivity options](/en-us/microsoftteams/pstn-connectivity).
- A *Microsoft Copilot* license. For more information, see [Where can I get Microsoft Copilot?](https://support.microsoft.com/topic/40a622db-6d25-4266-b008-4bbcb55cf52f).

### Step 2: Enable transcription or recording during calls

For Teams phones, users can only use Copilot when you enable one or both of the following settings:

- **Copilot** &gt; **Enabled with Transcript**: Users who have this policy assigned can use Copilot when transcription is started during a call. If transcription isn't enabled, then users can't see the Copilot option for the call.
- **Cloud Recording for Calling** &gt; **Enabled**: Users who have this policy enabled can record 1:1 and group calls directly to the cloud and use Copilot during a call.

You can enable these calling policy settings using the Teams admin center or PowerShell. For more information, see [Manage Microsoft Copilot in Teams calls](/en-us/microsoftteams/copilot-teams-calling-transcription) and [Configure call recording, transcription, and captions in Teams](/en-us/microsoftteams/call-recording-transcription-captions).

## Call experience

### Copilot in Call Transfers

1. Make sure call transcription is turned on by selecting **More**.
2. While on a call on your phone, select **Transfer**, then check **Generate and send call summary with transfer**.
3. Select **Transfer now** to transfer the call. The transferee will see an AI-generated Call summary after they accept the call under **More**.

### In-call Copilot

1. Make sure call transcription is turned on by selecting **More**.
2. While on a call on your Teams phone device, select **More** &gt; **Copilot**.
3. Use the following prompts to catch up on the call real-time:

    - Summarize the call
    - What questions were asked
    - List action items