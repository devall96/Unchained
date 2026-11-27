<p align="center"><img src="res/splash.png" alt="Unchained"></p>

**Unchained** brings *Whiplash* (original Xbox, 2003) to **Windows and Linux** as a native PC port. It is a **static recompilation**: the game's Xbox code is translated ahead of time into a native program, so no emulator runs the game. On top of that sits what a good PC release should have: your screen's full resolution, real widescreen and ultrawide, a HUD at the screen's edges, AMD FSR 1, smooth frame pacing with no shader stutter on later starts, button prompts for the controller in your hands, an in-game settings menu and a Configuration app that sets everything up from **your own copy of the game**.

<p align="center"><a href="https://recomplauncher.com/game/unchained"><picture><source media="(prefers-color-scheme: dark)" srcset="https://recomplauncher.com/assets/press/launcher/badge-light.svg"><img alt="Get it on RecompLauncher" src="https://recomplauncher.com/assets/press/launcher/badge-dark.svg" height="48"></picture></a></p>

**[⬇ Download Unchained](https://devall96.github.io/Unchained/)** · [All releases](https://github.com/devall96/Unchained/releases) · [Testers wanted](#-testers-wanted) · [Where it's at](#where-its-at) · [What it does](#what-it-does) · [Getting started](#getting-started) · [Steam Deck](#steam-deck) · [Known issues](#known-issues) · [Roadmap](#roadmap) · [How it was made](#how-it-was-made)

> [!CAUTION]
> **No game files are included, and none ever will be**: not in the code, the releases, the issues or the wiki. Unchained is made to be used with your own, legally obtained copy of *Whiplash* for the original Xbox (USA): its disc image or its extracted files. The game's code is recompiled on your PC, from your copy, the first time you start it. Please don't post disc images, game files, texture dumps or anything taken from them here.

> [!IMPORTANT]
> **Made with AI.** Every line of Unchained's own code, its changes to the recompiler's runtime, the tests, the art and this page were written or made by Claude, Anthropic's AI, through Claude Code. A human, [devall96](https://github.com/devall96), came up with the idea, directs it and plays every build, but no human reviews the code line by line. [Who did what](#who-did-what) has the details. If you don't want to run code written that way, don't run this. As with anything on the internet, you run it at your own risk.

> [!WARNING]
> **Early: version 0.1, tested on one PC.** The opening levels (the training lab and the lobby around it) have been played through on Windows and Linux; the rest of the game hasn't been played on Unchained yet. Everything so far has been tested on a single AMD desktop. That's why [testers are wanted](#-testers-wanted). Keep a copy of saves you care about (Unchained also backs them up by itself at every start).

> [!NOTE]
> **Not official.** Unchained is a fan project. It isn't made by, affiliated with or endorsed by Crystal Dynamics, Eidos, Square Enix, Embracer Group or Microsoft, or by the authors of the recompiler it's built on. Please [open an issue here](https://github.com/devall96/Unchained/issues) for Unchained problems.

## 🧪 Testers wanted

So far Unchained has run on exactly one computer: an AMD Ryzen 7 7800X3D with a Radeon RX 9070 XT, on Windows 11 and on Ubuntu 26.04. That says very little about how it does on yours, so if you own the game and have an evening, you'd help a lot. Hardware it has **never** seen:

- **NVIDIA graphics** (any generation) and **Intel graphics** (Arc and integrated). The new Vulkan renderer has only met AMD's drivers.
- **Steam Deck** and other PC handhelds (ROG Ally, Legion Go…). The Linux release *should* run on a Deck (see [Steam Deck](#steam-deck)), but nobody has tried it.
- **Laptops**, older or slower PCs, and **other Linux distros and desktops** (the AppImage has only reached the title screen in Ubuntu 24.04, Fedora and Arch containers on the same PC).
- **Controllers** other than an Xbox pad: DualSense, DualShock 4, Switch Pro, 8BitDo and generic pads.
- **Ultrawide** (21:9, 32:9), **16:10**, high refresh rate and **VRR** (G-Sync / FreeSync) screens, multi-monitor setups.

**How to help:**

1. [Download](https://github.com/devall96/Unchained/releases/latest) the Windows installer or the Linux AppImage, point it at your copy of the game and play.
2. Play a level, ideally one past the first few that nobody has reported yet, and note anything that looks, sounds or plays wrong.
3. [Open a bug report](https://github.com/devall96/Unchained/issues/new/choose). The form asks for:
   - your system: Windows version, or Linux distro and desktop (e.g. *Fedora 41, KDE Plasma 6, Wayland*), or *Steam Deck, SteamOS 3.x*;
   - your GPU and driver version, CPU, and screen size;
   - the Unchained version (on the Configuration app's About page);
   - where it happened (level and place, menu or cutscene), what you did, what happened and what you expected;
   - a screenshot (**F12**) or a short clip if it's visual, and the **F10** overlay if it's about smoothness;
   - the newest log: `logs\unchained_NNN.log` in Unchained's folder on Windows, `~/.local/share/Unchained/logs/` on Linux, and for a crash the newest file in `CrashDumps\`.

"It worked fine on my setup" reports are just as useful, so please send those too: knowing a GPU or a handheld is fine is half of what testing is for. And if you can code, [contributions](CONTRIBUTING.md) are very welcome; a bit of help would go a long way.

## Screenshots

<p align="center"><img src="docs/images/game-lobby.jpg" alt="The lobby at 2560x1440 with the wider 16:9 view and the HUD at the screen's top corner" width="900"></p>
<p align="center"><sub>The lobby at 1440p in release 0.1: the game's own view widened to 16:9, the HUD out at the screen's corner.</sub></p>

| | |
| --- | --- |
| ![On a walkway above the lobby, the floors below drawn at 1440p](docs/images/game-walkway.jpg) | ![A dim balcony in the lobby, lit the way the original Xbox version lights it](docs/images/game-balcony.jpg) |

The game graphics in these screenshots come from a legally obtained copy of the game, as they do on your PC. They belong to their owners and aren't part of Unchained.

The Configuration app, which sets the game up from your own copy and holds every setting:

| | |
| --- | --- |
| ![The Play page: graphics presets, OG Graphics included, and the window mode](docs/images/config-play.png) | ![The Display page: window, resolution, wider view, HUD at the edges, field of view, VSync](docs/images/config-display.png) |
| ![The Graphics page: renderer, render scale, FSR 1, clean edges, filtering, shadows, draw distance, colour grading](docs/images/config-graphics.png) | ![The Controls page: camera speed, inversion, vibration and button prompts](docs/images/config-controls.png) |
| ![The Game Files page: pick your disc image or extracted folder](docs/images/config-files.png) | ![The Sound & Saves page: sound output, save backups and save profiles](docs/images/config-saves.png) |

<sub>Captured from the 0.1 release on a fresh install, before any game files were added.</sub>

## Where it's at

Unchained started on **Sunday 15 November 2026** from the recompiler's game template. Two days later it plays the opening levels with sound, saves and controls on Windows and Linux, and about two thirds of the PC features on its list are in.

PC features from [docs/TODO.md](docs/TODO.md) (started items count half; the full status is in [docs/STATUS.md](docs/STATUS.md)):

| Area | Progress | Done |
|---|---|---|
| Core | `███████████████░░░░░` | 75% (3 of 4) |
| Platforms and input | `█████████████░░░░░░░` | 67% (4 of 6) |
| Performance | `███████████████░░░░░` | 75% (6 of 8) |
| Graphics | `██████████████████░░` | 92% (5.5 of 6) |
| Player features | `████████████░░░░░░░░` | 58% (7 of 12) |
| Adapted to Whiplash | `███████░░░░░░░░░░░░░` | 36% (4 of 11) |
| Launcher, files and theme | `██████████████████░░` | 88% (3.5 of 4) |
| **All** | `█████████████░░░░░░░` | **65%** (33 of 51) |

| | Status |
|---|---|
| Boots, menus, saves | ✅ Works |
| Opening levels (training lab, lobby) | ✅ Played through on Windows and Linux |
| The rest of the game | ❓ Not played on Unchained yet: [please help](#-testers-wanted) |
| Music and sound effects | ✅ Work |
| Spoken dialogue | ⚠️ Some lines don't play yet (see [Known issues](#known-issues)) |
| Windows (Vulkan, with Direct3D 12 as the fallback) | ✅ Tested on one AMD PC |
| Linux (one AppImage, Vulkan) | ✅ Tested on Ubuntu 26.04; reaches the title in Ubuntu 24.04, Fedora and Arch containers |
| Steam Deck | ❓ Should work, untested |
| macOS | 🗺️ [On the roadmap](#macos-port) |

## What it does

**The game, natively**
- The whole Xbox game recompiled to native code: 25,805 functions, built on your own PC from your own copy the first time you start it (about 10 to 40 seconds with the bundled compiler). No emulator, no game code in the download.
- Only the supported release starts, so you never chase a bug that comes from a different disc. Another release is refused with a message saying what was found.
- Your saves live on a virtual Xbox hard disk in Unchained's folder, like the console's.

**Picture**
- **Your screen's resolution.** The game renders at the size it's shown (never below the console's own), and past 100% it supersamples.
- **Real widescreen and ultrawide.** Whiplash had no widescreen mode, so Unchained widens the game's own camera: 16:9, 16:10, 21:9 and up to 32:9 show *more* at the sides instead of stretching, and the game draws what the wider view shows (no pop-in at the edges, even with a wider field of view). 4:3 with bars, and the console's own stretch, are options.
- **AMD FSR 1** upscaling when rendering below your screen's size, with **RCAS sharpening**.
- **Sharper shadows** (a 2048 shadow map instead of the console's 256), **16x anisotropic filtering**, a **field of view** setting and a **draw distance** setting.
- **Clean menu and HUD edges.** Flat 2D art (the font, menu and dialog frames, the HUD's green terminal icons) is redrawn at 4x with clean edges, while painted art, gradients and TV static are left as they were.
- **Colour grading:** exposure, contrast, saturation, temperature and tint.
- **Graphics presets:** **OG Graphics** (the console as it was: its own 640x480 at 4:3, every setting at the console's default, the fixes kept), Original, Low, High and Max.
- **Character shadows** can be switched off.

**HUD and prompts**
- **The HUD at the screen's edges** like a modern game, at any aspect ratio, with menus and centred text kept centred. A slider moves it anywhere from where the console put it to the edges.
- **Button prompts for the controller in your hands**, switching live: today's Xbox pad, PlayStation symbols or Nintendo letters by position. The console's own glyphs are an option too. The pop-up icons at the top of the screen follow along.

**Smoothness**
- **VSync modes:** off, on, adaptive (a tear instead of a held frame when late), fast (no wait, no tear) and VRR for G-Sync and FreeSync screens.
- **No shader stutter after the first start.** Compiled shaders are kept between runs, and every graphics pipeline the game has used is made ahead in the background at start. The hitches left on a warm start are the game's own level loads at loading-screen cuts.
- **A Vulkan renderer on both systems**, with Direct3D 12 as the automatic fallback on Windows. In frame-time tests on the test PC, Vulkan's 1% lows were equal to or better than D3D12's in every scene, and it had no frame over 100 ms on a cold start.
- **Performance overlay (F10):** fps, a frame-time graph, 1% and 0.1% lows, hitches over 25/33/50/100 ms, and the render size.
- The game keeps real time with no frame cap (checked in the intro and menus); the cap stays at 60 by default until gameplay above 60 is checked.

**In-game menu**
- **F1**, or **Back + Start** on a controller, opens every option the Configuration app has, over the game, in the same look. The game gets none of your input while it's open, and your changes are saved when you close it.

**Controls**
- **Any controller** through SDL3, read by button position, with camera speed, inverted camera axes and vibration strength.

**Saves and files**
- **Save backups at every start** (the last 5 kept), **save profiles** (named sets of saves, each on its own virtual disk) and a **custom save folder**.
- Saves, settings, logs and caches stay in one data folder, which `UNCHAINED_DATA_ROOT` can move anywhere; on Linux a `portable.txt` beside the AppImage keeps them in its folder.
- `--game <disc image or folder>` plays your copy where it is, without copying it, for shortcuts, scripts and launchers.

**Configuration app**
- A lab-terminal look of its own: dark teal, green terminal frames and big slanted headings, drawn by Unchained with bundled open fonts and no game art. The same app on Windows and Linux.
- **Setup:** pick your disc image or game folder; it checks the release, copies the files beside Unchained (your originals aren't touched), builds the game's code with its progress on the same page, then **PLAY**.
- Pages for play, display, graphics, controls, sound and saves, game files and about. After setup, `Unchained.exe` starts straight into the game; `Unchained.exe --configure` opens the app again.
- The first-start build window matches the same look, shows a failed build's reason in the window, sizes itself for 150% to 300% display scaling, and goes into the game by itself when it's done.

**Extras**
- **Screenshots (F12)** as PNGs in `screenshots\`.
- **Accessibility:** colour vision filters (protanopia, deuteranopia, tritanopia, with a strength slider) and a HUD-off switch.
- **Texture packs:** dump the game's textures, edit or upscale them, and Unchained draws yours instead, picked up while the game runs. See [docs/MODS.md](docs/MODS.md).

Every setting, with its default, is in [docs/SETTINGS.md](docs/SETTINGS.md).

### The fixes that made it run

Whiplash turned out to be an unusual Xbox game, and the recompiler's runtime couldn't run it as it came. These are the main fixes, all made for Unchained:

- **About 140 library functions named by hand.** The recompiler's signature files matched only 75 of the 248 library functions the game uses, because Whiplash's Direct3D was a different build from the games those signatures came from. The missing Direct3D and DirectSound pieces were found one boot at a time, seventeen boots on the first day, each naming whatever the last crash pointed at.
- **A push buffer interpreter.** Whiplash mostly skips the Direct3D API and writes the Xbox GPU's raw command stream itself. No version of the runtime, and no fork of it, could run that, so Unchained's runtime got an interpreter for those commands: vertex programs, vertex formats, textures, pixel combiners and every draw type the game uses. That is what made the intro, the title and then the whole game appear.
- **The strobe.** The game asks for two presents per frame, so every other picture was empty and the screen flashed between the game's colour and black. Fixed so only a real frame is shown.
- **Characters, shadows and cutscenes:** the characters' vertex data read correctly (they were scraps before), shadows drawn into their own texture with the render targets the game sets itself, the cutscene and intro letterbox kept, culling taken from what the game pushes, and the hyper mode's texture stages.
- **Saves:** the console's disc check now passes, so the game mounts its hard disk instead of reporting "a hard disk error".
- **A sweep for missed pieces:** library functions the game calls but nobody had mapped (one misnamed), state the renderer took from the wrong place, and frame buffer addresses (the game was handed the same address for the front and back buffers).
- **Widescreen pop-in:** with a wider field of view, lights, plants and props vanished near the screen's edges, because the game decided what to draw with its own 60° view. It now uses the same view as the picture.

## Getting started

**You need:** your own copy of *Whiplash* for the original Xbox (USA), as a disc image (`.iso`) or its extracted files, and about 5 GB of free disk space.

### Windows

**Needs:** Windows 10 or 11 (64-bit) and a graphics card with Vulkan 1.3 or Direct3D 12 (any AMD, NVIDIA or Intel card from the last several years). Nothing else to install: the compiler and the C++ runtime come with Unchained.

1. Download **`Unchained-0.1.2-Windows-x64-Setup.exe`** (55 MB) from the [latest release](https://github.com/devall96/Unchained/releases/latest) and run it. It installs for your user only (no admin), to `C:\Unchained` by default; avoid *Program Files*, since Unchained keeps its data beside itself. Prefer no installer? `Unchained-0.1.2-Windows-x64.zip` (83 MB) works the same: extract it to a folder you can write to.
2. **About the Windows warning:** Unchained isn't code-signed yet, so SmartScreen may say *"Windows protected your PC"*. Click **More info → Run anyway**.
3. Start **Unchained** (it opens the Configuration app the first time). On **GAME FILES**, choose your disc image or game folder. It checks the release, copies the files and builds the game's code once, with its progress on the same page.
4. Press **PLAY**. From then on, Unchained starts straight into the game.

### Linux

**Needs:** a 64-bit distro from about 2022 on (glibc 2.35 or newer: Ubuntu 22.04, Debian 12, Fedora 36, SteamOS 3 and later) and a **Vulkan 1.3 driver** (Mesa for AMD and Intel, or NVIDIA's own driver). The compiler is inside the AppImage, so there's nothing else to install.

1. Download **`Unchained-0.1.2-Linux-x86_64.AppImage`** (148 MB, one file with everything inside) from the [latest release](https://github.com/devall96/Unchained/releases/latest).
2. Make it executable (right-click → Properties → *Allow executing file as program*, or `chmod +x Unchained-*.AppImage`) and run it. It adds **Unchained** and **Unchained Configuration** to your applications menu.
3. Choose your disc image or game folder in the Configuration app, then press **PLAY**, as on Windows.

If your system has no FUSE, run it with `APPIMAGE_EXTRACT_AND_RUN=1`. Without a Vulkan 1.3 driver, Unchained tells you which one to install. Your data lives in `~/.local/share/Unchained`.

### Keys

| Key | What it does |
|---|---|
| **F1** (or Back + Start) | The in-game menu |
| **F10** | The performance overlay |
| **F12** | A screenshot |

Unchained is played with a controller for now; full keyboard and mouse play is on the [roadmap](#roadmap).

### Which copy of the game works

Unchained works with **one version of the game: *Whiplash* for the original Xbox, the North American (USA) release.** If you own the Xbox disc from North America, it's the right one; other regions' discs aren't supported yet.

- **What to give it:** a disc image (`.iso`) made from your disc, or a folder with the game's files copied off it. Both work.
- **Use an untouched copy.** Some tools that make smaller disc images change one small part of the game's main file along the way. Unchained notices that and asks for an unchanged copy, so make your image with a tool that copies the disc as it is.
- **It checks for you.** When you choose your files, the setup looks at the game's main file and tells you straight away if it's a different version or has been changed, before anything is copied.
- **Nothing else is needed:** no console files, keys or BIOS. The game is in English only (text and voices), as the disc is.

## Steam Deck

Unchained **should** run on a Steam Deck: SteamOS 3 is newer than the AppImage needs, the Deck's GPU has a Vulkan 1.3 driver, and its controls appear to the game as a controller. But I don't have a Deck, so **nobody has tried it yet**. If you have one, a report would be very welcome. What should work:

1. In **Desktop Mode**, download the AppImage, make it executable (Properties → *Is executable*) and run it once to set up your game files. It adds itself to the applications menu.
2. To play from **Game Mode**, add it in Steam with **Add a Non-Steam Game** (pick *Unchained* from the list), then start it from your library.
3. The Deck's 16:10 screen gets the widened view. If it runs heavy, try the **Low** preset or a lower render scale with FSR 1.

A handheld preset (30/40/45/60 fps targets at the screen's own size) and a built-in **Add to Steam** button are on the [roadmap](#roadmap).

## Known issues

- **Spoken dialogue:** many of the partner character's lines don't play yet (the main character's voice, the sound effects and the music do). The first sure example is the fire machine scene in the training lab.
- **Light beams flicker:** the beams wall lamps throw straight up vanish and come back at some distances in the lab. The investigation so far is written up in [docs/LIGHT_BEAM_FLICKER.md](docs/LIGHT_BEAM_FLICKER.md), for anyone who wants to pick it up.
- **Hyper mode** shows no trail effect yet (the game goes into hyper mode correctly).
- **Only the opening levels** have been played through. Later levels are untested.
- **Controller only for now.** Keyboard and mouse play is on the [roadmap](#roadmap).
- **Above 60 fps** is only checked in the intro and menus, so the cap stays at 60 by default.
- **Draw distance** doesn't reach the gameplay camera with the widened view yet (it does at 4:3).
- **The title screen in widescreen** shows a white strip at each side, past the edge of its sky.
- **The very first start** compiles shaders as it goes, so the first loading-screen cuts hitch once; from the second start on they're gone.
- **The picture is darker and greener in some rooms than you may remember.** That's the original Xbox version's own lighting: the levels ask for it, and Xbox footage shows the same. The PS2 version lights characters more brightly, which is where the brighter memory usually comes from. An optional brighter look is on the roadmap.
- **Not code-signed** yet on Windows, so SmartScreen shows a warning on first run.

## Roadmap

Roughly in order. Everything is tracked item by item in [docs/TODO.md](docs/TODO.md).

**Next: finishing the game**
- **A full playthrough**, level by level, with fixes for whatever breaks. This is where testers help most.
- **Every voice line playing**, including the partner character's.
- **The hyper mode trail**, and **the light beam flicker** in the lab (what's known so far is in [docs/LIGHT_BEAM_FLICKER.md](docs/LIGHT_BEAM_FLICKER.md)).
- **The camera's feel** in play, checked against the console.
- **Above 60 fps in gameplay:** physics and cutscenes checked at high frame rates, then the default cap raised.
- **Draw distance** in widescreen, together with the game's own distance culling and level of detail.

**Then: more PC features**
- **Steam Deck and handhelds:** a handheld preset (30/40/45/60 fps at the screen's own size) and an **Add to Steam** button.
- **One-click updates** from the Configuration app.
- **Keyboard and mouse:** every action rebindable to keys and mouse buttons, a mouse camera, and keyboard key caps in the button prompts.
- **HDR10** output, **colour LUTs** (`.cube` colour tables) and a **photo mode** with a free camera.
- **An optional brighter, PS2-style character lighting**, as a choice beside the Xbox look.
- **Accessibility and assists:** invincibility, damage scaling, text speed.
- **Level select**, and **effect toggles** for the game's own effects (trails, fog, glow, screen effects).
- **Translated menus** for Unchained's own screens, and **Discord Rich Presence** (off by default).
- A faster release build (profile-guided optimisation and ThinLTO).
- Modern upscalers and frame generation (FSR 3/4, DLSS), which need motion vectors a 2003 game doesn't make: later, from depth and camera reprojection.

**macOS port**

A native macOS version is planned. Much of the groundwork is already there from the Linux port:
- **Graphics:** the Vulkan renderer can run on Apple's Metal through MoltenVK, rather than a whole new renderer.
- **Window, input and sound** already go through SDL3, as on Linux.
- **The game's code** is recompiled into portable C++ (even the Xbox's x87 floating point is done in plain C++), so a native Apple Silicon build looks possible, with Rosetta 2 as the fallback.
- **Still to do:** the way the Xbox's memory is mapped, the first-start code build with a bundled compiler for macOS, the Configuration app on macOS, and an app bundle that is signed and notarised so macOS lets it open.

**Giving back**
- The general runtime work (the push buffer interpreter, the rendering fixes, the Vulkan renderer, the build window) is meant to go back to the recompiler upstream as pull requests, so other Xbox games written the same way can run too.
- **Decompilation over time:** the game's own systems (input, camera, rendering glue, saves) rewritten as readable C++ one at a time, replacing their recompiled versions.

## How it was made

It started with a question in early November: could *Whiplash* get a proper PC port? A search found nothing anywhere: no port, no decompilation, no tools for its files. The original Xbox release was chosen over the PS2 one because the Xbox's x86 code can be recompiled with the [Xbox XBE Recomp](https://github.com/TGP482/XboxXBERecomp) toolkit. Work started on **Sunday 15 November 2026 at 04:13**:

| When | What |
| --- | --- |
| Sun 15 Nov, 04:13 | The project starts from the recompiler's game template: 25,805 functions turned into C++. |
| Sun 16:47 | It's named **Unchained**: a play on the chain, and on freeing the game from the Xbox. |
| Sun 17:41 | First frames on screen after seventeen boots; the strobe fixed at 17:59. |
| Sun 19:03 | The push buffer interpreter: the first shape, then the intro and the title logo. |
| Sun 19:35 – 19:53 | Controls, saves, and the characters appear. |
| Mon 16 Nov, 01:00 – 03:29 | Shadows, cutscene bars, hyper mode, a half-hour play session, a sweep for missed pieces. |
| Mon 04:04 – 09:59 | The PC port: full resolution and widescreen, FSR 1, the test suite, VSync modes, the shader cache, the HUD at the edges, presets, accessibility, the overlay, the Configuration app and setup, button prompts, clean UI edges. |
| Mon evening | The in-game menu, the release preparation, the single-exe installer and the themed build window. |
| Tue 17 Nov, early | The widescreen pop-in fixed; the **Linux port**: native Vulkan on both systems, one AppImage, every window the same on Windows and Linux; Vulkan the default; OG Graphics. |

In numbers: about 120 commits in Unchained and 65 in its runtime, about 15,000 lines added to the runtime (the push buffer interpreter, the fixes and the Vulkan renderer) and about 5,000 in Unchained's own code, plus about 140 functions named by hand.

**Testing** is done the way players see it: every build is played on screen, frames are captured from the renderer itself and compared against reference footage of the original, and performance is measured frame by frame (1% and 0.1% lows, hitches, stutter, pacing), never by an average fps. An automated suite replays scripted and recorded play sessions on both systems and both renderers.

The bar for features comes from the projects I contribute to: what a good PC recomp release should have, applied to an original Xbox game from 2003.

## Building it

The game's code is never in this repository: the build recompiles your own `default.xbe`.

**Windows:** Visual Studio 2022 or newer with **Desktop development with C++**, **C++ Clang tools for Windows** and **C++ CMake tools for Windows**.

1. `git clone --recursive https://github.com/devall96/Unchained.git`
2. Put the game's files in `assets/`: `default.xbe`, `Game.ini`, `Xbox.rkv`, `Xbox.r01`–`Xbox.r09`, `map/`, `movies/`, `objects/`, `newgame.dat`, `xbreverb.bin`.
3. Run `build.bat` (type `.\build.bat` in PowerShell). It checks the XBE, names the library functions, recompiles and builds. The first build takes 30 to 90 minutes.

`release.bat` lays out the release, makes the zip and the installer (`tools/installer`).

**Linux:** clang, CMake, Ninja and the Vulkan and SDL3 build dependencies, then `cmake --preset linux-relwithdebinfo` and a build of `Unchained`. The release AppImage is made by `tools/appimage/release.sh`, in an Ubuntu 22.04 container with LLVM's own clang and lld bundled.

`tools/tests/run_suite.py` is the frame-time suite (per-present times, 1% and 0.1% lows, hitches, stutter), on both systems. Contributions go to the `test` branch: see [CONTRIBUTING.md](CONTRIBUTING.md).

## Who did what

- **[devall96](https://github.com/devall96)**: the idea, the direction, every decision, and playing every build, with a recorded play session that every automated test still replays.
- **Claude** (Anthropic), through Claude Code: Unchained's code, the push buffer interpreter and the other runtime changes, the Vulkan renderer and the Linux port, the tests, the Configuration app and its art, and the documentation.

## Credits

- **[Xbox XBE Recomp](https://github.com/TGP482/XboxXBERecomp)** (MIT): the recompiler and runtime Unchained is built on. Unchained's changes to it (the push buffer interpreter, the rendering fixes, the Vulkan renderer and the Linux port) are on the `unchained` branch of [devall96/XboxXBERecomp](https://github.com/devall96/XboxXBERecomp/tree/unchained), which `sdk/` points to.
- [XenonRecomp](https://github.com/hedge-dev/XenonRecomp) for the overridable function layout and instruction hooks.
- [AMD FidelityFX Super Resolution 1](https://github.com/GPUOpen-Effects/FidelityFX-FSR) (MIT).
- [SDL 3](https://github.com/libsdl-org/SDL), [Dear ImGui](https://github.com/ocornut/imgui), [toml++](https://github.com/marzer/tomlplusplus), [Zydis](https://github.com/zyantific/zydis) and Zycore, [volk](https://github.com/zeux/volk), [Vulkan Memory Allocator](https://github.com/GPUOpen-LibrariesAndSDKs/VulkanMemoryAllocator), [Vulkan-Headers](https://github.com/KhronosGroup/Vulkan-Headers), [glslang](https://github.com/KhronosGroup/glslang) and [stb_truetype](https://github.com/nothings/stb).
- [LLVM](https://llvm.org) (clang and lld), bundled to build the game's code on your PC.
- Fonts (SIL Open Font License): [Barlow Semi Condensed](https://fonts.google.com/specimen/Barlow+Semi+Condensed), [Anton](https://fonts.google.com/specimen/Anton) and [Cascadia Mono](https://github.com/microsoft/cascadia-code).
- Full licences: `THIRD_PARTY.txt` in every release.

*Whiplash* and its names and characters belong to their owners. Unchained is not affiliated with Crystal Dynamics, Eidos, Square Enix, Embracer Group or Microsoft.

## License

Unchained's own code is [MIT](LICENSE). The licence covers Unchained's code only, never the game.

---

<p align="center"><a href="https://ko-fi.com/devall96"><img src="https://img.shields.io/badge/Support_me_on-Ko--fi-FF5E5B?logo=ko-fi&logoColor=white&style=for-the-badge" alt="Support me on Ko-fi"></a></p>
