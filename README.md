# SA-MP Discord Rich Presence (Extended)

[![Release](https://img.shields.io/badge/Release-v1.0.0-blue.svg)](https://github.com/panntzyy/samp-discord-rpc/releases)
[![Platform](https://img.shields.io/badge/Platform-GTA%20San%20Andreas%20%2F%20SA%3AMP-orange.svg)]()
[![License](https://img.shields.io/badge/License-MIT-green.svg)]()

A modern, highly customizable **Discord Rich Presence plugin (.asi)** for Grand Theft Auto: San Andreas Multiplayer (SA:MP). 

This project is an **extended continuation of the original `samp-discord-plugin` by [Hual](https://github.com/Hual/samp-discord-plugin)**, bringing full configuration control, zero third-party DLL dependencies, and enhanced Discord activity features.

---

## What's New in the Extended Version?

| Feature | Original (Hual) | **Extended Version (This Mod)** |
| :--- | :---: | :---: |
| **Configuration File** | ❌ No (Hardcoded) | ✅ **Full `samp-discord-rpc.ini` support** |
| **Discord App Presence** | ❌ Locked to original ID | ✅ **Modernized App ID (`GTA Mabar`) with official assets** |
| **Interactive Discord Buttons** | ❌ Not supported | ✅ **Up to 2 clickable buttons (Dynamic Server Website + Repo)** |
| **Empty Server Fallback** | ⚠️ Forced tumbleweed if < 10 players | ✅ **Clean default SA:MP logo (no tumbleweed)** |
| **Dynamic Text Formatter** | ❌ Hardcoded format | ✅ **Custom placeholders (`%hostname%`, `%ip%`, `%nickname%`, etc.)** |
| **Custom Server Logos & Links** | ✅ Online list | ✅ **`server-config.txt` with dynamic server Website/Discord links** |
| **Dependencies** | Requires VC++ runtimes | ✅ **Pure Win32 static build (zero extra DLLs)** |

---

## Quick Installation

### Option 1: Via Modloader (Recommended)
1. Download `samp-discord-rpc.asi` and `samp-discord-rpc.ini` from the [Releases](https://github.com/panntzyy/samp-discord-rpc/releases).
2. Create a new folder inside your Modloader directory:
   ```
   GTA San Andreas\modloader\Discord RPC\
   ```
3. Put `samp-discord-rpc.asi` and `samp-discord-rpc.ini` inside that folder.
4. If you have an older Discord plugin (`samp-discord-plugin.asi`), remove or disable it to avoid conflicts.

### Option 2: Direct GTA SA Folder
Place `samp-discord-rpc.asi` and `samp-discord-rpc.ini` directly into your main GTA San Andreas directory.

---

## Configuration (`samp-discord-rpc.ini`)

You can edit `samp-discord-rpc.ini` with Notepad anytime without restarting the game:

```ini
[Discord]
UpdateInterval = 10
; Automatically fetches server logos & websites from GitHub repo
CustomLogosURL = https://raw.githubusercontent.com/panntzyy/samp-discord-rpc/main/server-config.txt

[Presence]
Details = %hostname%
State = %ip%:%port%
ShowTimestamp = 1
LargeImageKey = logo
LargeImageText = %players%/%maxplayers% players online
SmallImageKey = info
SmallImageText = Playing as %nickname%
```

### Discord Buttons (Automatic & Smart)
- **Button 1 ("Website")**: Automatically displays the official website or Discord invite of the server being played (fetched dynamically from `server-config.txt`). If the server has no registered website, Button 1 is automatically omitted.
- **Button 2 ("Custom Discord SAMP RPC")**: Always links to this open-source repository.

### Supported Placeholders:
- `%hostname%` : SA:MP Server hostname
- `%ip%` : Server IP address
- `%port%` : Server port
- `%nickname%` : Your player nickname
- `%players%` : Current online players
- `%maxplayers%` : Maximum server player slots
- `%gamemode%` : Running gamemode
- `%mapname%` : Server map name

---

## How to Request Your Server's Logo & Website

Want your SA:MP server's logo and official website/Discord link to automatically appear for all players?

1. Go to the **[Issues Tab](https://github.com/panntzyy/samp-discord-rpc/issues)**.
2. Click **New Issue** and select **Custom Server Logo Request**.
3. Fill in your Server IP, Server Name, Website / Discord Link, and attach a **512x512 transparent PNG or JPG logo**.
4. Once verified, your server will be added to `server-config.txt`!

*(Server owners can also submit a Pull Request directly modifying [`server-config.txt`](server-config.txt)).*

---

## Credits
- **[Hual](https://github.com/Hual)** - Original creator and pioneer of the SA:MP Discord Rich Presence plugin concept.
- **[panntzyy](https://github.com/panntzyy)** - Extended version architecture, standalone named pipe IPC, dynamic formatting, and INI configuration engine.
