---
layout: Conceptual
title: Required desktop client diagnostic data for Microsoft Teams - Microsoft Teams | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/microsoftteams/privacy/policy-control-diagnostic-data-desktop
breadcrumb_path: /microsoftteams/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-MicrosoftTeams
ms.suite: office
feedback_system: Standard
feedback_product_url: https://aka.ms/TeamsFeedback
recommendations: true
ms.author: divyasrirk
author: DivySri-RK
manager: prgholve
ms.topic: reference
ms.service: msteams
ms.subservice: msteams-admin
audience: admin
ms.reviewer: majaisin,stbyer
ms.date: 2020-08-13T00:00:00.0000000Z
description: A list of desktop properties and events for the policy controls for Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- privacy-teams
- must-keep
locale: en-us
document_id: ce04d066-1080-7102-4caa-9568857e061a
document_version_independent_id: 484b9ad8-1ce4-9d8d-64ca-23007cf02dd9
original_content_git_url: https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/live/Teams/privacy/policy-control-diagnostic-data-desktop.md
site_name: Docs
depot_name: office.OfficeDocs-MicrosoftTeams
page_type: conceptual
toc_rel: ../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/office.OfficeDocs-MicrosoftTeams/{branchName}{pdfName}
feedback_help_link_type: ''
feedback_help_link_url: ''
asset_id: privacy/policy-control-diagnostic-data-desktop
moniker_range_name: 
monikers: []
item_type: Content
source_path: Teams/privacy/policy-control-diagnostic-data-desktop.md
cmProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/63959238-cb90-4871-a33d-4a5519097e47
- https://authoring-docs-microsoft.poolparty.biz/devrel/3e34b70d-bca0-4369-a01b-71d1edfd427b
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://authoring-docs-microsoft.poolparty.biz/devrel/78d87f42-5582-4a6b-90be-7db2f12b34e6
- https://authoring-docs-microsoft.poolparty.biz/devrel/8ca32b3f-fa14-46df-b09a-9c4a591d6396
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 454e8842-2e68-19dd-834d-9de00e6a083a
---

# Required desktop client diagnostic data for Microsoft Teams - Microsoft Teams | Microsoft Learn

The following article contains a list of Microsoft Teams desktop events, and lists of properties each event collects.

For more information about diagnostic data, including how to control what diagnostic data is sent to Microsoft, see [Diagnostic data sent from the Teams app to Microsoft](policy-control-overview#diagnostic-data-sent-from-the-teams-app-to-microsoft). To view the diagnostic data being sent to Microsoft, you can use the [Diagnostic Data Viewer](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855).

## Events

Note

There are common properties for all events listed below, to review them, see Properties sent with all events.

### Logging

Note

For information on the properties of Logging events, see Properties sent with logging events.

- **adal-anonymous-mac.ts:this.logger.logError** - Records that a generic sso error occurred when logging in anonymously on a Mac device.
- **adalAnonymousUtil.ts:loggingService.getInstance** - Records error statement logging that the app couldn't launch anonymous user authentication.
- **adal-anonymous-windows.ts:this.logger.logError** - Records that a generic sso error occurred when logging in anonymously on a windows device.
- **adalBase.ts:this.loggingService.logError** - Records information needed to determine that the user profile is null or empty.
- **adal-impl-mac.ts:this.loggingService.logError** - Records the occurrence of an issue when parsing telemetry received during authentication or generic sso error occurred when logging in on a Mac device.
- **adal-rigel-windows.ts:this.logger.logError** - General logging statement indicating a generic sso error occurred when logging in on our Meeting room device.
- **adal-sso-windows.ts:this.loggingService.logError** - Records that a generic sso error occurred when logging in on a Windows device, errors in initiating the chat service or log in failure information.
- **appOnlineService.ts:loggingService.getInstance** - Records the occurrence of an error due to settings that couldn't be parsed during startup or with downloading pre-user authentication, pre-authorized settings.
- **appStart.ts:loggingService.logError** - Records the occurrence of an error when the application couldn't launch, disk space error, valid certificate error or failed to find the correct certificate, and restarting the app.
- **browserWindowHttp.ts:this.loggingService.logError** - Records information to indicate that the application couldn't be updated due to issues with the file system.
- **contextInstallService.ts:loggingService.getInstance**- Records the occurrence of an error when:
    - attempting to parse or read a file or resolve a URL critical to the contextual install feature.
    - the URL shortener attempts to run the contextual install feature.
- **crashManager.ts:loggingService.logError** - Records information to determine the cause of an error when the application crashes.
- **localStorageService.ts:loggingService.getInstance** - Records the occurrence of an error when essential boot data doesn't load properly to run the application.
- **logProviders\pageDumpProvider.ts:loggingService.getInstance** - Records error information when the application crashes.
- **multiWindowManager.ts:this.logError** - Records the occurrence of an error when essential boot data doesn't load properly to run the application.
- **nativeElectronNotifications\osNotificationService.ts:this.loggingService.logError** - This event records the occurrence of an error when attempting to launch a notification about a failure.
- **OutlookMeetingAddinHelper.ts:loggingService.getInstance** - Records the occurrence of an error when attempting to connect to a meeting using the Outlook meeting add-in.
- **recoveryManager.ts:loggingService.getInstance** - Records the occurrence of an error during update rollbacks.
- **renderer\startPage\startPage.ts:this.logger.logError** - Records the occurrence of an error with the application start page.
- **settingsService.ts:loggingService.getInstance** - Records the occurrence of an error with the application settings.
- **updateInfo.ts:loggingService.getInstance** - Records the occurrence of an error with transmitting updates.
- **updatenotification.js:this.\_loggingService.logError** - Records the occurrence of disk space issues.
- **utility.ts:loggingService.logError** - Records an error accessing a local file (a file in the application).
- **utility.ts:loggingService.getInstance** - Records an error in available diskspace, display issues, url issues, cookie issues, protocols, or regkey issues on machine to load the application.
- **windowmanager.js:this.\_loggingService.logError** - Records the occurrence of cookie issues, whitescreen issues, issues between desktop and shell communication, url issues,errors with loading page messages, errors with process rendering, and network connectivity issues.
- **windowmanager.js:loggingService.getInstance** - Records information to indicate when the recovery window can't be shown.

### Outlook add-in

Note

For information on the properties of Outlook add-in events, see Properties sent with Outlook add-in events.

- **joinmeetingoperation** - Records information needed to join a user to a meeting.
- **meetingaddinapplifecycle** - Records information regarding app state such as Launch or Exit.
- **meetingaddinloadtime** - Records the time it takes to load meeting information from Outlook.
- **openmeetingoperation** - Records information needed to open a scheduled meeting.
- **savemeetingoperation** - Records information needed to save the meeting while scheduling it.

### Scenario

Note

For information on the properties of Scenario events, see Properties sent with scenario events.

- **desktop\_app\_load** - Records information needed to determine that the desktop application has launched, that the service should be initialized, and that it's able to be initialized.
- **desktop\_app\_not\_ready** - Records information needed to determine that the desktop application isn't ready to function.
- **desktop\_install** - Records information needed to determine that the desktop application has been installed successfully, or that it failed to install.
- **desktop\_previous\_lifecycle\_invalid** - Records information needed to determine that the desktop application restarted after it had been previously been running and then crashed.

### Tracking

Note

For information on the properties of Tracking events, see Properties sent with tracking events.

- **deeplink\_scenario\_missing** - Teams was launched from a deeplink, but the telemetry/diagnostic isn't present.
- **desktop\_app\_initialized** - Records information needed to determine if the application has successfully started when the desktop application is initialized.
- **desktop\_app\_quit\_exception** - The application crashed while attempting to close.
- **desktop\_blankScreenDetected** - Records information needed to determine errors when the desktop application renders a blank screen.
- **desktop\_blankScreenDetectedAfterRepaint** - Detected that page was blank upon detecting rendering attempt.
- **desktop\_blankScreenRecoveredAfterRepaint** - Recovered from a rendering issue where the screen wasn't rendered earlier.
- **desktop\_configuration\_failed\_to\_save** - Collects information needed to determine configuration errors when desktop settings have failed to save.
- **desktop\_navigation\_error\_recovery** - Collects information needed to determine desktop navigation errors when a page fails to load after five attempts.
- **desktop\_previous\_gpu\_crashed** - Records information needed to determine graphics processing unit errors when the desktop crashes.
- **desktop\_previous\_plugin\_host\_crashed** - Collects information need to determine media stack issues associated with desktop application crashes.
- **desktop\_recovery\_cleared\_user\_data** - Records application crashed multiple times, and app had to clear local cache to recover.
- **desktop\_settings\_blank\_on\_load** - This is an error that the applications settings aren't present.
- **desktop\_settings\_failed\_to\_load** - Collects information needed to determine cause when desktop settings fail to load.
- **desktop\_silent\_restart** - Client update is staged and client is updated without user disruption.
- **desktop\_terminated** - Records information needed to determine whether the inter-process communication has been disconnected when the user closes the desktop application.
- **desktop\_uncaught\_exception** Function call on an undefined object, this will result in a crash/app restart.
- **desktop\_write\_storage\_failed** - Records information needed to determine disk errors when the desktop application fails to write to storage.
- **registration\_failed** - Records information needed to resolve add-in registration failures.
- **registration\_success** - Records information needed to determine whether add-in registrations were successful.
- **security\_unsupported\_ipc\_channel** - Interprocess message that wasn't permitted was inbound.
- **sfb\_running\_not\_connected** - Detected that the Skype for Business app isn't running.
- **sfb\_not\_running** - Records that the 'wait for response' from call to Skype of Business timed out.
- **sfb\_never\_replied** - Tracks no API response when communicating with Skype for Business.
- **server\_error\_hit** - Tracks that an error from the ipc pipes communicating with Skype for Business.
- **unexpected\_sfb\_ipc\_disconnection** - Records information needed to determine a failure to connect to the service.
- **unregister\_failed** - Records information needed to determine errors in de-registering the Outlook meeting add-in.

## UserBI panelaction

Note

For information on the properties of UserBI panelaction events, see Properties sent with UserBI panelaction events.

- **inlinereply** - Records information whether a user has replied from the notification.
- **toastclick** - Records a user's click to navigate to the message entry to toast notifications to monitor service SLA and to load the appropriate response to toast notification.
- **toastdismiss** - Records information needed to determine errors and delays when the user dismisses the rendering of a toast notification.
- **toast\_skip** - Records information needed to avoid transmitting a delayed toast notification.
- **toasttimeout** - Records information needed to determine errors and delays when the rendering of a toast notification has timed out.

### UserBI panelview

Note

For information on the properties of UserBI panelview events, see Properties sent with UserBI panelview events.

- **toastshow** - Records information needed to determine that a toast was rendered.

## Property lists

### Properties sent with all events

| Property name | Description |
| --- | --- |
| EventInfo\_Time | Event generation time |
| EventInfo\_Name | Event name - Used to differentiate between event types |
| EventInfo\_BaseType/name | Event type - Used to differentiate between event types in an event |
| EventInfo\_Sequence | Sequence of the event |
| userAgent | Browser agent string |
| userpdclevel | Privacy data control setting of the user |
| eventpdclevel | Privacy data control categorization level of the event |
| AppInfo\_Language | App language |
| clientType/AppInfo\_ClientType | Client type where the app is running |
| environment/AppInfo\_Environment | Engineering environment that served the user request |
| clientVersion/appversion/AppInfo\_Version/desktopBuildVersion | Version of the app |
| buildtime | timestamp that the app was built in engineering systems |
| osversion/DeviceInfo\_OsVersion | OS version |
| AppInfo\_ProcessArchitecture | System architecture (32bit/64bit) |
| preferredLocales | preferred locale for the user |
| locale/AppInfo\_Locale | App locale |
| os/DeviceInfo\_OsName | OS Name |
| UserInfo\_Language | Selected user language |
| UserInfo\_Id | User ID |
| UserInfo\_TenantId/TenantId | Tenant ID |
| ring/UserInfo\_Ring | Concept that helps deliver application in a phased manner |
| region | Datacenter region that served user's request |
| UserInfo\_ConfigIds/UserInfo\_Etag | ID that helps identify users in different experiments/rollouts |
| DeviceInfo\_BrowserName | Browser name |
| DeviceInfo\_BrowserVersion | Browser version |
| DeviceInfo\_Id/machineId/DeviceInfo\_IdV2 | ID that helps identify the device |
| totalMemory | Hardware memory of the device |
| cores | Hardware cores of the device |
| cpuspeed | Hardware cpu speed of the device |
| DeviceInfo\_CpuArchitecture/cpuarchitecture | CPU architecture of the device |
| UserRole | Helps identify user role in a tenant |
| DeviceInfo\_WindowsMode | Helps identify Windows security mode |
| desktopSession/Session\_Id | Helps identify a session |
| dbOpen | Captures state of the local database |
| UserInfo\_Upn | One sided hash of user identifier |

### Properties sent with logging events

| Property name | Description |
| --- | --- |
| message | Captures a detailed message about the log |

### Properties sent with scenario events

| Property Name | Description |
| --- | --- |
| Scenario\_Status | Status of a scenario |
| Scenario\_Step | Step in a scenario |
| sequence | Sequence number of the scenario |
| delta | Time taken to complete different steps in a scenario |
| elapsed | Time since the scenario started |
| scenario | Uniquely identify a scenario |
| Scenario\_Name | Name of the scenario |
| errorInfo | Info of the error that might have occurred during a scenario |
| session | Unique session ID |
| freeMemory | Captures free memory available |
| processMemory | Captures process memory |
| scenarioDelta | Captures time different between two scenario steps |
| Session\_DesktopId | Unique session ID |
| machineLocked | Captures if the machine was locked or not |
| windowIsVisible | Captures if the app window was visible to use |
| appStates/webAppStates | records a list of app states that the app went through. This helps with crash investigation because we can see what state the app was in |
| crashDesktopSession | Captures ID of the crashed session |
| appRuntime | Captures runtime of the app |
| diagnosticEvents | Last 50 web app diagnostic events before app crash |
| activities | Last 50 user scenario names which happened before crash |
| crashSession | Captures ID of the crashed session |
| crashId | Captures ID of the crashed session |
| isPreviousLifecycleValid | Whether previous app was fully initialized and terminated successfully |
| isSettingValid | Whether preauth settings are valid |
| rollbackReason | Reason due to which app was rolled back |
| deeplinkType | Type of the deeplink |
| watchdogCrash | Whether app crashed due to hang |
| protocols | Protocol used to launch the app |
| electronBuild | Build version of electron app |
| distribution | whether Teams was installed via exe or msi or dmg or pkg, etc. |
| updateTimeOfDay | Time the app was updated |
| launchPath | whether Teams is installed in %LOCALAPPDATA%, %PROGRAMFILES%, or other locations |
| loggedIn | If the user was logged in |
| envType/complianceEnvironmentType | Commercial cloud or private (for example, DoD, GCC-High, etc.) |
| cpuusage | CPU usage |
| installationSource | Type of installation user has |
| adalVersion | Version of the auth library |
| asyncStart | Is the app using synchronous or asynchronous start |
| attempts | Number of online check attempts made for the user before showing a blocking screen |

### Properties sent with tracking events

| Property name | Description |
| --- | --- |
| name2 | Captures name of the tracking event |
| numVisibleNotifications | Number of visible application notifications |
| giphyEnabled | Whether giphy service was enabled |
| error | Captures error details related to the tracking event |
| method | Protocol method GET or POST |
| channel | Captures inter-process communication channel within the app |
| windowTitle | Type of display window associated with event |
| message | The type of error message |
| crashSession/crashDesktopSession/crashId/Session\_DesktopId/Session\_DesktopBackgroundId | Captures unique ID for session debug purposes |
| responseCode | Captures response code for the service call |
| errorUrl | The URL that failed to load |
| errorCode | Captures error code |
| ssoEventData | Authentication state and status |
| correlationId | ID to correlate events with service side for debug purposes |
| errorDescription | Captures description of the errorcode |
| source | Method to get the Teams app and what package type Teams was installed from |
| windowIsDestroyed | True/False state of Application Windows during event |
| windowIsFocused | True/False state of Application Windows during event |
| windowIsVisible | Was the application visible when event happened |
| windowIsMinimized | True/False state of Application Windows during event |
| windowIsMaximized | True/False state of Application Windows during event |
| windowIsFullscreen | True/False state of Application Windows during event |
| distSrc | Captures the distribution source of user landing into the app |
| retries | Retry count when attempting to connect to an endpoint |
| uses\_slimcore | True or false if web call is using slimcore |
| persistCookieExpiresIn | Time remaining in validity of web application cookie |
| tenantName | Name of tenant for user of the application |
| appStartReason | How the application session started such as user initiated, after updating, etc. |
| machineLocked | Whether machine was locked or not locked during the event |
| data | Captures technical data for scenario investigation |
| appRuntime | Captures runtime of the app |
| activities | Last 50 user scenario names that happened before crash |
| timeSinceActivity | Time since last user activity |
| appStates | Records a list of app states that the desktop app went through, which helps with crash investigations because it shows what state the desktop app was in |
| timeSinceAppState | Time since the app state changed |
| webAppStates | Records a list of app states that the web client went through, which helps with crash investigations because it shows what state the web client app was in |
| timeSinceWebAppState | Time since the web app state changed |
| diagnosticEvents | Last 50 web app diagnostic events before app crash |
| timeSinceLastDiagnosticEvent | Time since last diagnostic event sent |
| timeSinceSecondLastDiagnosticEvent | Time since second-last diagnostic event sent |
| appInitialized | Whether webapplication has started |
| targetVersion | Version application is going to be updated to |
| port | Internet message port number |
| originalUrl | Original location of page being rendered |
| deeplinkId | GUID for destination type of Teams link |
| appSessionEnd | Whether event occurred at end of application session |
| eventData | Captures machine state and app config to help debugging in case of issues |
| deeplinkType | Type of the deeplink (chat, meeting, channel) |
| previousUpdateUrl | Location where application last retrieved its update from |
| previousUpdateVersion | Last version application was updated to |
| previousUpdateTime | When application binaries were last updated |
| protocol | Handler type for link, such as file or image |
| files | Type of file associated with an event, such as Application cache or GPU cache |
| Perf\_WorkingSetSizeKB | Size of memory cache |
| isTimeboxingWebAppInitialize | Whether app initialized before time box counter ran out |
| isExp | Whether the app version in use is part of an experiment |
| deviceType | Captures type of the device |
| sanitizedErr | Captures sanitized version of the error information |
| rigelVersion | Captures version of rigel device |
| DeviceInfo\_OsSku | Captures OS SKU information |
| isLoggedOut | Captures if the user is logged out |
| complianceEnvironmentType | Commercial cloud or private (for example, DoD, GCC-High, etc.) |
| restartTimes | Exact times of previous restarts |
| Skype\_ResultCode | Captures result of interop communication between Skype and Teams |
| cpumodel | Captures model of CPU |
| isSlimCoreRunningOutproc | Whether Slimcore component is running in its own process |
| isSlimCoreStartedAsync | Type of launch of internal audio/video (A/V) stack |
| networkState | Captures state of the network |
| desktopBuildAge | How old the application build is at event time |
| vdiMode | Captures if the app is running in VDI mode |

### Properties sent with UserBI panelview events

| Property | Description |
| --- | --- |
| Panel\_Uri | Uri of the panel delivered to the user |
| Panel\_Type | Panel type accessed by the user |
| Team\_Id | ID of the team in which action was performed by the user |
| Thread\_Id | ID of the thread that was accessed by user |
| Panel\_PreviousUri | URI of the previous panel |
| Panel\_Region | Region where the panel was hosted in the app |
| Panel\_LaunchMethod | Method through which the panel was launched |
| Panel\_PreviousType | Type of the previous panel |
| Thread\_Type | Type of thread accessed by user |
| Panel\_LaunchSource | Source information of the panel that was launched |
| Tab\_Type | Type of the tab accessed by user |
| Team\_Type | Type of team accessed by user |

### Properties sent with UserBI panelaction events

| Property name | Description |
| --- | --- |
| Action\_DestinationUri | Uri of the resource being accessed by user action |
| Panel\_Uri | Uri of the panel delivered to the user |
| Action\_Gesture | Type of gesture performed by user on the app |
| Action\_ScenarioType | Feature grouping that relates to business metric for feature |
| Panel\_Type | Panel type accessed by the user |
| Action\_Outcome | Outcome of the action performed by user |
| Team\_Id | ID of the team in which action was performed by the user |
| Module\_Type | Type of the module that hosted user action |
| Module\_Name | Name of the module that hosted user action |
| Module\_Summary | Summary of the module that hosed user action |
| Thread\_Id | ID of the thread that was accessed by user |
| Panel\_PreviousUri | URI of the previous panel |
| Panel\_Region | Region where the panel was hosted in the app |
| Panel\_LaunchMethod | Method through which the panel was launched |
| Panel\_PreviousType | Type of the previous panel |
| Thread\_Type | Type of thread accessed by user |
| Module\_State | State of the module accessed by user |
| Action\_Scenario | Feature inside a group of features that relates to business metric |
| Panel\_LaunchSource | Source information of the panel that was launched |
| Tab\_Type | Type of the tab accessed by user |
| Team\_Type | Type of team accessed by user |

### Properties sent with Outlook add-in events

| Property Name | Description |
| --- | --- |
| AccountComparisonFailedReason | Add-in compares the account with Teams account to see if creation is allowed, this event is sent if the comparison fails |
| AccountComparisonSuccessful | Add-in compares the account with Teams account to see if creation is allowed, this event is sent if the comparison is successful |
| AdalVersion | Version of the authentication library used |
| AddinBitness | Version of add-in |
| AddinLanguage | Language of add-in strings being used |
| AggregatorSetupCompletedTime | Setup time for add-in loader |
| AppDomainCreatedTime | Time when add-in loader initializes app domain |
| AppointmentDisplayTime | Time at which the appointment item was displayed during meeting creation |
| AuthenticationCompletedTime | Time at which authentication was provided for a given request |
| ConnectionMode | Indicates the connection mode of the user's primary Exchange account |
| ConnectionStartedTime | Time when Outlook calls OnConnection |
| ErrorDetails | Captures details of the error |
| ErrorName | Captures name of the error |
| ExchangeVersion | Captures version of Exchange |
| IsSmtpFormatError | Error in SMTP address |
| IsTeamsRunning | Captures if there's a Teams process running |
| IsTeamsUserLoggedOut | Captures if the user is logged out of Teams |
| LanguageSetupCompletedTime | Time at which language setup got completed |
| ManagedConnectTime | Time when the managed add-in received the connect callback |
| ManagedOnStartupTime | Time when managed started the startup |
| MTFetchCompleted | Time when MT meeting options request is completed |
| NetFrameworkVersion | .nET framework used |
| NetworkAvailable | Is network available |
| OperationStartTime | Time when different operations started |
| OsBitness | Bitness of OS |
| OutlookLanguage | Captures language of the Outlook app |
| OutlookVersion | Captures version of Outlook app |
| OwnerResolutionTime | Time to resolve the meeting owner |
| ParseResponseCompletedTime | Time when parsing of response completed |
| RecipientResolutionError | Error details when resolving a recipient |
| RecipientsResolutionTime | Total time to resolve all recipients |
| RehydrateCompletedTime | Time when properties are read from Outlook |
| SaveToOutlookCompletedTime | Time when properties are saved to Outlook |
| ServiceRequestStartTime | Start time of the service request |
| ServiceResponseReceiveTime | Time of response from the service |
| SettingsInitializeCompletedTime | Time when settings initialized |
| SetupLoggingCompletedTime | Time when logging was set up |
| ShutdownBeginTime | Time when shutdown of add-in begins |
| ShutdownCompletedTime | Time when shutdown completed |
| StartupBeginTime | Time when startup of add-in begins |
| StartupCompletedTime | Time when startup completed |
| TeamsDeployment | Deployment of Teams client (Dev, Prod) |
| TeamsRing | Ring of current user logged into Teams client |
| TeamsVersion | Captures version of Teams app |
| TelemetrySetupCompletedTime | Time when telemetry setup is completed |
| UpnMismatch | Whether there's a upn mismatch between outlook and teams |
| UserDomain | Domain of the user |
| ViewUpdatedTime | Time when the view got updated |