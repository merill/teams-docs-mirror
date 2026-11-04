---
layout: Conceptual
title: Set up dynamic filters for SIP Gateway - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/devices/sip-gateway-dynamic-filters
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: chasing
ms.date: 2024-08-20T00:00:00.0000000Z
ms.topic: install-set-up-deploy
audience: admin
ms.service: msteams
ms.subservice: itpro-devices
ms.collection:
- teams-rooms-devices
- Teams_ITAdmin_Devices
- Tier1
f1.keywords:
- NOCSH
search.appverid: MET150
ms.localizationpriority: medium
description: Learn how to create and set up dynamic filters and exclusions for SIP gateway to control access to your organization's resources.
locale: en-us
document_id: 7aed77ca-bff7-6dca-fc04-429c94b796ed
document_version_independent_id: 7aed77ca-bff7-6dca-fc04-429c94b796ed
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/devices/sip-gateway-dynamic-filters.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: devices/sip-gateway-dynamic-filters
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/devices/sip-gateway-dynamic-filters.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/68cb9039-df60-49b0-8ef8-89ad96497f63
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/5fc61396-d075-4560-aece-fdbda73d243f
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/725b6df3-93e8-472d-834e-e7e0d2953d35
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/ad9437c1-8cda-4537-ad69-b4b263652e13
platformId: b31d942b-f3b1-1094-53a2-036a503d3fdd
---

# Set up dynamic filters for SIP Gateway - Microsoft Teams | Microsoft Learn

This article explains how to exclude SIP Gateway from Conditional Access Policy, which is a feature that allows you to control access to your organization's resources based on certain conditions. You can exclude SIP Gateway from conditional access if you use it for voice and don't want to enforce extra security requirements on those users. In this article, you'll find the steps to create an exclusion group and assign it to the policy along with the prerequisites.

The SIP Gateway resources mentioned in this article can’t be directly excluded from Conditional Access policies. Hence, we describe the dynamic app filter approach to exclude SIP Gateway apps. Also, simply excluding SIP Gateway apps won't address the gap as SIP Gateway apps don't own any scopes on their own and depend on Teams app for the required scopes.

## Prerequisites

To add or deactivate custom security attributes definitions, you must have:

- [Attribute Assignment Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference#attribute-assignment-administrator)
- [Attribute Definition Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference#attribute-definition-reader)
- Microsoft Graph module, when using [Microsoft Graph PowerShell](/en-us/powershell/microsoftgraph/installation)

Important

By default, Global Administrator and other administrator roles do not have permissions to read, define, or assign custom security attributes.

## Step 1: Add an attribute set

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/) as a [Attribute Definition Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference).
2. Browse to **Protection** &gt; **Custom security attributes**.
3. Select **Add attribute set** to add a new attribute set.

    Note

    If **Add attribute set** is disabled, ensure that you're assigned the Attribute Definition Administrator role. For more information, see [Troubleshoot custom security attributes](/en-us/entra/fundamentals/custom-security-attributes-troubleshoot).
4. Enter a name, description, and maximum number of attributes.

    Tip

    An attribute set name can be 32 characters with no spaces or special characters. Once you've specified a name, you can't rename it. For more information, see [Limits and constraints](/en-us/entra/fundamentals/custom-security-attributes-overview).
5. When finished, select **Add**.
6. The new attribute set appears in the list of attribute sets.

## Step 2: Add a custom security attribute definition

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/) as a [Attribute Definition Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference).
2. Browse to **Protection** &gt; **Custom security attributes**.
3. On the **Custom security attributes** page, choose an existing attribute set or select **Add attribute set** to add a new attribute set. All custom security attribute definitions must be part of an attribute set.
4. Select to open the selected attribute set.
5. Select **Add attribute** to add a new custom security attribute to the attribute set.
6. In the **Attribute name** box, enter a custom security attribute name.

    Tip

    An attribute set name can be 32 characters with no spaces or special characters. Once you've specified a name, you can't rename it. For more information, see [Limits and constraints](/en-us/entra/fundamentals/custom-security-attributes-overview).

    [![Screenshot displaying the Exclude attribute set.](media/exclude-attribute-set.png)](media/exclude-attribute-set.png#lightbox)
7. In the **Description** box, enter an optional description.

    Tip

    A description can be 128 characters long. If necessary, you can later change the description.
8. From the **Data type** list, select the data type for the custom security attribute.

    - Data type: A description.
    - Boolean: A Boolean value that can be true or false.
    - Integer: A 32-bit integer.
    - String: A string that can be X characters long.
9. For **Allow multiple values to be assigned**, select **Yes** or **No**.

    - Select **Yes** to allow multiple values to be assigned to this custom security attribute.
    - Select **No** to only allow a single value to be assigned to this custom security attribute.
10. For **Only allow predefined values to be assigned**, select **Yes** or **No**.

    - Select **Yes**, if custom security attribute can be assigned values from a predefined values list.
    - Select **No** to allow this custom security attribute to be assigned user-defined values or potentially predefined values.
11. If **Only allow predefined values to be assigned** is selected Yes, then select **Add value** to add predefined values. An active value is available for assignment of objects. A value that isn't active is defined, but not yet available for assignment.
12. When finished, select **Save**.
13. The new custom security attribute appears in the list of custom security attributes.

## Step 3: Add SIP Gateway Service Principals to your tenant

**Using Azure Active Directory module:**

1. Open a new elevated PowerShell window.
2. Run `Install-Module AzureAD`.
3. Run `Import-Module AzureAD`.
4. Run `Connect-AzureRmAccount`.
5. Sign in with the admin account.
6. Run the following cmdlet:

    ```powershell
    Get-AzureADServicePrincipal -Filter "AppId eq '582b2e88-6cca-4418-83d2-2451801e1d26'"
    ```

    If you get no output, then run:

    ```powershell
    New-AzureADServicePrincipal -AppId "582b2e88-6cca-4418-83d2-2451801e1d26"
    ```
7. Run the following cmdlet:

    ```powershell
    Get-AzureADServicePrincipal -Filter "AppId eq '0ab9de21-b802-4d77-b279-1ad41ca233b4'"
    ```

    If you get no output, then run:

    ```powershell
    New-AzureADServicePrincipal -AppId "0ab9de21-b802-4d77-b279-1ad41ca233b4"
    ```

**Using MS Graph module:**

1. Run the following cmdlets:

    ```powershell
    ## SIP Gateway API:
    Get-MgServicePrincipal -Filter "AppId eq '0ab9de21-b802-4d77-b279-1ad41ca233b4'"
    New-MgServicePrincipal -AppId "0ab9de21-b802-4d77-b279-1ad41ca233b4"
    ```

    ```powershell
    ## SIP Gateway UserApp:
    Get-MgServicePrincipal -Filter "AppId eq '582b2e88-6cca-4418-83d2-2451801e1d26'"
    New-MgServicePrincipal -AppId "582b2e88-6cca-4418-83d2-2451801e1d26"
    ```
2. After running these cmdlets, you should get the following output to proceed:

    ![Screenshot of the output that is expected after running cmdlets.](media/powershell-output-expected.png)

**Bulk device sign-in**

If you are using bulk-sigin for your devices, you will also have to add this extra service principal Teams SIP Gateway:

```powershell
##Using AzureAd Module:
Get-AzureADServicePrincipal -Filter "AppId eq '61c8fd69-c13e-4ee6-aaa6-24ff71c09bca
```

If you get no output, then run:

```powershell
New-AzureADServicePrincipal -AppId "61c8fd69-c13e-4ee6-aaa6-24ff71c09bca"
```

```powershell
## Using MS Graph Module:
Get-AzureADServicePrincipal -Filter "AppId eq '61c8fd69-c13e-4ee6-aaa6-24ff71c09bca
New-MgServicePrincipal -AppId "61c8fd69-c13e-4ee6-aaa6-24ff71c09bca" 
```

## Step 4: Assign custom security attribute to SIP Gateway

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/) as at least a [Conditional Access Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference).
2. Browse to **Identity** &gt; **Applications** &gt; **Enterprise applications**.
3. Clear all filters.
4. Search for SIP Gateway API (0ab9de21-b802-4d77-b279-1ad41ca233b4) and select it.
5. Under **Manage** &gt; **Custom security attributes**, select **Add assignment**.
6. Under **Attribute set**, select the attribute set you created in step 1.
7. Under **Attribute name**, select the attribute name you created in step 2.
8. Under **Assigned values**, select **Add values**, select the value from the list (requireMFA in this example), then select **Done**.

    ![Screenshot displaying to select requireMFA.](media/require-mfa-selection.png)
9. Select **Save**.
10. Follow the same steps for SIP Gateway UserApp (582b2e88-6cca-4418-83d2-2451801e1d26).
11. Follow the same steps for Teams SIP Gateway (61c8fd69-c13e-4ee6-aaa6-24ff71c09bca) in case you’re using bulk signin for your devices.

## Step 5: Exclude this attribute from your Conditional Access Policy

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/) as at least a [Conditional Access Administrator](/en-us/entra/identity/role-based-access-control/permissions-reference).
2. Browse to **Protection** &gt; **Conditional Access**.
3. Select the policy you want to change.
4. Under **Target resources**, select the following options to autofill this field:

    - From **Select what this policy applies to** list, choose **Cloud apps**.
    - On the **Include** tab, select **All** apps option.
5. Change tab to **Exclude** and Select **Edit filter**.
6. On the **Edit filter** page, set **Configure** to **Yes**.
7. Select the attribute you created earlier (in this case 'exclAttrAllowMultiple').
8. Set **Operator** to **Contains**.
9. Set **Value** to the one assigned to SIP Gateway apps in step 4 (in this case requireMFA).

    [![Screenshot displaying the edit filter pane.](media/edit-filter.png)](media/edit-filter.png#lightbox)
10. Select **Done**.
11. Review and confirm your settings.

    ![Screenshot showing the user's image.](media/sip-gateway-dynamic-filters/image.png)
12. Select **Save** to enable your policy.