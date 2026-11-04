---
layout: Conceptual
title: Implement Quality of Service (QoS) in Microsoft Teams desktop clients on Windows - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/qos-in-teams-clients
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: odocspr
author: officedocspr5
manager: pamgreen
ms.topic: how-to
ms.service: msteams
ms.subservice: meetings
ms.reviewer: siunies
ms.date: 2024-11-12T00:00:00.0000000Z
audience: admin
description: Learn how to use Quality of Service (QoS) to optimize network traffic for the Microsoft Teams desktop client.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
locale: en-us
document_id: 6dd90fec-827b-5b36-8576-5ae38b33e455
document_version_independent_id: 85815d3e-7796-b92d-fc3e-2d5c14743010
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/QoS-in-Teams-clients.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: qos-in-teams-clients
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/QoS-in-Teams-clients.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 733ff909-a782-310b-6ff8-5053e5408653
---

# Implement Quality of Service (QoS) in Microsoft Teams desktop clients on Windows - Microsoft Teams | Microsoft Learn

There are multiple methods you can use to set the Differentiated Services Code Point (DSCP) markings for Teams desktop clients running on Windows. This article assumes you're using the default source port ranges as defined in [Implement QoS in Teams](qos-in-teams#step-3-choose-initial-port-ranges-for-each-media-type). If you customized the source port ranges for your environment, you need to adjust the following guidance to reflect the source ports being used.

## Configuring DSCP markings using Intune

Microsoft Intune (and other Mobile Device Management (MDM) providers) use the eXtensible Markup Language (XML)-based Open Mobile Alliance-Device Management (OMA-DM) protocol for policy settings management. Windows implements OMA-DM XML via Configuration Service Providers (CSPs) - and for Quality of Service (QoS), the [NetworkQoSPolicy](/en-us/windows/client-management/mdm/networkqospolicy-csp) CSP is used.

To create the device configuration policy for QoS for Teams clients on Windows:

1. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Select **Devices** &gt; **Configuration** &gt; **Create**.
3. Enter the following properties:

    - **Platform**: Select **Windows 10 and later**.
    - **Profile type**: Select **Templates** and then select **Custom**.
4. Select **Create**.
5. In **Basics**, enter the following properties:

    - **Name**: Enter a descriptive name for the profile. Name your profiles so you can easily identify them later. For example, **Windows: Teams QoS DSCP Markings**
    - **Description**: Enter a description for the profile. This setting is optional, but recommended.
6. Select **Next**.
7. In **Configuration settings**, select **Add**. Use the following tables to fill in the required OMA-URI settings (repeat for each row in the table).

    *Table 1. Intune OMA-URI Settings for Teams*

    | **Name** | **Description** | **OMA-URI** | **Data Type** | **Value** |
    | --- | --- | --- | --- | --- |
    | Teams Audio: Application | Teams executable name. | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/AppPathNameMatchCondition | String | ms-teams.exe |
    | Teams Audio: Ports | Audio source ports used by the Teams client. | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/SourcePortMatchCondition | String | 50000-50019 |
    | Teams Audio: DSCP Marking | Marking applied for audio (EF46) | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | Integer | 46 |
    | Teams Video: Application | Teams executable name. | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/AppPathNameMatchCondition | String | ms-teams.exe |
    | Teams Video: Ports | Video source ports used by the Teams client. | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/SourcePortMatchCondition | String | 50020-50039 |
    | Teams Video: DSCP Marking | Marking applied for video (AF41) | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | Integer | 34 |
    | Teams Screenshare: Application | Teams executable name. | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsScreenshare/AppPathNameMatchCondition | String | ms-teams.exe |
    | Teams Screenshare: Ports | Screen sharing ports used by the Teams client. | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsScreenshare/SourcePortMatchCondition | String | 50040-50059 |
    | Teams Screenshare: DSCP Marking | Marking applied for screen sharing (AF21) | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsScreenshare/DSCPAction | Integer | 18 |
    | Teams Calling-Meeting Signaling: Application | Teams executable name. | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsCMSignaling/AppPathNameMatchCondition | String | ms-teams.exe |
    | Teams Calling-Meeting Signaling: Ports | Calling and Meeting Signaling source ports used by the Teams client. | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsCMSignaling/SourcePortMatchCondition | String | 50070-50089 |
    | Teams Calling-Meeting Signaling: DSCP Marking | Marking applied for calling and meeting signaling (CS5) | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsCMSignaling/DSCPAction | Integer | 40 |
8. Select **Next**.
9. In **Assignments**, select the group or groups that you want to target with this policy. The group membership must include Windows devices (and not user accounts) as this policy is a device policy.
10. Select **Next**.
11. In **Applicability Rules**, define and desired rules (optional).
12. Select **Next**.
13. In **Review + create**, review the settings for accuracy, and when finished select **Create**.

## Configuring DSCP markings using PowerShell commands

Endpoint DSCP markings can be set in PowerShell using the [New-NetQosPolicy](/en-us/powershell/module/netqos/new-netqospolicy) command. In the following examples, there are two commands each for audio, video, and application sharing. The following commands show creating policies for the Teams client (ms-teams.exe).

**Set QoS for audio**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "ms-teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**Set QoS for video**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "ms-teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**Set QoS for sharing**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "ms-teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

**Set QoS for calling and meeting signaling**

```powershell
new-NetQosPolicy -Name "Teams Calling-Meeting Signaling" -AppPathNameMatchCondition "ms-teams.exe" -IPProtocolMatchCondition UDP -IPSrcPortStartMatchCondition 50070 -IPSrcPortEndMatchCondition 50089 -DSCPAction 40 -NetworkProfile All
```

## Configuring DSCP markings using Group Policy

You can create policy-based QoS settings within a Group Policy object (GPO). When creating the policies, you need to create a separate policy for audio, video, and application sharing.

To create a QoS audio policy for domain-joined Windows computers, first log on to a computer on which Group Policy Management is installed. Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:

1. In Group Policy Management, locate the container where the new policy should be created. For example, if all your client computers are located in an OU named **Clients**, create the new policy in the Clients OU.
2. Right-click the appropriate container, and then select **Create a GPO in this domain, and Link it here**.
3. In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then select **OK**.
4. Right-click the newly created policy, and then select **Edit**.
5. In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then select **Create new policy**.
6. In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box. Select **Specify DSCP Value**, and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then select **Next**.
7. On the next page, select **Only applications with this executable name** and enter the following name: **ms-teams.exe**.
8. Click **Next**. This setting instructs the policy to prioritize only matching traffic from the Teams client.
9. On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then select **Next**. These two settings ensure that packets are managed regardless of which computer (IP address) sent the packets and which computer (IP address) receives the packets.
10. On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list. TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.
11. Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**. Select **Finish**.
12. Repeat steps 5-10 to create policies for Video, Application/Desktop Sharing and Calling and Meeting Signaling, substituting the appropriate values in steps 6 and 10.

The new policies you created don't take effect until Group Policy is refreshed on your client computers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:

1. On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).
2. At the command prompt, enter

    ```console
    gpupdate /force
    ```

## Verify DSCP markings in the Group Policy object

To verify the values from the Group Policy object are set, perform the following steps:

1. Open a Command Prompt as administrator (*Run as administrator*).
2. At the command prompt, enter

    ```console
    gpresult /R > gp.txt
    ```

    This command generates a report of applied GPOs and send it to a text file named *gp.txt*.

    For a more readable HTML report named *gp.html*, enter the following command:

    ```console
    gpresult /H gp.html
    ```
3. In the generated file, look for the heading **Applied Group Policy Objects**, and verify that the names of the Group Policy objects created earlier are in the list of applied policies.
4. Open the Registry Editor, and go to

    HKEY\_LOCAL\_MACHINE\Software\Policies\Microsoft\Windows\QoS

    Verify the values for the registry entries listed in Table 2.

    *Table 2. Values for Windows registry entries for QoS*

    | Name | Type | Data |
    | --- | --- | --- |
    | Application Name | REG\_SZ | ms-teams.exe |
    | DSCP Value | REG\_SZ | 46 |
    | Local IP | REG\_SZ | \* |
    | Local IP Prefix Length | REG\_SZ | \* |
    | Local Port | REG\_SZ | 50000-50019 |
    | Protocol | REG\_SZ | \* |
    | Remote IP | REG\_SZ | \* |
    | Remote IP Prefix | REG\_SZ | \* |
    | Remote Port | REG\_SZ | \* |
    | Throttle Rate | REG\_SZ | -1 |
5. Verify the value for the Application Name entry is correct for the client you're using, and that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.