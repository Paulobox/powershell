## Installation
Go to Documents directory and clone repo:
```ps1
git clone https://github.com/Paulobox/powershell
```

[chocolatey](https://chocolatey.org/install)

Modules:
```ps1
choco install terminal-icons.powershell fzf oh-my-posh zoxide -y
```

PSReadline:
```ps1
Install-Module -Name PSReadLine -AllowPrerelease -Scope CurrentUser -Force -SkipPublisherCheck
```

PSFzf
```ps1
Install-Module -Name PSFzf -AllowPrerelease -Scope CurrentUser -Force -SkipPublisherCheck
```

---

# OTHER

## Git Commands

<details><summary>remove .git folder in current directory</summary>
  
```powershell
Remove-Item -Path .\.git -Recurse -Force
```

</details>

## powershell scripts

<details><summary>Convert from .png to .webp in current directory</summary>
  
```powershell
$outputDirectory = $PWD.Path
if (-not (Test-Path $outputDirectory)) {
    New-Item -ItemType Directory -Force -Path $outputDirectory
}
Get-ChildItem *.png | ForEach-Object {
    & "cwebp.exe" -q 70 -o (Join-Path -Path $outputDirectory -ChildPath "$($_.BaseName).webp") $_.FullName
}
```
  
</details>

## BCD backup WINDOWS:
Open CMD as administrator:
<details><summary>bcd export</summary>
bcdedit /export "%UserProfile%\Desktop\MyBCDEdit.bcd"
</details>

<details><summary>bcd import</summary>
bcdedit /import "<full path of BCD file>"
bcdedit /import "%UserProfile%\Desktop\MyBCDEdit.bcd"
</details>
