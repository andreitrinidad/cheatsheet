# Windows Web Development Environment Setup

## Recommended Things
- Windows Terminal (Preview) - Better Terminal


# First Things first
## 1. Installing VS Code
### Fonts and Theme

  **Fira Code** - font ligatures
   
  Put this in `settings.json`

  ```
  "editor.fontFamily": "Fira Code",
  "editor.fontLigatures": true,
  ```

**Cobalt2** - Wes Bos theme

### Other Helpful Extensions
- Auto-open Markdown Preview - preview markdown realtime
- Eslint
- Gitlens - obviously for Git
<!-- Add links later-->

---

## 2. Setting up WSL

Windows Subsystem on Linux

2.1 Install via elevated Powershell
  
  ```
  Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
  ```

2.2 Download Linux distro from the Windows Store

## 3. Installing Valet

3.1 Open you WSL terminal and enter the following commands:

3.1 Installing PHP 7.1

```bash
#creating own repo
sudo add-apt-repository ppa:ondrej/php

#updating ubuntu
sudo apt-get update && sudo apt-get upgrade

#Slow part
sudo apt-get install php-fpm php-mysql php7.1-cli php7.1-curl php7.1-mbstring php7.1-mcrypt php7.1-xml php7.1-zip php7.1-intl curl git unzip php-cli

```
[Useful link](https://dev.to/jackabox/setting-up-a-windows-10-development-environment-with-wsl-php--laravel-4e18) about this 




