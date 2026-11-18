---
layout: Conceptual
title: Certified third-party synthetic audio and video detection in Microsoft Teams meetings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/third-party-synthetic-audio-video-detection-meetings
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: LanaChin8
ms.author: v-lanchin
manager: v-jesserowe
ms.reviewer: smahadevan
ms.date: 2026-11-18T00:00:00.0000000Z
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
audience: admin
f1.keywords:
- NOCSH
ms.custom:
- security
description: Learn how to set up and configure third-party synthetic audio and video detection for Teams meetings.
locale: en-us
document_id: 2b3d74b3-ca2c-b2a3-47a7-992fbf638549
document_version_independent_id: 2b3d74b3-ca2c-b2a3-47a7-992fbf638549
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/third-party-synthetic-audio-video-detection-meetings.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: third-party-synthetic-audio-video-detection-meetings
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/third-party-synthetic-audio-video-detection-meetings.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 5f68e1e7-e86e-b1ab-4252-bcaedee62ef4
---

# Certified third-party synthetic audio and video detection in Microsoft Teams meetings - Microsoft Teams | Microsoft Learn

**APPLIES TO:**![Image of a checkmark for yes](/en-us/office/media/icons/success-teams.png)Meetings ![Image of an x for No](/en-us/office/media/icons/cancel-teams.png)Events ![Image of an x for No](/en-us/office/media/icons/cancel-teams.png)Calls

Note

This feature is currently in public preview.

## Overview

As AI-generated audio and video become more sophisticated, attackers can convincingly impersonate executives, colleagues, job candidates, or vendors during live meetings. These attacks typically target the moments where money moves or access is granted, such as payment approvals, remote hiring interviews, and live social engineering.

Microsoft Teams supports certified third-party synthetic audio and video detection solutions directly within Teams meetings. As an admin, you choose a detection provider that meets your organization's needs and turn on detection through a Teams meeting policy. When detection is on for a meeting, Teams automatically adds the provider's detection bot to the meeting. The provider analyzes meeting media for signs of synthetic or manipulated audio and video. In public preview, detection results are surfaced through the provider's experience. Native Teams detection alerts, participant indicators, and associated actions are available separately in private preview.

Important

This feature is in public preview. Features, user interface labels, and supported scenarios can change before general availability.

## How it works

Third-party synthetic audio and video detection uses a partner ecosystem model. Certified partners provide the detection models. Microsoft provides the platform, the admin policy controls, a standardized API for reporting detections, and the in-meeting experience.

1. An admin allows the provider's Teams app and grants admin consent to the permissions it needs.
2. The admin turns on synthetic audio and video detection in a Teams meeting policy, selects one provider, and assigns the policy to organizers.
3. Organizers who have the policy see a **Detect synthetic audio and video** option in meeting options for supported meetings.
4. When the option is on, Teams automatically adds the provider's detection bot to the meeting when it starts.
5. The provider's service analyzes participant audio and video and reports detections back to Teams through the Microsoft Graph API.
6. Teams shows the detection to the organizer in the meeting, identifies the flagged participant, and lets the organizer take action.

## Key terms

| Term | Description |
| --- | --- |
| Detection provider | An independent software vendor (ISV) whose synthetic media detection solution integrates with Teams through the Teams synthetic audio and video detection certification program. |
| Detection bot | The provider's media bot that Teams adds to detection-enabled meetings to receive audio and video for analysis. |
| Detection (verdict) | The provider's assessment that a specific participant's audio, video, or both appear to be synthetic or manipulated. |
| Modality | The media type that a detection applies to: audio, video, or audio and video. |
| Detection-enabled meeting | A supported meeting where the synthetic audio and video detection meeting option is on. |

## What certification means

Providers that are available in Teams have gone through the Teams synthetic audio and video detection certification program. Certification validates how a provider's solution integrates with and surfaces detections in Teams at enterprise scale, including integration quality, scale, reliability, security, compliance, and consistent disclosure to users.

Certification doesn't validate the accuracy of a provider's detection models. Detection results are produced by the provider, and the provider is responsible for its detection quality. Evaluate each provider's accuracy claims, privacy statement, and terms against your organization's requirements before you deploy.

## Available detection providers (coming soon)

Each provider has its own licensing, service activation, data handling, and support model. Contact the provider directly to purchase or activate its service.

## Prerequisites

Before you set up synthetic audio and video detection, make sure that:

- Your organization has an agreement with a supported detection provider and has completed any provider-side licensing or service activation.
- You have the provider's exact Teams app name or app ID, its requested permissions and their purpose, and its support contact.
- You have the Teams Administrator role (or higher) to manage the app and meeting policies.
- A Global Administrator or Privileged Role Administrator is available to grant admin consent to the provider app. For more information, see [Grant tenant-wide admin consent to an application](/en-us/entra/identity/enterprise-apps/grant-admin-consent?#prerequisites).
- You reviewed the provider's privacy statement, terms of service, media processing behavior, data retention and residency, and any participant consent requirements that apply in your jurisdictions.

Users don't need to install the provider's app themselves. The policy-driven experience relies on admin consent, provider selection, and meeting policy assignment.

## Supported scenarios

| Scenario | Supported in preview |
| --- | --- |
| Scheduled Teams meetings | Yes |
| Recurring Teams meetings | Yes |
| End-to-end encrypted (E2EE) meetings | No |
| Events (such as town halls and webinars) | No |
| 1:1 and group calls, including PSTN calls | No |

## Set up synthetic audio and video detection

### Step 1: Allow the provider app

1. In the left navigation of the Teams admin center, go to **Teams apps** &gt; **Manage apps**.
2. Search for the provider's app by its exact name or app ID.
3. Open the app and confirm that it's the provider's synthetic audio and video detection app, published by the expected publisher.
4. Make sure the app is **Allowed** for your organization. If your organization uses app-centric management, make the app available to the users or groups that will receive the detection meeting policy. If your organization uses app permission policies, make sure the applicable policy allows the app.

We recommend one of the following scoping approaches:

- Make the app available to all users, and assign the detection meeting policy to all or a subset of users and groups.
- Scope the app and the detection meeting policy to the same users and groups.

If an organizer has the detection meeting policy but the provider app isn't available to them, the detection bot doesn't join their meetings.

### Step 2: Grant admin consent

Detection providers typically request the following Microsoft Graph permissions:

| Permission | Why it's needed |
| --- | --- |
| Join group calls and meetings as an app | Lets the detection bot join detection-enabled meetings. |
| Join group calls and meetings as a guest | Lets the detection bot join meetings as a guest participant. |
| Access media streams in a call as an app | Lets the provider receive meeting audio and video for analysis. |
| Read online meeting details | Lets the provider identify the meeting it's analyzing. |
| Read user's online meetings | Lets the provider read meeting information for in-scope organizers. |
| Sign in and read user profile | Standard sign-in permission for the app. |

1. From the **Manage apps** page, open the provider app and select the **Permissions** tab.
2. Select **Grant admin consent**. Alternatively, use the consent link that the provider supplies.
3. Review each requested permission before you accept it.

    [![Screenshot of permissions on the Permission tab for granting admin consent.](media/third-party-synthetic-audio-video-detection-consent.png)](media/third-party-synthetic-audio-video-detection-consent.png#lightbox)

Caution

Don't grant consent if the app identity, publisher, requested permissions, or sign-in experience don't match the provider's documentation. Contact the provider to resolve the discrepancy first.
4. Confirm with the provider that the service reports successful activation for your tenant.

### Step 3: Turn on detection in a meeting policy

You can use the Teams admin center or PowerShell to turn on synthetic audio and video detection in a meeting policy.

#### Use the Teams admin center

1. In the left navigation of the Teams admin center, go to **Meetings** &gt; **Meeting policies**.
2. Select an existing meeting policy, such as the Global (Org-wide default) policy, or create a custom policy.
3. Under **Meeting protection**, select a provider from the **Synthetic audio and video detection provider** dropdown list.

    [![Screenshot of the Synthetic audio and video detection provider option to select a provider.](media/third-party-synthetic-audio-video-detection-provider.png)](media/third-party-synthetic-audio-video-detection-provider.png#lightbox)

    The provider list shows the providers currently available through this feature for your organization. A provider appearing in the list doesn't mean that app availability, admin consent, or provider-side activation is complete.
4. The **Turn on synthetic audio and video protection** setting appears and is on by default. If you're editing a policy in which it was previously turned off, make sure you turn it on.
5. Select **Save**.

Note

If the provider isn't listed, verify feature and provider availability and app configuration. If the provider appears but detection doesn't start, verify consent, provider-side activation, the organizer's effective policy, and the meeting option.

#### Use PowerShell

Use the [Set-CsTeamsMeetingPolicy](/en-us/powershell/module/microsoftteams/set-csteamsmeetingpolicy) cmdlet with the `-SyntheticMediaDetection` and `-SyntheticMediaDetectionAppId` parameters.

Here are some examples.

##### Enable detection and select the provider

```powershell
Set-CsTeamsMeetingPolicy -Identity "<policy name>" -SyntheticMediaDetection Enabled -SyntheticMediaDetectionAppId "<provider bot application ID>"
```

##### Verify the saved policy settings

```powershell
Get-CsTeamsMeetingPolicy -Identity "<policy name>" | Select-Object Identity, SyntheticMediaDetection, SyntheticMediaDetectionAppId
```

##### Disable detection

```powershell
Set-CsTeamsMeetingPolicy -Identity "<policy name>" -SyntheticMediaDetection Disabled
```

### Step 4: Assign the policy

Assign the meeting policy to the organizers or groups you want to protect. Policy assignment can take up to 24 hours to take effect, although it typically completes within an hour. To check a user's effective policy, go to **Users** &gt; **Manage users** in the Teams admin center, select the user, and review their assigned policies.

Detection applies to meetings based on the organizer's meeting policy. Attendees, including people from outside your organization, don't need the policy for their media to be analyzed in a detection-enabled meeting.

## Organizer experience

Note

This experience is available in private preview on Teams desktop and web only.

Organizers who are assigned the detection meeting policy see the **Detect synthetic audio and video** option in **Meeting options** &gt; **Advanced protection** for supported meetings.

- When the option is on, Teams adds the provider's detection bot to the meeting automatically.
- When the option is off, the bot doesn't join and the meeting isn't analyzed.

## In-meeting experience

Note

This experience is available only in private preview.

### Detection bot

When a detection-enabled meeting starts, the provider's detection bot joins automatically and appears as a participant in the meeting roster. The bot receives meeting media for analysis. It doesn't speak, present, or share content.

### Detection alerts

When the provider detects synthetic or manipulated media from a participant, it reports the detection to Teams. Teams then:

- Shows an in-meeting alert to the organizer that identifies the flagged participant and the provider that made the detection.
- Shows an indicator next to the flagged participant in the roster.

### Organizer actions

From the alert or the roster, the organizer can:

- **Remove** the flagged participant from the meeting.
- **Mark as not a concern** to dismiss the alert when the organizer has verified the participant.

Teams doesn't remove participants automatically. The organizer decides what action to take.

## Interaction with other Teams features

The following table describes how other Teams features and settings affect synthetic audio and video detection.

| Feature or setting | Behavior |
| --- | --- |
| End-to-end encryption (E2EE) | E2EE meetings aren't supported. When E2EE is on for a meeting, the detection bot can't receive media, so detection doesn't run. |
| App blocked or consent removed | App availability and required consent must remain in place for the integration to function. A provider appearing in the dropdown doesn't confirm that these prerequisites are met. |
| Recording and transcription | Enabling this feature doesn't itself start a Teams recording or transcription. |
| Meeting templates and sensitivity labels | A template or label that enforces E2EE prevents detection for that meeting. |

## Privacy and data handling

- **Media processing**: In a detection-enabled meeting, participant audio and video are sent to the detection provider's service for analysis. Processing, retention, and residency of that media are governed by the provider's terms and privacy statement.
- **Participant notice**: The detection bot is visible in the meeting roster so participants can see that the meeting is being analyzed.
- **Consent**: Detection follows the participant consent model for the preview and is controlled by the detection provider
- **Microsoft data**: Teams doesn't store raw media or biometric artifacts from detections.
- **Trust boundary**: Detections are the provider's verdicts. Teams shows provider attribution alongside every detection.

## FAQ

### Does Microsoft perform the detection?

No. The certified provider that your organization selects performs the analysis. Microsoft provides the platform, policy controls, API, and integration framework for doing that.

### Are external participants analyzed?

Yes. In a detection-enabled meeting, the provider analyzes media from participants, including guests, external users, and anonymous users, subject to the consent model.

### Does the provider record my meeting?

The detection bot receives media for analysis but doesn't create a Teams recording or transcript. Review the provider's terms for how it processes and retains media.

### What happens if the provider's service goes down?

The meeting continues normally without detection.