---
layout: Conceptual
title: Microsofts SMS Messaging Policy - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/sms-microsoft-teams-policy
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: officedocspr5
ms.author: odocspr
manager: pamgreen
ms.reviewer: annagentry, julienp
ms.date: 2026-05-29T00:00:00.0000000Z
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-calling
ms.collection:
- M365-voice
- m365initiative-voice
- Tier1
search.appverid: MET150
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Microsofts policy for SMS messaging in Microsoft Teams
locale: en-us
document_id: 922b936d-5b0f-d5ef-e67a-fe872b8bc2d9
document_version_independent_id: 922b936d-5b0f-d5ef-e67a-fe872b8bc2d9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/sms-microsoft-teams-policy.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: sms-microsoft-teams-policy
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/sms-microsoft-teams-policy.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: d2c5f0eb-e546-32ac-ef1a-a44292eeaeac
---

# Microsofts SMS Messaging Policy - Microsoft Teams | Microsoft Learn

Teams Short Message Service (SMS) Messaging Policy

Teams SMS enables businesses to communicate with customers directly through SMS using a dedicated, verified 10-digit long code number (10DLC), ensuring messages are secure, compliant, and trusted. The integration uses the 10DLC framework to improve message deliverability and regulatory compliance, making it well-suited for conversational customer engagement, notifications, and other critical communications. Teams SMS isn't meant for broadcasting or marketing purposes.

## How we handle opt-out requests for SMS

If an individual requests to opt-out of future messages on Teams SMS, then all further traffic from that number is automatically stopped. You must ensure that you don't send more messages for that messaging campaign from the same number. If you separately obtain express consent to message for another purpose, then you must ask the customer to respond with a START message to resubscribe or send messages from a different number for that campaign. You must also ensure that you don't send additional messages to the same recipient from new or different numbers unless the sender of those messages has independent prior consent (express or implied) to contact the recipient. To learn more on Opt-out handling, see [Opt-out messaging](sms-setup-campaign#opt-out-message).

## Message content

### Adult content

Message content that includes elements of sex, hate, alcohol, firearms, tobacco, gambling, or sweepstakes and contests can trigger additional requirements. This content is expressly prohibited in some jurisdictions. If you send a message that includes this content, then it is your duty to abide by all applicable laws of the jurisdictions in which the communications are received. At the request of law enforcement or Microsoft Teams, you must be prepared to provide proof of consent with local laws that regulate adult content.

Even where such content isn't unlawful, you should include an age verification mechanism at opt-in to age-gate the intended message recipient from adult content. In the United States, additional legal requirements apply to marketing communications directed at children under the age of 13.

### Prohibited practices

You're prohibited from using Teams SMS to evade reasonable opt-out requests. Additionally, you may not evade any measures implemented by Teams SMS or a communications service provider to ensure your compliance with messaging requirements and industry standards.

Teams SMS also prohibits certain message content regardless of consent. Prohibited content includes the following:

- Content that promotes unlawful activities (for example, tax evasion or animal cruelty in the United States)
- Hate speech, defamatory speech, harassment, or other speech determined to be patently offensive
- Pornographic content
- Obscene or vulgar content
- Intimidation and threats
- Content that intends to defraud, deceive, cause harm, or wrongfully obtain anything of value
- Content that incites harm, discrimination, or violence
- Content that spreads malware
- Content that intends to evade age-gating requirements

We reserve the right to modify the list of prohibited message content at any time.

## Spoofing

Spoofing is the act of causing a misleading or inaccurate originating number or email address to display on a message recipient’s device. We strongly discourage you and any service provider that you use from sending spoofed messages. Spoofing shields the identity of the message sender and prevents message recipients from easily opting out of unwanted communications. We also require that you abide by all applicable spoofing laws.

## Final thoughts

### Legal Responsibility

This Messaging Policy doesn't constitute legal advice, and we reserve the right to modify the policy at any time. Microsoft Teams isn't responsible for ensuring that the content, timing, or recipients of our customers’ messages meet all applicable legal requirements.

Our customers are responsible for all messaging requirements. For further guidance, the Cellular Telecommunications Industry Association (CTIA) Messaging Principles and Best Practices provides a helpful overview of the relevant industry standards.

### Penalties

We encourage our customers to develop and implement policies and procedures designed to ensure compliance with all messaging requirements. Violations of messaging requirements may lead to substantial fines that can balloon quickly. It's in your best interest to learn and abide by all applicable messaging requirements and develop effective mitigation safeguards to contain and eliminate violations before they spread. If you do breach our Messaging Policy or other legal requirements, then we'll work with you to ensure future compliance. However, we reserve the right to remove SMS capabilities from any Teams customer who demonstrates a pattern of noncompliance with our Messaging Policy or legal requirements.