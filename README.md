# SettingsPageVisibility
The `SettingsPageVisibility` registry key (`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\Explorer!SettingsPageVisibility`) is used to control which settings pages are visible to the user in the Windows Settings application.

`Get-SettingsPageVisibility` and `Set-SettingsPageVisibility` started as basic functions used to hide and un-hide the Windows Update settings page on devices where ConnectWise Automate was managing the updates and configuring this registry key to prevent users from accessing the Windows Update settings page.

When it came time to recreate the functions on my own time, I wanted to get away from using a basic PSObject to house the properties. Not wanting to rely on compiling C# code using the `Add-Type` cmdlet or compiling a DLL, I went down the rabbit hole of defining custom classes in PowerShell. The result is the absolute abomination visible in the [src](/src) folder.

# Additional Reading
- [Configure the Settings Page Visibility in Windows | Microsoft Learn](https://learn.microsoft.com/en-us/windows/configuration/settings/page-visibility)
- [Settings Page Visibility | Microsoft Learn](https://learn.microsoft.com/en-us/windows/iot/iot-enterprise/customize/page-visibility)
- [Settings Policy CSP | Microsoft Learn](https://learn.microsoft.com/en-us/windows/client-management/mdm/policy-csp-settings#pagevisibilitylist)
- [Launch the Windows Settings app - Windows apps | Microsoft Learn](https://learn.microsoft.com/en-us/windows/apps/develop/launch/launch-settings-app#ms-settings-uri-scheme-reference)
- [How to Hide or Show Specific Settings Page in Windows 11 | Windows OS Hub](https://woshub.com/hide-show-settings-pages-windows/)