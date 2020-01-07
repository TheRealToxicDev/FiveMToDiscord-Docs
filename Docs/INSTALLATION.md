### INSTALLATION INSTRUCTIONS

**STEP 1: Create A Webhook**

If you want System Infos, Killing Log and Chat Message notifications.

* Create A Discord Channel Named "System Logs" or "FiveM Logs" 
* Go To The Channel Settings & Select "Webhooks"
* Click On "Create Webhook" 
* Set Your Bot Name & Picure
* Copy Your Webhook URL & Save It for Later
* Save & Profit

***

**STEP 2: Add your Webhook**

If you want System Infos, Killing Log and Chat in three channels, replace the webhooks links I have in lines 1, 2 & 3 with the webhooks link for each channel. Otherwise, create just one Webhook and replace these 3 lines with that webhook

* First of all, create a Discord Webhook, if not already done. See "STEP 1"
* Copy the link of the Webhook
* Open the config.lua
* Replace Lines 1,2 & 3
* Save & Profit

***

**STEP 3: Call the Webhook event from another resource**

Simply use this:

-- Channels: 'chat' or 'system' or 'kill'

`TriggerEvent('DiscordBot:ToDiscord', 'WHICH_CHANNEL', 'NAME', 'MESSAGE', 'IMAGE_URL', true)
The boolean always has to be true, when calling DiscordBot:ToDiscord with the channel names ('chat', 'system' and 'kill')`

***

**STEP 4: Changing the System Avatar**

* Open the config.lua
* Replace https://wiki.fivem.net/w/images/d/db/FiveM-Wiki.png at line 3 with your preferred Image
* Save & Profit

***

**STEP 5: Changing the User Avatar**

* Open the config.lua
* Replace https://i.imgur.com/KIcqSYs.png at line 5 with your preferred Image
* Save & Profit

***

**STEP 6: Changing the System Name**

* Open the config.lua
* Replace "SYSTEM" at line 7 with your preferred name
* Save & Profit

***

**STEP 7: Specify Special Commands**

* Open the config.lua
* Add (or remove) the Command in the SpecialCommands Table, in the given format
* Save & Profit

***

**STEP 8: Blacklist Commands**

* Open the config.lua
* Add (or remove) the Command in the BlacklistedCommands Table, in the given format
* Save & Profit

***

**STEP 9: Specify Commands which have their own webhook**

* Open the config.lua
* Add (or remove) the Command in the OwnWebhookCommands Table, in the given format
* Save & Profit

***

**STEP 10: Specify TTS Commands**

* Open the config.lua
* Add (or remove) the Command in the TTSCommands Table, in the given format
* Save & Profit

***

**(How To)'Fix' some commands not printing (Not recommended though)**

* Open the cl_chat.lua in the chat resource
* Find this piece of code:` if data.message:sub(1, 1) == '/' then
      ExecuteCommand(data.message:sub(2))
    else
      TriggerServerEvent('_chat:messageEntered', GetPlayerName(id), { r, g, b }, data.message)
    end`
* Add This: `TriggerServerEvent('DiscordBot:ToDiscord', 'chat', GetPlayerName(id) .. ' [ID: ' .. GetPlayerServerId(id) .. ']', data.message, 'steam', GetPlayerServerId(id), false, true)`
in a new line after ExecuteCommand(data.message:sub(2)) to make it look like this:
`if data.message:sub(1, 1) == '/' then
      ExecuteCommand(data.message:sub(2))
 	  TriggerServerEvent('DiscordBot:ToDiscord', 'chat', GetPlayerName(id) .. ' [ID: ' .. GetPlayerServerId(id) .. ']', data.message, 'steam', GetPlayerServerId(id), false, true)
	else
      TriggerServerEvent('_chat:messageEntered', GetPlayerName(id), { r, g, b }, data.message)
    end`
* Save & Profit

━━━━━━━━━━━━━━━━━━━━━━━

### Documentation Pages
> [Home](../README.md)

> [ESX_RPChat Support/Fix](Docs/ESX-FIX.md)

> [Supported Versions](Docs/SUPPORTED-VERSIONS.md)

> [Changelog & Updates](Docs/CHANGELOG.md)

> [My Contact Options](Docs/CONTACT.md)
