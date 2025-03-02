---
id: logs-trace
title: Trace logs
sidebar_label:  Trace logs
---

The Trace logs will help you keep trace of all the actions taken by Overwolf and make sure that everything is running smoothly. You can also use these logs to view basic system information, Overwolf user information (If the user is logged in), the users gamelist version and if Windows 10 Hardware Accelerated GPU Scheduling is enabled (Which may cause issues with recording).

It’s also important to check that the overlay is enabled, if Overwolf helpers launched correctly, which extensions are running, which Overwolf processes are running & when Overwolf processes have closed and other processes currently running on the computer to check for any interference. 

## OW, OS and User info

In the first section of the Trace log you can check under which path Overwolf is installed, the system information such as Windows version, build & .NET version. If the user is logged in you can also view their account details :

```
2021-07-20 10:21:00,606 (INFO) [UI][12564] AppCenter - command line: C:\Program Files (x86)\Overwolf\Overwolf.exe -from-startmenu -launchapp ojgnfnbjckbpfaciphphehonokbggjhpnnoafack
2021-07-20 10:21:00,607 (INFO) [UI][12564] AppCenter - Running dll folder: C:\Program Files (x86)\Overwolf\0.174.87.15
2021-07-20 10:21:00,657 (INFO) [UI][12564] AppCenter - Registering for restart with commandline: -from-startmenu -launchapp ojgnfnbjckbpfaciphphehonokbggjhpnnoafack -ARR 1
2021-07-20 10:21:00,704 (INFO) [UI][12564] AppCenter - Process tree:	OverwolfLauncher - C:\Program Files (x86)\Overwolf\OverwolfLauncher.exe (35256)	explorer - C:\Windows\explorer.exe (9916)
2021-07-20 10:21:00,714 (INFO) [UI][12564] AppCenter - Found 1 processes named 'Overwolf'
2021-07-20 10:21:00,719 (INFO) [UI][12564] AppCenter - is unique process: True
2021-07-20 10:21:00,721 (INFO) [UI][12564] ClientInstanceManager - Testing overwolf instances
2021-07-20 10:21:00,721 (INFO) [UI][12564] ClientInstanceManager - First unique Overwolf instance
2021-07-20 10:21:00,760 (INFO) [UI][12564] CefGlobalFlags - Global CEF flags init
2021-07-20 10:21:00,937 (INFO) [UI][12564] LoginSession - Initializing Login Session (Windows 10 64-bit, .NET 4.5, 10.0.19041.1023)
2021-07-20 10:21:00,940 (INFO) [ 8][8868]  UserInformationLog - UID: OW_c58ed287-9974-4f2f-829f-6826d8bc6143
2021-07-20 10:21:00,940 (INFO) [ 8][8868]  UserInformationLog - MUID: c17f3db1-9075-4045-9507-197c7eac9126
2021-07-20 10:21:00,941 (INFO) [ 8][8868]  UserInformationLog - Username: shirel.garfinkle
2021-07-20 10:21:00,941 (INFO) [ 8][8868]  UserInformationLog - Channel:  website (ML:website) 
2021-07-20 10:21:00,942 (INFO) [ 8][8868]  UserInformationLog - CurrentVersion: 0.174.87.15
2021-07-20 10:21:00,942 (INFO) [ 8][8868]  UserInformationLog - LastVersion: 0.174.0.10
2021-07-20 10:21:00,943 (INFO) [ 8][8868]  UserInformationLog - UpdateRequireUAC: false
2021-07-20 10:21:00,951 (INFO) [UI][12564] LevelDBStorage - LevelDB version: 1.22
```

## GPU and HAGS

In this section you can see which GPU is used and if Hardware-accelerated GPU scheduling is enabled. If it is enabled and causing issues with recording you can ask the user to disable it using [this guide](https://support.overwolf.com/en/support/solutions/articles/9000181387-common-capture-issues#accel). 

```
2021-07-20 10:21:01,010 (INFO) [ 9][4760]  <>c - Override GPU Info with dxdiag [Intel(R) UHD Graphics, NVIDIA GeForce GTX 1650 Ti,  ] -> [Intel(R) UHD Graphics, NVIDIA GeForce GTX 1650 Ti,  ]
2021-07-20 10:21:01,055 (INFO) [ 8][8868]  UserInformationLog - OS: HAGSEnable: False
```

## Overlay life cycle

In this section you can see the Overwolf overlay starting up:

```
2021-07-20 10:21:01,703 (INFO) [OverlayService ID 15][23824] OverlayService - Initializing OverlayService
2021-07-20 10:21:01,703 (INFO) [OverlayService ID 15][23824] OverlayService - Connecting to OverlayService
2021-07-20 10:21:01,717 (INFO) [OverlayService ID 15][23824] OverlayService - Waiting for OverwolfHelper.exe to exit
2021-07-20 10:21:01,727 (INFO) [OverlayService ID 15][23824] OverlayService - Starting OWServer
```

## extensions info

In this section you can see the amount of extensions the user has, which extensions are loading (According to their unique ID) and if there are any issues in loading the extensions:

```
2021-07-20 10:21:03,482 (INFO) [UI][12564] ExtensionDataManager - Loading 26 installed extensions...
2021-07-20 10:21:03,484 (INFO) [UI][12564] ExtensionDataManager - Loading per-load extensions
2021-07-20 10:21:03,814 (INFO) [UI][12564] ExtensionDataManager - Loading extension ppagiehdogdjlomggmoejfamedbjggdggnjbilhe silently...
2021-07-20 10:21:03,816 (INFO) [UI][12564] ExtensionsUpdateManager - Updating packages info synchronously.
2021-07-20 10:21:03,954 (INFO) [UI][12564] ExtensionsUpdateManager - parsed update data of 583 extensions.
2021-07-20 10:21:03,954 (INFO) [UI][12564] ExtensionsUpdateManager - clearing and updating packages
2021-07-20 10:21:03,961 (INFO) [UI][12564] ExtensionsUpdateManager - Package data updated. Will check again in 02:00:00 hours
2021-07-20 10:21:03,966 (WARN) [18][26900] ExtensionDataManager - wait for load to end...
2021-07-20 10:21:03,995 (INFO) [UI][12564] ExtensionDataManager - Loading extension ggfmakpbllghoepnmfelddbminamnbmfelbahfdp silently...
2021-07-20 10:21:04,002 (INFO) [UI][12564] ExtensionDataManager - Loading extension geajlfbgmkaklkojofefpgnnjcceibhakfjhfefk silently...
2021-07-20 10:21:04,003 (INFO) [UI][12564] ExtensionsUpdateManager - Could not find package geajlfbgmkaklkojofefpgnnjcceibhakfjhfefk
2021-07-20 10:21:04,007 (INFO) [UI][12564] ExtensionDataManager - Loading extension midihkloolidnegokmecmcdepinaidpmbpgpncek silently...
2021-07-20 10:21:04,011 (INFO) [UI][12564] ExtensionDataManager - Loading extension bebanicmemnmpcomjjlnjkeionhgkkdgfdocgdam silently...
2021-07-20 10:21:04,016 (INFO) [UI][12564] ExtensionDataManager - Loading extension ecbhmmfmjonpojpbedhhhbjanafifbbcjofikdim silently...
2021-07-20 10:21:04,016 (INFO) [UI][12564] ExtensionGameEventsProvider - ecbhmmfmjonpojpbedhhhbjanafifbbcjofikdim is set not to init on startup
2021-07-20 10:21:04,021 (INFO) [UI][12564] ExtensionDataManager - Loading extension oldfhfbggeglgjgenidckaneodejpjkaggklojma silently...
2021-07-20 10:21:04,025 (INFO) [UI][12564] ExtensionDataManager - Loading extension cmhjmacifnhhboffmobjofpejedkbnfolcgijhpc silently...
2021-07-20 10:21:04,030 (INFO) [UI][12564] ExtensionDataManager - Loading extension hadnijlcblooohinkbaggccaedldhpfdnaagefci silently...
2021-07-20 10:21:04,039 (INFO) [UI][12564] ExtensionDataManager - Loading extension nafihghfcpikebhfhdhljejkcifgbdahdhngepfb silently...
2021-07-20 10:21:04,045 (INFO) [UI][12564] ExtensionDataManager - Loading extension pmecpbelmicelkhhcdlonffhgoclgcdbfgmdfhag silently...
2021-07-20 10:21:04,052 (INFO) [UI][12564] ExtensionDataManager - Loading extension cccgaknkmciakiacadiefgpmbcgboopeohekmigg silently...
2021-07-20 10:21:04,072 (INFO) [UI][12564] ExtensionDataManager - Loading extension kfnacgfblhkjdgcndfdobooemjaapcefaminngbk silently...
2021-07-20 10:21:04,084 (INFO) [UI][12564] ExtensionDataManager - Loading extension cghphpbjeabdkomiphingnegihoigeggcfphdofo silently...
2021-07-20 10:21:04,214 (INFO) [UI][12564] ExtensionDataManager - Loading extension dafpjodfmofenjonekfnkphpghegoekhfepmbmib silently...
2021-07-20 10:21:04,278 (INFO) [UI][12564] ExtensionDataManager - Loading extension ojgnfnbjckbpfaciphphehonokbggjhpnnoafack silently...
2021-07-20 10:21:04,286 (INFO) [UI][12564] ExtensionDataManager - Loading extension cchhcaiapeikjbdbpfplgmpobbcdkdaphclbmkbj silently...
2021-07-20 10:21:04,307 (INFO) [UI][12564] ExtensionDataManager - Loading extension pibhbkkgefgheeglaeemkkfjlhidhcedalapdggh silently...
2021-07-20 10:21:04,423 (INFO) [UI][12564] ExtensionDataManager - Loading extension lnknbakkpommmjjdnelmfbjjdbocfpnpbkijjnob silently...
2021-07-20 10:21:04,485 (INFO) [UI][12564] ExtensionDataManager - Loading extension nonfnefnlcikmjkkdclbhpojenalpkcoipjjognm silently...
2021-07-20 10:21:04,545 (INFO) [UI][12564] ExtensionDataManager - Loading extension decddmhlpdgkcihhfbahfkafojbjckglidmilgoh silently...
2021-07-20 10:21:04,659 (INFO) [UI][12564] ExtensionDataManager - Loading extension bfcbjmpkifhjdigfjiapnkokoajejacldgpoldgi silently...
2021-07-20 10:21:04,695 (INFO) [UI][12564] ExtensionDataManager - Loading extension kpaejaacomnkenpbmclnglmblpmfiapjlebhpcom silently...
2021-07-20 10:21:04,759 (INFO) [OverlayService ID 15][23824] OverlayService - Overlay started
2021-07-20 10:21:04,778 (INFO) [OverlayService ID 15][23824] LoginSession - Init after overlay ready
2021-07-20 10:21:04,909 (INFO) [UI][12564] ExtensionDataManager - Loading extension ikakjhlicfmeoglkoihlnhphenmedggccipebkkb silently...
2021-07-20 10:21:04,944 (INFO) [UI][12564] ExtensionDataManager - Loading extension fbikhiaoalpganbhcfceednmcmolodebmnnmfpmc silently...
2021-07-20 10:21:04,955 (INFO) [UI][12564] ExtensionDataManager - Loading extension fiekjlgoffmlmgfmggnoeoljkmfkcapcdmcgcfgm silently...
2021-07-20 10:21:05,100 (INFO) [UI][12564] ExtensionDataManager - Collecting uninstalled extensions from extension installation folder...
```

## OW Helpers info

In this section you can see the Overwolf Helpers starting (Hyperlink to the section about helpers)

```
2021-07-20 10:21:05,728 (INFO) [26][7788]  OverwolfHelpersProcesesManager - Launching helper OverwolfHelper.exe: 0
2021-07-20 10:21:05,737 (INFO) [26][7788]  OverwolfHelpersProcesesManager - Looking for helper in C:\Program Files (x86)\Common Files\Overwolf\0.174.87.15\OverwolfHelper.exe
2021-07-20 10:21:05,737 (INFO) [26][7788]  OverwolfHelpersProcesesManager - Helper working directory: C:\Program Files (x86)\Common Files\Overwolf\0.174.87.15
2021-07-20 10:21:05,740 (INFO) [26][7788]  OverwolfHelpersProcesesManager - Asking the user to allow Overwolf.exe admin privileges
2021-07-20 10:21:05,742 (INFO) [26][7788]  OverwolfHelpersProcesesManager - Starting helper C:\Program Files (x86)\Common Files\Overwolf\0.174.87.15\OverwolfHelper.esxe "path=C:\Program Files (x86)\Overwolf\0.174.87.15\win32\OWExplorerLauncher.dll pid=11708"
2021-07-20 10:21:05,774 (INFO) [19][19032] UpdatesServiceManager - Found a service, running it
2021-07-20 10:21:05,810 (INFO) [UI][12564] TrayContextMenuViewModel - Refreshing recent games in recently launched games tray menu
2021-07-20 10:21:05,832 (INFO) [26][7788]  OverwolfHelpersProcesesManager - The user has allowed Overwolf.exe admin privileges

```
