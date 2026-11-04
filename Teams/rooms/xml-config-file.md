---
layout: Conceptual
title: Remotely manage Microsoft Teams Rooms device settings - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/rooms/xml-config-file
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
author: MSTonySmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: henrikalim
ms.date: 2026-08-04T00:00:00.0000000Z
ms.topic: how-to
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection:
- M365-collaboration
- teams-rooms-devices
- Tier2
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.custom:
- seo-marvel-mar2020
description: Remote management of the default settings used by a Microsoft Teams Rooms device and creating a master settings file.
locale: en-us
document_id: 25a70665-5bf1-14f7-1df0-7596effcaf48
document_version_independent_id: 813cf005-2777-9419-d1ce-3f9401ac267c
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/rooms/xml-config-file.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: rooms/xml-config-file
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/rooms/xml-config-file.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
platformId: a7ef2a19-7de4-4888-b795-aae8dc45607d
---

# Remotely manage Microsoft Teams Rooms device settings - Microsoft Teams | Microsoft Learn

Important

We recommend using the individual and bulk settings configuration options within the Teams Rooms Pro Management Portal instead of the XML configuration. We no longer publish new XML settings but all settings are managable within the Portal. Learn more in [Manage settings for Teams devices](/en-us/microsoftteams/rooms/pro-portal-settings).

This article discusses remote management of the default settings used by a Microsoft Teams Rooms device. It discusses how to create a master settings file and links to discussions of how to place them as needed on Teams Rooms.

It's possible for you to change default settings of Teams Rooms by updating an XML file and sending copies to the remote Teams Rooms devices.

Note

Some features are available only on Teams Rooms devices that have been assigned a Microsoft Teams Rooms Pro license. To see which features require Microsoft Teams Rooms Pro, see [Microsoft Teams Rooms licenses](rooms-licensing).

## Manage console settings with an XML configuration file

At startup, if a Microsoft Teams Rooms console finds an XML file named SkypeSettings.xml located at `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`, it applies the configuration settings indicated by the XML file then deletes the XML file.

Depending on how many Microsoft Teams Rooms devices your enterprise has and how you choose to manage to configure them, there are several ways to place the XML configuration file. Once the file is pushed to the console, restart it to process the configuration changes. The XML configuration file is deleted after it's successfully processed.

You can use any method you like so long as you can use it to transfer files and trigger a restart on the console device. The file must be readable, writable, and delete-able by the device's local user account. Preferably it's owned by, and has full privileges granted to, device's local user. If the file permissions aren't set correctly, the software can fail to apply the settings, can fail to delete the file upon successful processing, and can even potentially crash.

## Create an XML configuration file

Any text editor can be used to create a settings file. The **XML Elements** table explains the elements shown in this sample SkypeSettings.xml (required file name) configuration file. XML elements are case-sensitive.

```XML
<SkypeSettings>
  <AutoScreenShare>1</AutoScreenShare>
  <HideMeetingName>0</HideMeetingName>
  <AutoExitMeetingEnabled>true</AutoExitMeetingEnabled>
  <AudioRenderDefaultDeviceVolume>50</AudioRenderDefaultDeviceVolume>
  <AudioRenderCommunicationDeviceVolume>50</AudioRenderCommunicationDeviceVolume>
  <UserAccount>
    <SkypeSignInAddress>username@microsoft.com</SkypeSignInAddress>
    <Password>Password!</Password>
  </UserAccount>
  <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled>
  <SfbMeetingEnabled>false</SfbMeetingEnabled>
  <IsTeamsDefaultClient>true</IsTeamsDefaultClient>
  <RequirePasscodeForAllTeamsMeetings>false</RequirePasscodeForAllTeamsMeetings>
  <RequirePasscodeForAllPrivateTeamsMeetings>false</RequirePasscodeForAllPrivateTeamsMeetings>
  <WebExMeetingsEnabled>true</WebExMeetingsEnabled>
  <ZoomMeetingsEnabled>true</ZoomMeetingsEnabled>
  <GoogleMeetMeetingsEnabled>true</GoogleMeetMeetingsEnabled>
  <UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>
  <CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>
  <CustomDisplayEmailForThirdPartyMeetings>guest@microsoft.com</CustomDisplayEmailForThirdPartyMeetings>
  <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
  <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
  <AllowRoomRemoteEnabled>true</AllowRoomRemoteEnabled>
  <RoomQRcodeEnabled>true</RoomQRcodeEnabled>
  <QRCodeAutoAcceptProximateMeetingInvitations>true</QRCodeAutoAcceptProximateMeetingInvitations>
  <DualScreenMode>false</DualScreenMode>
  <DuplicateIngestDefault>true</DuplicateIngestDefault>
  <DisableTeamsAudioSharing>false</DisableTeamsAudioSharing>
  <EnableRoomCapacityNotification>true</EnableRoomCapacityNotification>
  <FrontRowEnabled>true</FrontRowEnabled>
  <FrontRowVideoSize>medium</FrontRowVideoSize>
  <FrontRowPanelDefaults>3,2</FrontRowPanelDefaults>
  <SingleFoRDefaultContentLayout>1</SingleFoRDefaultContentLayout>
  <DefaultFoRExperience>0</DefaultFoRExperience>
  <ShowMeetingChat>true</ShowMeetingChat>
  <OpenMeetingChatByDefault>true</OpenMeetingChatByDefault>
  <PrioritizeVideoParticipantsGallery>true</PrioritizeVideoParticipantsGallery>
  <HideMeForAllLayouts>false</HideMeForAllLayouts>
  <EnablePublicPreview>false</EnablePublicPreview>
  <NoiseSuppressionDefault>1</NoiseSuppressionDefault>
  <EnableCloudIntelliFrame>true</EnableCloudIntelliFrame>
  <EnableCIFOnByDefault>true</EnableCIFOnByDefault>
  <EnableCIFOnSupportedCamerasOnly>true</EnableCIFOnSupportedCamerasOnly>
  <OemCameraControlsEnabled>true</OemCameraControlsEnabled>
  <LocalPtzControlsEnabled>true</LocalPtzControlsEnabled>
  <RoomLanguageSwitchEnabled>true</RoomLanguageSwitchEnabled>
  <SendLogs>
    <EmailAddressForLogsAndFeedback>username@microsoft.com</EmailAddressForLogsAndFeedback>
    <SendLogsAndFeedback>true</SendLogsAndFeedback>
  </SendLogs>
 <SendFeedbackToPMP>true</SendFeedbackToPMP>
 <Devices>
    <MicrophoneForCommunication>Device1</MicrophoneForCommunication>
    <SpeakerForCommunication>DeviceX</SpeakerForCommunication>
    <DefaultSpeaker>DeviceX</DefaultSpeaker>
    <ContentCameraId>Camera1</ContentCameraId>
    <ContentCameraEnhancement>true</ContentCameraEnhancement>
    <ContentCameraInverted>false</ContentCameraInverted>
  </Devices>
  <Theming>
       <ThemeName>Custom</ThemeName>
       <CustomBackgroundMainFoRDisplay>file name</CustomBackgroundMainFoRDisplay>
       <CustomBackgroundExtendedFoRDisplay>file name</CustomBackgroundExtendedFoRDisplay>
       <CustomBackgroundConsole>file name</CustomBackgroundConsole>
       <CustomThemeImageUrl>file name</CustomThemeImageUrl>
  </Theming>
  <RemoveFoRCalendar>false</RemoveFoRCalendar>
  <CoordinatedMeetings enabled="true">
    <TrustedAccounts>username1@microsoft.com,username2@contoso.com</TrustedAccounts>
    <Settings>
      <Audio default="true" enabled="true"/>
      <Video default="true" enabled="true"/>
      <Whiteboard default="true" enabled="true"/>
    </Settings>
  </CoordinatedMeetings>
  <EnableResolutionAndScalingSetting>true</EnableResolutionAndScalingSetting> 
  <MainFoRDisplay> 
      <MainFoRDisplayResolution>1920,1080</MainFoRDisplayResolution> 
      <MainFoRDisplayScaling>100</MainFoRDisplayScaling> 
  </MainFoRDisplay> 
  <ExtendedFoRDisplay> 
      <ExtendedFoRDisplayResolution>1920,1080</ExtendedFoRDisplayResolution> 
      <ExtendedFoRDisplayScaling>100</ExtendedFoRDisplayScaling> 
  </ExtendedFoRDisplay>  
  <EnableDeviceEndToEndEncryption>false</EnableDeviceEndToEndEncryption>
  <SplitVideoLayoutsDisabled>false</SplitVideoLayoutsDisabled>
</SkypeSettings>
```

If a variable value is of the wrong type, elements are out of order, elements are unclosed, or another error is found, the XML file is *badly formed*. While processing a badly formed XML file, settings found up to the point where the error occurs are applied, then the rest of the file is ignored. Any unknown elements in the XML are ignored. If a parameter is omitted, it remains unchanged on the device. If a parameter value is invalid, its prior value remains unchanged.

**XML elements**

| Element | Type | Level | Usage |
| --- | --- | --- | --- |
| `<SkypeSettings>` | Container for all elements. |  | Required. |
| `<AutoScreenShare>` | Boolean ❷ | First ❶ | If true, a connected HDMI ingest will be automatically shared on the Front of Room display and when in a Teams Meeting it will be automatically shared to remote participants. If false, a connected HDMI ingest will be automatically shared on the Front of Room display in and out of a Teams meeting but it won't be shared to remote participants in the meeting automatically, users will need to select the share icon to share content to remote participants. |
| `<HideMeetingName>` | Boolean ❷ | First ❶ | If true, meeting names are hidden. |
| `<UserAccount>` | Container | First ❶ | Container for credentials parameters. The sign-in address, Exchange address, or email address are usually the same, such as RainierConf@contoso.com. |
| `<SkypeSignInAddress>` | String ❷ |  | The sign-in name for the console's SfB or Teams device account. |
| `<Password>` | String ❸ |  | The password parameter is the same password used for the Skype for Business device account sign-in. |
| `<TeamsMeetingsEnabled>` | Boolean ❷ | First ❶ | Disabled by default.  The XML file is considered badly formed if both `<SkypeMeetingsEnabled>` and`<TeamsMeetingsEnabled>` are disabled, but it's acceptable to have both settings enabled at the same time. |
| `<SfbMeetingEnabled>` | Boolean ❷ | First ❶ | Disabled by default. |
| `<IsTeamsDefaultClient>` | Boolean ❷ | First ❶ | Enabled by default. |
| `<RequirePasscodeForAllTeamsMeetings>` | Boolean ❷ | First ❶ | Disabled by default.  If true, users are required to enter the correct meeting id and passcode to join all Teams meetings scheduled in the room with a Microsoft Teams Room Pro license. |
| `<RequirePasscodeForAllPrivateTeamsMeetings>` | Boolean ❷ | First ❶ | Disabled by default.  If true, users are required to enter the correct meeting id and passcode to join all **private** Teams meetings scheduled in the room with a Microsoft Teams Room Pro license. |
| `<WebExMeetingsEnabled>` | Boolean ❷ | First ❶ | Disabled by default.  If true, enables direct guest join experience for Cisco Webex meetings. |
| `<ZoomMeetingsEnabled>` | Boolean ❷ | First ❶ | Disabled by default.  If true, enables direct guest join experience for Zoom meetings. |
| `<GoogleMeetMeetingsEnabled>` | Boolean ❷ | First ❶ | Disabled by default.  If true, enables direct guest join experience for Google Meet meetings. |
| `<UseCustomInfoForThirdPartyMeetings>` | Boolean ❷ | First ❶ | Disabled by default and uses conference room account info to join third party meetings.  If this value is set to true, you must specify both `<CustomDisplayNameForThirdPartyMeetings>`, `<CustomDisplayEmailForThirdPartyMeetings>` must be specified. |
| `<CustomDisplayNameForThirdPartyMeetings>` | String ❸ | First ❶ | Specify guest name used to join third party meetings. Third party service will display this data in their experience and may store in their service. |
| `<CustomDisplayEmailForThirdPartyMeetings>` | String ❸ | First ❶ | Specify guest email used to join third party meetings. Third party service will display this data in their experience and may store in their service. |
| `<BluetoothAdvertisementEnabled>` | Boolean ❷ | First ❶ | Enabled by default. |
| `<AutoAcceptProximateMeetingInvitations>` | Boolean ❷ | First ❶ | If true, proximity based meeting invitations via Bluetooth are automatically accepted. Enabled by default. |
| `<AllowRoomRemoteEnabled>` | Boolean ❷ | First ❶ | If true, room remote connections are allowed. Enabled by default. |
| `<RoomQRcodeEnabled>` | Boolean ❷ | First ❶ | If true, a QR code is shown on the home screen. Users can scan the QR code to quickly join meetings with the room system. Enabled by default. For more information, see [Join meetings with QR codes](/en-us/microsoftteams/rooms/teams-rooms-qr-codes). |
| `<QRCodeAutoAcceptProximateMeetingInvitations>` | Boolean ❷ | First ❶ | If true, proximity based meeting invitations via QR code are automatically accepted. Enabled by default. For more information, see [Join meetings with QR codes](/en-us/microsoftteams/rooms/teams-rooms-qr-codes). |
| `<AutoExitMeetingEnabled>` | Boolean ❷ | First ❶ | If true, device will automatically leave the meeting if it's the last participant remaining in the meeting before or after the meeting end time. Disabled by default. |
| `<DualScreenMode>` | Boolean ❷ | First ❶ | If true, dual screen mode is enabled. Otherwise the device uses single screen mode. |
| `<DuplicateIngestDefault>` | Boolean ❷ | First ❶ | If true, content is shown on both screens in dual screen mode, when out of meeting. |
| `<DisableTeamsAudioSharing>` | Boolean ❷ | First ❶ | Set to true to disable HDMI audio sharing to meeting participants in Teams meeting. The default is false. |
| `<EnableCloudIntelliFrame>` | Boolean ❷ | First ❶ | Enabled by default. If true, Cloud IntelliFrame is enabled. |
| `<EnableCIFOnByDefault>` | Boolean ❷ | First ❶ | Enabled by default. If true, Cloud IntelliFrame will be enabled by default for all remote participants viewing the room. |
| `<EnableCIFOnSupportedCamerasOnly>` | Boolean ❷ | First ❶ | Enabled by default. If true, Cloud IntelliFrame will only work on [selected cameras](/en-us/microsoftteams/devices/cloud-intelliframe#cameras-enabled-by-default). |
| `<OemCameraControlsEnabled>` | Boolean ❷ | First ❶ | Enabled by default. If true, OEM camera controls appear within the camera settings during meetings. |
| `<LocalPtzControlsEnabled>` | Boolean ❷ | First ❶ | Enabled by default. If true, in-room participants can pan, tilt, and zoom a supported room camera from the console during meetings. For more information, see [Camera controls in Teams Rooms](camera-controls). |
| `<EnableRoomPeopleCount>` | Boolean ❷ | First ❶ | Enabled by default. If true, people count will be enabled for Teams Rooms. |
| `<EnableRoomCapacityNotification>` | Boolean ❷ | First ❶ | Enabled by default to provide warnings to in room participants that the room has reached capacity (this requires the room capacity be set in Exchange and a camera capable of people counting). Set to false if you wish to disable these warnings. |
| `<FrontRowEnabled>` | Boolean ❷ | First ❶ | Enabled by default. If false, Front row is disabled. For more information, see [Set front row as the default layout](manage-front-row). |
| `<FrontRowVideoSize>` | String |  | Lets you set the size of Front row to provide more or less space for remote participant video and shared content. Possible values are `small`, `medium`, and `large`. The default value is `medium`. For more information, see [Set front row as the default layout](manage-front-row). |
| `<FrontRowPanelDefaults>` | String |  | Lets you configure the position of the raise hand and chat components in the meeting panels to the left and right of meeting content on front-of-room displays.To manually configure the position of the raise hand and chat components, specify the numeric values of the component that should be shown in the left and right panels respectively, separated by a comma (for example, `3,1`). Panels using the same component will be ignored except for **1** Hide the panel.<br>- **1** Hide the panel.<br>- **2** Show meeting chat.<br>- **3** Show raised hand list.<br><br>If `FrontRowPanelDefaults` isn't specified in dual display mode, the raise hand component is shown in the left panel and chat component is shown in the right panel. In single display mode, the left panel isn't displayed by default for front-of-room displays narrower than 21:9. |
| `<DefaultFoRExperience>` | Boolean ❷ | First ❶ | Gallery view by default. Put 1 to change the default layout from Gallery view to Front row. For more information, see [Set front row as the default layout](manage-front-row). |
| `<EnableResolutionAndScalingSetting>` | Boolean ❷ | First ❶ | By default it's disabled. If you want to change your front-of-room's resolution and scaling, set it to true. If true, the display resolution and scale setting will be applied. This setting will affect both the main front-of-room display and extended front-of-room display once this setting is enabled. For more information, see [Remotely configure layout, scale, and resolution on Teams Rooms displays](manage-front-room-scale-res). |
| `<MainFoRDisplay>` | Container | First ❶ | Use this container if your device is using single display mode.In dual display mode, the main front-of-room display is the screen where the room calendar is shown. This screen is meant to be installed on the right-hand side. `<MainFoRDisplayResolution>` and `<MainFoRDisplayScaling>` must be set together at the same time. If you only use either `<MainFoRDisplayResolution>` or `<MainFoRDisplayScaling>`, it will be ignored. For more information, see [Remotely configure layout, scale, and resolution on Teams Rooms displays](manage-front-room-scale-res). |
| `<MainFoRDisplayResolution>` | String |  | Input numeric value of Width, Height (e.g. 1920,1080 or 3840,2160). It will be ignored if your front-of-room display doesn't support it. For more information, see [Remotely configure layout, scale, and resolution on Teams Rooms displays](manage-front-room-scale-res). |
| `<MainFoRDisplayScaling>` | Number |  | Input numeric value of scaling. Valid values are 100 (recommended), 125, 150, 175, 200, 225, 250, and 300. If you input greater than and your front-of-room display only supports up to 300, it will be set to 300. For more information, see [Remotely configure layout, scale, and resolution on Teams Rooms displays](manage-front-room-scale-res). |
| `<ExtendedFoRDisplay>` | Container | First ❶ | In dual display mode, the extended front-of-room display is the screen where the date, time, and room information are displayed. This screen is meant to be installed on the left-hand side. `<ExtendedFoRDisplayResolution>` and `<ExtendedFoRDisplayScaling>` must be set together at the same time. If you only use either `<ExtendedFoRDisplayResolution>` or `<ExtendedFoRDisplayScaling>`, it will be ignored. For more information, see [Remotely configure layout, scale, and resolution on Teams Rooms displays](manage-front-room-scale-res). |
| `<ExtendedFoRDisplayResolution>` | String |  | Input numeric value of Width, Height (e.g. 1920,1080 or 3840,2160). A value will be ignored if your front-of-room display does not support it. For more information, see [Remotely configure layout, scale, and resolution on Teams Rooms displays](manage-front-room-scale-res). |
| `<ExtendedFoRDisplayScaling>` | Number |  | Input numeric value of scaling. Valid values are 100 (recommended), 125, 150, 175, 200, 225, 250, and 300. If you input greater than 300 and your front-of-room display only supports up to 300, it will be set to 300. For more information, see [Remotely configure layout, scale, and resolution on Teams Rooms displays](manage-front-room-scale-res). |
| `<SingleFoRDefaultContentLayout>` | String |  | In single display mode, you can set the default layout between Content+people and Content only:<br>- **0** Content only<br>- **1** Content+people (default)<br><br> For more information, see [Remotely configure layout, scale, and resolution on Teams Rooms displays](manage-front-room-scale-res). |
| `<ShowMeetingChat>` | Boolean ❷ | First ❶ | Enabled by default. If disabled, meeting chat functionality (including chat bubbles and chat selection) isn't available in any meeting layout on the Teams Rooms device. |
| `<OpenMeetingChatByDefault>` | Boolean ❷ | First ❶ | Enabled by default. If disabled, chat panel won't show by default in meetings using Gallery view. |
| `<PrioritizeVideoParticipantsGallery>` | Boolean ❷ | First ❶ | Enabled by default. Video participants appear on the main stage with audio participants on the side or bottom rail. If disabled, audio and video participants are mixed together. |
| `<HideMeForAllLayouts>` | Boolean ❷ | First ❶ | Disabled by default. If enabled, preview video will be hidden for all layouts. |
| `<EnablePublicPreview>` | Boolean ❷ | First ❶ | Disabled by default. If true, public preview is enabled and end-users can access features in public preview on enabled Teams Rooms. See [Public preview for Microsoft Teams Rooms on Windows](../public-preview-doc-updates#public-preview-for-microsoft-teams-rooms-on-windows) for more information. |
| `<NoiseSuppressionDefault>` | String | First ❶ | Controls noise suppression levels in Teams.<br>- **0** Off. Use OEM-provided noise suppression only.<br>- **1** High. Suppresses all background noises (stationary and nonstationary) that aren't speech. |
| `<SendLogs>` | Container | First ❶ |  |
| `<SendFeedbackToPMP>` | Boolean ❷ | First ❶ | Enabled by default. If true, when a user sends feedback through Report a problem from a room with a Teams Room Pro license, each feedback creates an event in the Teams Rooms Pro Management portal. |
| `<EmailAddressForLogsAndFeedback>` | String ❸ |  | Sets an email address that receives logs and feedback submitted using Report a problem. |
| `<SendLogsAndFeedback>` | Boolean ❷ |  | Allows logs to be sent with feedback submitted using Report a problem. To ensure logs and feedback with larger sizes are delivered, adjust the message size restriction for your mailboxes on the Exchange admin center. |
| `<Devices>` | Container | First ❶ | The connected audio device names in the child elements are the same values listed in the Device Manager app. The configuration can contain a device that does not presently exist on the system, such as an A/V device not currently connected to the console. The configuration would be retained for the respective device. |
| `<MicrophoneForCommunication>` | String ❸ |  | Sets the microphone used as the recording device in a conference. |
| `<SpeakerForCommunication>` | String ❸ |  | Device to be used as speaker for the conference. This setting is used to set the speaker device used in a call. |
| `<DefaultSpeaker>` | String ❸ |  | Device to be used to play the audio from an HDMI ingest source. |
| `<ContentCameraId>` | String ❸ |  | Define the instance path for the camera configured in room to share analog whiteboard content in a meeting. See Locate the Content camera USB instance path. |
| `<ContentCameraInverted>` | Boolean ❷ |  | Specify if the content camera is physically installed upside down. For content cameras that support automatic rotation, specify false. |
| `<ContentCameraEnhancement>` | Boolean ❷ |  | When set to true (the default), the content camera image is digitally enhanced: the whiteboard edge is detected and an appropriate zoom is selected, ink lines are enhanced, and the person writing on the whiteboard is made transparent.  Set to false if you intend to send a raw video feed to meeting participants for spaces where a whiteboard is not drawn on with a pen and instead the camera is used to show sticky notes, posters, or other media. |
| `<Theming>` | Container | First ❶ | One of the features that can be applied with an XML file is a Custom Theme for your organization. You're able to specify a theme name, background image, and color. |
| `<ThemeName>` | String ❸ |  | Used to identify the theme on the client. The Theme Name options are ` Vivid Flag Default`, one of the provided preset themes, or `Custom`.  Custom theme names always use the name `Custom`. The client UI can be set at the console to the Default or one of the presets, but use of a custom theme must be set remotely by an Administrator.  Preset themes include: `Vivid Flag Default``Summer Summit``Seaside Bliss``Into The Fold``Creative Conservatory``Default``Blue Wave``Digital Forest``Dreamcatcher``Limeade``Purple Paradise``Pixel Perfect``Roadmap``Sunset` To disable the current theme, use `No Theme` for the `<ThemeName>`. |
| `<CustomBackgroundMainFoRDisplay>` | String ❸ |  | Used to specify the filename of the main/right custom background image on Teams Rooms version 4.17 and later with a Microsoft Teams Rooms Pro license.  Required if `<ThemeName>` is set to `Custom`. For more information, see [Set up and manage Teams Rooms on Windows 4.17 and later custom backgrounds](/en-us/microsoftteams/rooms/custom-backgrounds?tabs=Enhanced). |
| `<CustomBackgroundExtendedFoRDisplay>` | String ❸ |  | Used to specify the filename of the extended/left custom background image on Teams Rooms version 4.17 with a Microsoft Teams Rooms Pro license.  Required if `<ThemeName>` is set to `Custom`**and**`<DualScreenMode>` is set to `true`. For more information, see [Set up and manage Teams Rooms on Windows enhanced custom backgrounds](/en-us/microsoftteams/rooms/custom-backgrounds?tabs=Enhanced). |
| `<CustomBackgroundConsole>` | String ❸ |  | Used to specify the filename of the touch console custom background image on Teams Rooms version 4.17 and later with a Microsoft Teams Rooms Pro license.  Optional. For more information, see [Set up and manage Teams Rooms on Windows enhanced custom backgrounds](/en-us/microsoftteams/rooms/custom-backgrounds?tabs=Enhanced). |
| `<CustomThemeImageUrl>` | String ❸ |  | Used to specify a custom theme image file name on Teams Rooms version 4.16 and earlier or on devices with a Teams Rooms Basic license. Input the file name only. For more information on custom themes, see [Set up and manage Teams Rooms on Windows standard custom backgrounds](/en-us/microsoftteams/rooms/custom-backgrounds?tabs=Standard). On Teams Rooms version 4.17 and later, we recommend you use the `<CustomBackgroundMainFoRDisplay>`, `<CustomBackgroundExtendedFoRDisplay>`, and `<CustomBackgroundConsole>` elements. |
| `<RemoveFoRCalendar>` | Boolean ❷ |  | Remove the calendar on front-of-room displays. Disabled by default. For more information, see [Microsoft Teams Rooms home screen design refresh](mtr-home-refresh). |
| `<CoordinatedMeetings>` | Boolean ❷ | First ❶ | Container for the configuration elements for Coordinated Meetings. This element has one attribute:<br>- **enabled** Determines whether Teams is configured to participate in Coordinated Meetings with other devices. |
| `<TrustedAccounts>` | String |  | This is a comma-separated list of UPNs for each Teams Rooms device or Surface Hub that the device should accept meeting join requests from, or to which meeting join requests should be sent. |
| `<Settings>` | Container |  | Container for the configuration audio and video configuration elements for Coordinated Meetings. |
| `<Audio>` | Boolean ❷ |  | Controls audio configuration on a Teams Rooms device. This element has two attributes:<br>- **default** Determines on which device the microphone will be active when a meeting starts. Only one device (typically a Teams Rooms device) can have this field set to `true` while the rest of the devices must have this field set to `false` to avoid audio echo and feedback.<br>- **enabled** Determines whether participants in a meeting can toggle the microphone on or off. Devices on which **Audio default** is set to `false` should have this setting set to `false` so that participants can't accidentally turn on a microphone and cause audio echo or feedback.<br>    If **Audio default** is set to `true`, the **Audio enabled** setting is ignored and participants can mute or unmute the microphone. |
| `<Video>` | Boolean ❷ |  | Controls video configuration on a Teams Rooms device. This element has two attributes:<br>- **default** Determines on which device the camera will be active when a meeting starts. For the best experience, we recommend that only the Teams Rooms device be set to `true` while all other devices are set to `false`.<br>- **enabled** Determines whether participants in a meeting can toggle the camera on or off. You can set this to `true` on any other devices in the event participants want to share different video perspectives (such as if a participant is using the Surface Hub whiteboard). If you don't want participants to turn a camera on or off on a device, set this to `false`.<br>     If **Video default** is set to `true`, the **Video enabled** setting is ignored and participants can turn the camera on or off. |
| `<Whiteboard>` | Boolean ❷ |  | Controls whiteboard configuration on a Teams Rooms device. This element has two attributes:<br>- **default** Determines on which device the whiteboard will be active when a meeting starts. For the best experience, we recommend that the Teams Rooms device be set to `false` and that you use the whiteboard on a Surface Hub.<br>- **enabled** Determines whether participants in a meeting can toggle the whiteboard on or off. If you don't want participants to turn the whiteboard on or off on a device, set this to `false`.<br>     If **Whiteboard default** is set to `true`, the **Whiteboard enabled** setting is ignored and participants can turn the whiteboard on or off. |
| `<EnableDeviceEndToEndEncryption>` | Boolean ❷ |  | Default is `false`. Specify `true` to enable end-to-end encryption for one-to-one Teams calls. Both caller and recipient need to have end-to-end encryption enabled for this to work. |
| `<RoomLanguageSwitchEnabled>` | Boolean ❷ |  | Default is `true`. Specify `false` to block end users from changing the console language. |
| `<SplitVideoLayoutsDisabled>` | Boolean ❷ |  | Default is `false`. This setting is only applicable to dual-display rooms. Specify `true` to disable splitting video gallery across both screens. This will also disable Front row layout, and any settings associated with Front row layout. |

❶ All of the first-level elements are optional. If a first-level element is omitted, all of its child parameters remain unchanged on the device.

❷ A boolean flag can be: true, false, 0, or 1. Leaving boolean or numeric values empty can render the XML malformed and prevent changes to the settings.

❸ If a string parameter is present and empty, and empty is a valid value, the parameter is cleared on the device.

## Locate the Content camera USB instance path

To locate the instance path:

1. Go into Windows settings on the Microsoft Teams Rooms console.
2. Enter the admin password.
3. From a Command Prompt, type `devmgmt.msc` to bring up Device Manager.
4. In **Device Manager**, look in the **Imaging devices** node and locate the content camera.
5. Right-click the camera, and open **Properties**.
6. Select the **Details** tab, and locate the **Device instance path** property in the drop-down.
7. The value shown is the device instance path to set in the XML configuration file. When specifying the path in XML, replace the ampersand (&) with `&amp;`.