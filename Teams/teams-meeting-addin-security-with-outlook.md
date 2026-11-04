---
layout: Conceptual
title: Teams meeting add-in security in Outlook - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/teams-meeting-addin-security-with-outlook
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: DivySri-RK
ms.author: divyasrirk
ms.date: 2025-03-12T00:00:00.0000000Z
manager: prgholve
ms.topic: how-to
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.reviewer: 
description: Protect your Teams meeting add-in in the Outlook desktop client on Windows. Use Outlook's Trust-Center to load signed DLLs from only trusted publishers, group policies to trust a publisher, or AppLocker to prevent untrusted DLLs from being loaded.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- teams-security
- trust-pod
ms.custom:
- Security
locale: en-us
document_id: 4eb41223-50b9-b2a7-baa3-ae5b84891564
document_version_independent_id: 4eb41223-50b9-b2a7-baa3-ae5b84891564
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/teams-meeting-addin-security-with-outlook.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: teams-meeting-addin-security-with-outlook
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/teams-meeting-addin-security-with-outlook.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/3e34b70d-bca0-4369-a01b-71d1edfd427b
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/8ca32b3f-fa14-46df-b09a-9c4a591d6396
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: 877ffc3c-6693-90a6-5fe2-773a4528d24d
---

# Teams meeting add-in security in Outlook - Microsoft Teams | Microsoft Learn

The Teams meeting add-in (or TMA) is used to schedule meetings in Teams from the Outlook desktop client on Windows.

TMA coordinates between the Outlook and Teams services, so it's important to keep TMA secure. Taking security measures helps lower the risk of cybersecurity attack.

Here are the ways to secure your Teams meeting add-in covered in this article:

1. (Recommended) Use Microsoft Outlook Trust Center to prevent Outlook from loading TMA when the TMA DLLs aren’t signed with a certificate from a trusted publisher.
    1. Use group policies for the domain and update the *Root certificate* and *trusted publisher*, especially since it prevents users from being prompted to trust the publisher.
2. AppLocker can also be used to stop DLLs from untrusted publishers from being loaded.

## Microsoft Outlook Trust Center group policies

You can use **Trust Center group policies** for add-in management:

- To make sure only add-ins trusted by the organization are loaded
- To stop add-ins from unspecified locations from loading

This practice helps protect against malware compromising the COM registration to load from another location with planted DLLs.

Here are the steps:

1. **Protect Outlook from add-ins that aren't secure**
    1. Go to the Outlook Trust Center, https://www.microsoft.com/en-us/trust-center.
    2. When you arrive, select **File &gt; Options &gt; Trust Center**.
    3. Select **Microsoft Outlook Trust Center**.
    4. Under Microsoft Outlook Trust Center in the left menu, select **Trust Center Settings**.
    5. Under **Macro Settings**, select **Notifications for digitally signed macros, all other macros disabled**.
    6. Admins must select **Apply macro security settings to installed add-ins** in this case.
    7. Select the **OK** button to make these changes and exit the trust center, and select **OK** again, to close options.

The choices persist from there.

Now, outside of the Outlook Trust Center:

1. Restart Outlook on your client.
2. When Outlook reopens, the application asks permission to load each add-in, automatically disabling any add-in that *isn't* signed.

    1. The image below is what the user experience of TMA looks like: ![Outlook security notice and how Trust all docs from this publisher, and Enable applications add-in works.](media/tma/outlook-security-notice-and-how-trust-all-docs-from-this-publisher-and-enable-application-add-in-will-work.png)
    2. End-users see a Microsoft Outlook Security Notice that may read *Microsoft Office has identified a potential security concern*listing Microsoft.Teams.AddinLoader.dll. The options are:
        1. **Trust all documents from this Publisher.**
            1. Selecting this option trusts the certificate’s publisher and the user won’t be prompted again until the certificate changes.
        2. **2. Enable application add-in.**
            1. This option only enables on a case-by-case basis, so this add-in enables for this single time, and the user will be prompted again.
        3. **3. Disable application add-in.**
            1. Disables the add-in.
    3. Follow the steps to **[set up Group Policy to automatically trust a specific root certificate Authority](/en-us/windows-server/identity/ad-fs/deployment/distribute-certificates-to-client-computers-by-using-group-policy)**.
        1. Open the Group Policy Management Console on your domain controller (DC).
        2. Create a new Group Policy Object (GPO) or edit an existing GPO that you want to use to configure the settings.
        3. Next go to Computer Configuration &gt; Policies &gt; Windows Settings &gt; Security Settings &gt; Public Key Policies.
        4. Right-click on Trusted Root Certification Authorities and select Import.
        5. Browse to the root certificate Microsoft Root Certificate Authority 2010 file for the certificate publisher you want to trust and import it.
        6. Link the GPO to the appropriate organizational unit to apply the settings to the computers that you want to use the policy. For more information on this process, see: [Deploy the Applocker Policy into production](/en-us/windows/security/threat-protection/windows-defender-application-control/applocker/deploy-the-applocker-policy-into-production)
    4. Next, follow the steps to set up Group Policy to automatically trust the publisher.
        1. Open the Group Policy Management Console on your domain controller.
        2. Create a new GPO or edit an existing GPO that you want to use to configure the settings.
        3. Navigate to Computer Configuration &gt; Policies &gt; Windows Settings &gt; Security Settings &gt; Public Key Policies.
        4. Right-click on Trusted Publishers and select Import.
        5. Browse to the leaf certificate Microsoft Corporation file for the certificate publisher you want to trust and import it.
        6. Link the GPO to the appropriate organizational unit to apply the settings to the computers you choose.
3. **Add-in Management through Group Policies**

    1. [Download Administrative Template files (ADMX/ADML)](https://www.microsoft.com/en-us/download/details.aspx?id=49030) for Microsoft 365 Apps for enterprise/Office LTSC 2021/Office 2019/Office 2016 and the Office Customization Tool for Office 2016.
    2. Add the ADMX/ADML template files to the Group Policy Management:
        1. Under **User Configuration &gt; Administrative Templates &gt; Microsoft Outlook (version number) &gt; Security &gt; Trust Center**.
            1. *Apply Macro security settings to Macros, add-ins and additional actions*: This policy setting controls whether Outlook also applies the Macro security settings to installed COM add-ins and additional actions.
                1. **Set to:** Enabled
            2. *Security setting for macros*: This policy setting controls the security level for macros in Outlook.
                1. **Set to:**Warning for signed, disable unsigned.
                    1. This option corresponds to the *Notifications for digitally signed macros, all other macros disabled* option in the Trust Center. If an add-in is digitally signed by a trusted publisher, the add-in can run signed by a trusted publisher.
        2. Additional Group Policies around Add-ins.
            1. Under **User Configuration &gt; Administrative Templates &gt; Microsoft Outlook 2016 &gt; Security**
                1. *Configure add-in trust level*: All installed trusted COM add-ins can be trusted. Exchange Settings for the add-ins still override if present and this option is selected.
            2. Under **User Configuration &gt; Administrative Templates &gt; Microsoft Outlook 2016 &gt; Miscellaneous**
                1. *Block all unmanaged add-ins*: This policy setting Blocks all add-ins that aren't managed by the "List of managed add-ins" policy setting.
                2. *List of managed add-ins*: This policy setting allows you to specify which add-ins are always enabled, always disabled (blocked), or configurable by the user. To block add-ins that aren't managed by this policy setting, you must also configure the "Block all unmanaged add-ins" policy setting.
            3. Under **User Configuration &gt; Administrative Templates &gt; Microsoft Outlook 2016 &gt; Security &gt; Security Form Settings &gt; Programmatic Security &gt; Trusted Add-ins**
                1. *Configure Trusted Add-ins*: This policy setting is used to specify a list of Trusted Add-ins that can be run without being restricted by the security measures in Outlook.

## AppLocker

The AppLocker application control policies help you control which apps and files users can run. These file types include executable files, scripts, Windows Installer files, dynamic-link libraries (DLLs), packaged apps, and packaged app installers.

Let's focus on using AppLocker to *stop* DLLs that aren't signed by a trusted publisher from loading.

#### Use AppLocker to stop unsigned DLLs from loading.

To use Applocker to stop your unsigned DLLs from loading, you have to create a new DLL rule in your Local or Group Policy.

Note

The pre-requisites for this section are Windows 10 Enterprise and, Education or Windows Server 2012 or later.

To set up AppLocker on *Windows 10 or Windows 11* for a specific DLL, follow these steps:

1. Open policy editor.
    1. Local Machine
        1. Open the Local Security Policy editor. Type secpol.msc into the Run dialog box or the Start menu search bar, and then press Enter.
    2. Group Policy
        1. Edit an AppLocker policy Through Group Policies | Microsoft Learn
2. In the Local Security Policy editor, navigate go to Application Control Policies &gt; AppLocker &gt; DLL Rules.
    1. If you're using a supported edition of Windows and still don't see DLL rules, it's possible that AppLocker isn't enabled or configured on your system. In this case, you can follow these steps to enable AppLocker:
        1. Open the Local Security Policy editor. Type secpol.msc into the Run dialog box or the Start menu search bar, then press Enter.
        2. In the Local Security Policy editor, navigate to Application Control Policies &gt; AppLocker.
        3. Right-click on AppLocker and select Properties.
        4. Under AppLocker Properties, in the Enforcement tab:
            1. Select Configured next to Configure rule enforcement.
            2. Configure extra policies such as rule collections as audit-only mode.
            3. Once this is verified, it can be updated to Enforce
            4. Select OK to save the changes.
            5. Be sure the Application Identity service is [running](/en-us/windows/security/threat-protection/windows-defender-application-control/applocker/configure-the-application-identity-service).
3. Create a new DLL Rule
    1. From the Local Security Policy editor
        1. Right-click on DLL Rules and select Create New Rule.
        2. In the Create DLL Rule wizard, select Use an Existing File and browse to the DLL file that you want to create a rule for.
        3. Select the type of rule that you want to create (such as to allow or deny) and configure any other rule conditions that are needed.
        4. Complete the wizard and save the new rule.
    2. Or from PowerShell:
        1. The PowerShell cmdlets that are needed to create a new DLL Rule can be piped together.
4. Add-in Management through AppLocker Group Policies
    1. **Get-ChildItem** - Gets the object for the file
    2. **Get-AppLockerFileInformation** - Gets the file information necessary to create AppLocker rules from a list of files or an event log
    3. **New-AppLockerPolicy**- Creates a new AppLocker policy from a list of file information and other rule creation options.
        1. RuleType needs to be published and this enforces code signing.
        2. User can be an individual user or group, all examples use Everyone.
        3. AllowWindows indicates that the AppLocker policy allows all local Windows components.
    4. To create the DLL rule per file
        1. TMA file location depends on the installation type
            1. Per user installation
                1. Install location: %localappdata%\Microsoft\TeamsMeetingAddin
            2. Per machine installation
                1. Install location: C:\Program Files(x86)\TeamsMeetingAddin
        2. `Get-ChildItem <TMAFileLocation>\Microsoft.Teams.AddinLoader.dll | Get-AppLockerFileInformation | New-AppLockerPolicy  -RuleType Publisher, Hash -User Everyone -RuleNamePrefix TeamsMeetingAddin -AllowWindows -Xml | Out-File .\TMA.xml`
        3. Set the policy:
            1. Local Machines i.`Set-AppLockerPolicy -XmlPolicy .\TMA.xml -Merge`
            2. Group Policy i. `Set-AppLockerPolicy -XMLPolicy .\TMA.xm -LDAP "<LDAP Info for Group Policy>"`
        4. Steps 1 and 2 need to be completed for each DLL under x64 and x86 directories for TMA.
    5. Create **all DLL rules at once**:
        1. Get-AppLockerFileInformation -Directory .\Microsoft\TeamsMeetingAddin\1.0.23089.2 -Recurse | New-AppLockerPolicy -Verbose -RuleType Publisher, Hash -User Everyone -RuleNamePrefix TeamsMeetingAddin -AllowWindows -Xml | Out-File .\TMA.xml`
        2. `Set-AppLockerPolicy -XmlPolicy .\TMA.xml  -Merge` 3. LDAP info is needed to perform Group Policy updates.

Important things to know:

1. It’s assumed that if AppLocker is turned on in an environment, then the IT department is familiar with AppLocker. They're aware it’s designed to use an Allow model and anything not Allowed will be blocked.
2. Hash rules are provided for fallback when Publisher rule fails. Hash rules need to be updated every time TMA updates.
3. The [PowerShell](https://microsoft.sharepoint.com/sites/knowledgecenter/SitePages/PowerShell.aspx) command for adding AppLocker policies will be set up to match only the exact version of the DLL being added &gt; go into the Allow Properties for the Publisher Rule and change the File Versions options for scope to And Above the listed version.
4. To make AppLocker accept a wider range of DLL versions for Publisher Rules, go to the Allow Properties for the Publisher Rule and change the drop-down for File version to *And above* (from *Exactly*). ![Make AppLocker accept a wider range of DLL versions for publisher rules.](media/tma/make-applocker-accept-a-wider-range-of-dll-versions-for-publisher-rules.png)
5. Once enabled if the AppLocker policy blocks the add-in, it will not show, and inspecting COM add-ins will show: ![Once enabled, if the AppLocker policy blocks the add-in it won't show, and inspecting COM add-ins will show the add-in as unavailable.](media/tma/once-enabled-if-the-applocker-policy-blocks-the-add-in-it-will-not-show-and-inspecting-com-add-ins-will-show-the-add-in-as-unavailable.png)

## For more information

[Enable or disable macros in Microsoft 365 files](https://support.microsoft.com/office/enable-or-disable-macros-in-microsoft-365-files-12b036fd-d140-4e74-b45e-16fed1a7e5c6#:%7E:text=Change%20macro%20settings%20in%20the%20Trust%20Center%201,the%20selections%20that%20you%20want%2C%20then%20click%20OK.) - Microsoft Support [AppLocker (Windows)](/en-us/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)| Microsoft Learn