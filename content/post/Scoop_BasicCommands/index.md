---
date : '2025-03-04T20:43:42+08:00'
draft : false
title : 'Scoop_BasicCommands'
description: 'Insturctions for scoop installation and daily use'
image : 'Isla.jpg'
categories : 
    - Windows
---
> [Scoop GitHub](https://github.com/ScoopInstaller/Scoop)
>
> [Scoop Wiki](https://github.com/ScoopInstaller/Scoop/wiki )

1. ### Scoop installation

   ```powershell
   Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
   # Specify the path as disk D
   $env:SCOOP='D:\Scoop'
   Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
   ```

2. ### Scoop basic commands

   ```powershell
   # Basic commands
   scoop status
   scoop checkup
   
   scoop update
   scoop update *
   
   scoop list
   ```

3. ### Scoop add buckets

   ```powershell
   # Display recognizable buckets 
   scoop bucket known
   
   # Add buckets
   scoop bucket add extras
   scoop bucket add versions
   scoop bucket add nirsoft
   scoop bucket add nerd-fonts
   scoop bucket add games
   scoop bucket add apps  https://github.com/kkzzhizhou/scoop-apps
   scoop bucket add dorado  https://github.com/chawyehsu/dorado  
   
   # Display buckets added
   scoop bucket list
   ```

4. ### Software installation

   ```powershell
   # Search software information
   scoop search <package>
   scoop info <package>
   scoop depends <package>
   scoop install <package> (--global)
   scoop uninstall <package>
   
   # Install common software
   scoop install 7zip git sudo aria2 curl grep sed less touch 
   scoop install python ruby go perl
   scoop install yazi ffmpeg jq jid poppler fd ripgrep fzf zoxide imagemagick ghostscript
   ```

5. ### Software Location

   ```bash
   # Locate a shim/executable (similar to 'which' on Linux)
   scoop which <package>
   
   # Returns the path to the specified app
   scoop prefix <package>
   ```

6. ### Scoop config

   ```powershell
   # Get or set configuration values
   scoop config
   
   # Configuration
   scoop config aria2-max-connection-per-server 32
   scoop config aria2-split 16
   scoop config aria2-min-split-size 1M
   ```

7. ### Scoop clear cache

   ```powershell
   scoop cache rm *
   
   # Clean up all outdated software versions
   scoop cleanup *
   ```

8. ### Software version freezing

   ```powershell
   # Hold an app to disable updates
   scoop hold <package>
   scoop unhold <package>
   ```

9. ### Software version control

   When installing multiple versions of the same software, you have the option to switch between them using this command. This usually involves resetting the environment variables and some other settings for the software, so that they point to the version you want installed via Scoop.

   ```powershell
   # Reset an app to resolve conflicts
   scoop reset <package>
   ```

10. ### Software export and import  

    ```bash
    # Export installed apps, buckets (and optionally configs) in JSON format
    scoop export > ~/desktop/scoop-export.json
    
    # Export with configs
    scoop export -c > ~/desktop/scoop-export.json
    
    # Import apps, buckets and configs from a Scoopfile in JSON format
    scoop import ~/desktop/scoop-export.json
    ```
