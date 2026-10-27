# DIABLO II: REBORN

**Download the latest version:** [Releases → Latest](https://github.com/ZebskiGaming/Diablo2Reborn-Releases/releases/latest)  ·  **Discord:** https://discord.gg/2KuF4RGPM

> **Pre-alpha:** Reborn is in active development. Expect rough edges, and please report anything odd on Discord.

## Mission statement

Diablo II: Reborn exists to bring new life to the game we love without losing what made it great.

We believe Diablo II's problem was never too much power. It was too few choices. So instead of nerfing the builds, items and strategies players love, we raise up everything that was left behind: forgotten skills, ignored uniques, overlooked mercenaries. Every class should have more than one way to win, and every drop should have a chance to matter.

We respect your time. Grinding is part of Diablo II, but it should be a hunt, not a chore. And through every change, we ask one question: does this still feel like Diablo II?

Reborn is, and always will be, free. No pay-to-win, no shortcuts for sale. Just the game, made better, for the community that kept it alive.

*Requires your own legitimate copy of Diablo II and Lord of Destruction. Reborn runs on game version 1.13c.*

## Two ways to play

| | **Closed realm** (recommended) | **Open play** |
|---|---|---|
| Where characters are saved | On the Reborn server | On your own PC |
| Difficulty | Every game is **players 8** | Normal player count |
| How to join | Reborn gateway → main **Battle.net** button | Reborn gateway → **Other Multiplayer → Open Battle.net** |

Characters don't move between the two.

# INSTALL GUIDE

## What you need

- Diablo II and Lord of Destruction, installed from your own Blizzard account.
- Windows 10 or 11.

Reborn's download contains only Reborn's own files (game data, RebornLoader.exe and RebornPlugin.dll). It does not include any Blizzard game files, so you convert your own copy of the game to version 1.13c (step 2).

## First-time install

1. **Make a separate copy of the game.**
   Copy your whole Diablo II folder to a new folder, for example `C:\Diablo2Reborn`. Everything below happens in that copy, so your normal game stays untouched.

2. **Convert the copy to 1.13c.**
   The free, open-source Slashdiablo launcher can do it ([github.com/nokka/slashdiablo-launcher](https://github.com/nokka/slashdiablo-launcher)):
   1. Run the launcher, click **Get started**, and set the Diablo II directory to your Reborn copy.
   2. Set **Maphack version** and **HD mod version** to **none**.
   3. Click **Done**, then **Update now**, and wait for it to finish.
   4. Close the launcher. Don't use its Play button for Reborn.
   5. In your Reborn folder, **delete** (or move into a subfolder) `SlashDiablo.dll`, `D2Template.dll` and `StormLib.dll`. These are Slashdiablo's own add-ons; `SlashDiablo.dll` switches your gateway back to "Slash Diablo" every time the game starts.

3. **Turn off DEP for this game only.**
   1.13c crashes on modern Windows (`UNHANDLED EXCEPTION: ACCESS_VIOLATION (c0000005)`) unless Data Execution Prevention is off for it:
   1. Open **Windows Security → App & browser control → Exploit protection settings → Program settings**.
   2. Click **Add program to customize → Choose exact file path**, and pick `Game.exe` in your Reborn folder.
   3. Under **Data Execution Prevention (DEP)**, tick **Override system settings** and switch it **Off**. Click **Apply**.

   This affects only that one `Game.exe`, nothing else on your PC.

4. **Download the latest release** and extract the zip into your Reborn folder, so that `RebornLoader.exe`, `RebornPlugin.dll`, `Play Reborn.bat` and a `data` folder all sit next to `Game.exe`.

5. **Set the gateway.** Double-click `Reborn-Gateway.reg` and click **Yes**. (Do this after step 2, because the launcher changes your gateway list.)

6. **Play.** Start the game with `Play Reborn.bat`. Check the main menu says **v 1.13**, choose the **Reborn** gateway, then:
   - **Closed realm:** click the main **Battle.net** button, create an account, and make a new character.
   - **Open play:** click **Other Multiplayer → Open Battle.net**.

**Bringing open play characters over:** 1.13c keeps characters in the `Save` folder inside your Reborn folder. Copy your files from `C:\Users\<you>\Saved Games\Diablo II` into it (keep a backup of the originals).

## Updating to a new release

1. Delete the old `data` folder from your Reborn folder.
2. Extract the new zip the same way as above, replacing `RebornLoader.exe` and `RebornPlugin.dll` too.
3. Everyone in a game must have the same release. If you get disconnected when joining, compare `VERSION.txt` with the host.

## If something goes wrong

- **"Error 1: ... Please run D2VidTst":** run `D2VidTst.exe` in your Reborn folder and pick Direct3D. If it does nothing, edit `Play Reborn.bat` and add `-3dfx` after `-txt` to use the included Glide graphics wrapper.
- **ACCESS_VIOLATION (c0000005):** redo step 3, and make sure you chose the `Game.exe` inside your Reborn folder.
- **The gateway keeps showing "Slash Diablo":** delete `SlashDiablo.dll`, `D2Template.dll` and `StormLib.dll` (step 2.5), then double-click `Reborn-Gateway.reg` again.
- **"Windows error 740" from RebornLoader:** `Game.exe` is set to run as administrator. Right-click `Game.exe` → **Properties → Compatibility**, and untick any compatibility mode or "Run as administrator".
- **RebornLoader does nothing, or reports a missing VCRUNTIME140.dll:** install Microsoft's [Visual C++ Redistributable (x86)](https://aka.ms/vs/17/release/vc_redist.x86.exe).
- **Antivirus warning about RebornLoader.exe:** the loader starts the game and loads RebornPlugin into it, which some antivirus programs mistake for a threat. It's Reborn's own tool; add an exception for your Reborn folder.

## Hosting open play games

Joining games works out of the box. To **host** an open play game that others can join, forward TCP port **4000** on your router to your PC. (Closed realm games are hosted by the Reborn server, so nothing is needed there.)

## Notes

- Reborn is a free fan project. Never pay anyone for Reborn items.
- Players on different game versions (1.13c and 1.14d) can't join each other's games.
- Questions, feedback and bug reports: [Discord](https://discord.gg/2KuF4RGPM)
