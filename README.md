# Disable Microsoft Cortana

Cortana is included in Windows 10. (More information about Cortana: https://support.microsoft.com/en-us/help/17214/windows-10-what-is

When creating a Windows 10 master image, you may want to disable it. You can disable Cortana using PowerShell with a registry key:

 ```python
PS > New-Item -Path 'HKLM:\SOFTWARE\Policies\Microsoft\Windows\' -Name 'Windows Search' | Out-Null
PS > New-ItemProperty -Path 'HKLM:\SOFTWARE\Policies\Microsoft\Windows\Windows Search' -Name 'AllowCortana' -PropertyType DWORD -Value '0' | Out-Null
 ```

This transforms the Cortana box into a “Search Windows” box.

Note: you can also disable Cortana by GPO(Group Policy Object).

Just Navigate to:

Computer Configuration
> Administrative Templates
>> Windows Components
>>> Search.
>>>> Set the “Allow Cortana” option to “Disabled”

## Alternative Way 


Just Copy the "Disable-MCortana.ps1" Script in my repo and ctrl+v in your notepad

Save the File as "Disable-MCortana.ps1".

Now Right click on the "Disable-MCortana.ps1" and select "Run with PowerShell"

Done! Cortana should be disabled now, whenever you use the search bar, it will be the good old search bar, you won't see the cortana icon
