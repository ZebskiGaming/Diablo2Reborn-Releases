# DIABLO II: REBORN

**Download the latest version:** [Releases → Latest](https://github.com/ZebskiGaming/Diablo2Reborn-Releases/releases/latest)  ·  **Discord:** https://discord.gg/2KuF4RGPM

> **Pre-alpha:** Reborn is in active development. Expect rough edges, and please report anything odd on Discord.

## Mission statement

Diablo II: Reborn exists to bring new life to the game we love without losing what made it great.

We believe Diablo II's problem was never too much power. It was too few choices. So instead of nerfing the builds, items and strategies players love, we raise up everything that was left behind: forgotten skills, ignored uniques, overlooked mercenaries. Every class should have more than one way to win, and every drop should have a chance to matter.

We respect your time. Grinding is part of Diablo II, but it should be a hunt, not a chore. And through every change, we ask one question: does this still feel like Diablo II?

Reborn is, and always will be, free. No pay-to-win, no shortcuts for sale. Just the game, made better, for the community that kept it alive.

*Requires your own legitimate copy of Diablo II and Lord of Destruction. Reborn runs on game version 1.13c.*

## Features at a glance

- **Class reworks** that bring forgotten skills back to life, with more to come.
- **Sharper, smoother graphics** (D2GL) and **widescreen up to 1068×600**, approved on the Reborn realm.
- **Quality of life:** Ctrl+click quick-move, gold auto-pickup, stat roll ranges on hover, purple uniques, and a Show Items toggle.
- **A closed realm** (characters saved on the server, every game players 8) and **open play**.

---

# Install guide

## What you need

- Diablo II and Lord of Destruction, installed from your own Blizzard account.
- Windows 10 or 11, with a graphics driver that supports OpenGL 3.3 or newer (any PC from the last decade).

The download contains Reborn's own files (the game data, `version.dll` and `RebornPlugin.dll`) plus two free graphics add-ons: **D2GL** (sharper, smoother graphics) and **SGD2FreeRes** (widescreen). It does not include any Blizzard game files, so you convert your own copy of the game to version 1.13c (step 2).

## First-time install

1. **Make a separate copy of the game.** Copy your whole Diablo II folder to a new folder, for example `C:\Diablo2Reborn`. Everything below happens in that copy, so your normal game stays untouched.

2. **Convert the copy to 1.13c.** The free, open-source [Slashdiablo launcher](https://github.com/nokka/slashdiablo-launcher) can do this:
   1. Run the launcher, click **Get started** and set the Diablo II directory to your Reborn copy from step 1.
   2. Set **Maphack version** and **HD mod version** to **none**.
   3. Click **Done**, then **Update now** and wait for it to finish.
   4. Close the launcher. Don't use its Play button for Reborn.
   5. In your Reborn folder, delete (or move into a subfolder) `SlashDiablo.dll`, `D2Template.dll` and `StormLib.dll`. These are Slashdiablo's own add-ons, not part of the game, and `SlashDiablo.dll` keeps switching your gateway back to "Slash Diablo".

3. **Extract the Reborn zip into your Reborn folder**, so that `version.dll`, `RebornPlugin.dll`, `glide3x.dll`, `SGD2FreeRes.dll`, `Play Reborn.bat` and a `data` folder all sit next to `Game.exe`. Say yes if Windows asks to replace files. `version.dll` is Reborn's file: it loads Reborn when the game starts, so there's no separate loader to run.

4. **Set the gateway.** Double-click `Reborn-Gateway.reg` and click **Yes**. Do this after step 2, because the launcher changes your gateway list.

5. **Bring your characters (optional, open play only).** 1.13c keeps characters in the `Save` folder inside your Reborn folder. To keep existing open play characters, copy the files from `C:\Users\<you>\Saved Games\Diablo II` into that `Save` folder. Keep a backup of the originals.

6. **Play.** Start the game with `Play Reborn.bat`. On the main menu, check the corner says **v 1.13**, click the gateway button and choose **Reborn**. Then:
   - **Closed realm** (characters saved on the server, every game is players 8): click the main **Battle.net** button, create an account and log in.
   - **Open play** (characters saved on your PC): click **Other Multiplayer > Open Battle.net**.

## Graphics and widescreen

- **Ctrl+O** in game opens the graphics settings (D2GL): window size, fullscreen, sharpening and other effects. Set the window size to your monitor's resolution for the sharpest picture.
- **Options > Video Options > Resolution** changes how much of the map you see: 640×480, 800×600, 856×480 or **1068×600** (widescreen).
- `Play Reborn.bat` starts the game with `-3dfx`, which turns these on. Always start Reborn with it.

## Updating to a new version

1. Delete the old `data` folder from your Reborn folder.
2. Extract the new zip the same way as above, **replacing every file** it asks about. Your graphics settings (`d2gl.ini`) are kept.
3. **Coming from Pre-Alpha v3 or older:** delete `RebornLoader.exe` and any shortcut to it. Start the game with `Play Reborn.bat` from now on.
4. Everyone in a game must have compatible versions. Compare `VERSION.txt` with the host if you get disconnected when joining.

## If something goes wrong

- **The game won't start, or the screen stays black:** update your graphics driver. If that doesn't help, edit `Play Reborn.bat`, change `-3dfx` to `-w` and start it again. That runs the game without the new graphics and widescreen, so you can still play.
- **No 1068×600 in Video Options:** `SGD2FreeRes.dll` is missing from your Reborn folder or did not load. `RebornProxy.log` says why; "error 126" means you need the Visual C++ Redistributable below.
- **"RebornPlugin.dll did not load" or "SGD2FreeRes.dll did not load":** install Microsoft's [Visual C++ Redistributable (x86)](https://aka.ms/vs/17/release/vc_redist.x86.exe).
- **"UNHANDLED EXCEPTION: ACCESS_VIOLATION (c0000005)":** on most PCs Reborn handles this by itself. If it still happens, turn off Data Execution Prevention for this one Game.exe: Windows Security > App & browser control > Exploit protection settings > Program settings > Add program to customize > Choose exact file path, pick `Game.exe` in your Reborn folder, then under **Data Execution Prevention (DEP)** tick **Override system settings** and switch it **Off**.
- **The gateway keeps showing "Slash Diablo":** `SlashDiablo.dll` is still in your Reborn folder. Delete it (step 2.5), then double-click `Reborn-Gateway.reg` again.
- **The game plays like plain 1.13c** (no purple uniques, no gold pickup, no Ctrl+click): `version.dll` is missing from your Reborn folder, likely removed by your antivirus. Restore it from the zip and add an exception for your Reborn folder.
- **Asking for help:** `RebornProxy.log` and `RebornPlugin.log` in your Reborn folder show what Reborn did at startup. Send them along on Discord.

## Hosting your own open play games

Joining games works out of the box. To **host** a game that others can join, forward TCP port 4000 on your router to your PC.

## Notes

- Closed realm characters are saved on the server; open play characters are saved on your own PC. They don't carry over between the two.
- Players on 1.13c and 1.14d can't join each other's games.
- To play plain 1.13c from your Reborn folder, move `version.dll` out of it.
- Reborn is a free fan project. **Never pay anyone for Reborn items.**

## Credits

- **D2GL** by Bayaraa: [github.com/bayaraa/d2gl](https://github.com/bayaraa/d2gl)
- **SGD2FreeRes** by Mir Drualga, licensed under the GNU AGPL v3, with Reborn approved for widescreen: [github.com/mir-diablo-ii-tools/SlashGaming-Diablo-II-Free-Resolution](https://github.com/mir-diablo-ii-tools/SlashGaming-Diablo-II-Free-Resolution)

Their license files ship in every Reborn download.
