# Disable-Cortana

Cortana is included in Windows 10. (More information about Cortana: https://support.microsoft.com/en-us/help/17214/windows-10-what-is)

When creating a Windows 10 master image, you may want to disable it. You can disable Cortana using PowerShell with a registry key:

PS > New-Item -Path 'HKLM:\SOFTWARE\Policies\Microsoft\Windows\' -Name 'Windows Search' | Out-Null
PS > New-ItemProperty -Path 'HKLM:\SOFTWARE\Policies\Microsoft\Windows\Windows Search' -Name 'AllowCortana' -PropertyType DWORD -Value '0' | Out-Null
This transforms the Cortana box into a “Search Windows” box.

Note: you can also disable Cortana by GPO.

Navigate to:

Computer Configuration
> Administrative Templates
>> Windows Components
>>> Search.
Set the “Allow Cortana” option to “Disabled”
