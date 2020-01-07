
### To allow the bot to work Correctly with ESX_RPChat Follow these steps
* Open your ESX_RPChat Directory
* Go to client > main.lua and delete ALL THE CODE in this file 
**(DO NOT DELETE THE FILE JUST THE CONTENTS/CODE INSIDE)**

* Now Go To server > main.lua and replace the code inside of it with the code in the link below
> [main.lua](https://pastebin.com/unkeAzcC)
* Save and Profit 

━━━━━━━━━━━━━━━━━━━━━━━
### Additional Fix
* Under each Register Command in your `esx_rpchat > client > main.lua` and your `esx_rpchat > server > main.lua` Files add this line 

`TriggerEvent('DiscordBot:ToDiscord', 'chat', steam,'[Server 1]  ' .. '**TWITTER: **' .. args, 'logoimageurl', true)`
* If this was done correct it should look like this

> [Example Register Command Event](https://pastebin.com/V6Xanc5s)
* Save and Profit 

### Side Note
> **PLEASE USE ONLY ONE OF THE FIXES PROVIDED IF ONE DOESNT WORK TRY THE NEXT AND ALWAYS MAKE A BACKUP OF THESE FILES BEFORE EDITING THEM**

━━━━━━━━━━━━━━━━━━━━━━━

### Documentation Pages
> [Home](../README.md)

> [Installation Instructions](Docs/INSTALLATION.md)

> [Supported Versions](Docs/SUPPORTED-VERSIONS.md)

> [Changelog & Updates](Docs/CHANGELOG.md)

> [My Contact Options](Docs/CONTACT.md)
