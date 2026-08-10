# Installation Guide

This guide explains how to install and configure the components used by the **Windows Liquid Glass Theme**.

The project combines Windhawk mods, YASB, Spicetify, Fluent Flyouts, and additional Windows customization tools to create a consistent translucent and Liquid Glass desktop experience.

---

## Table of Contents

1. [Requirements](#1-requirements)
2. [Before Installation](#2-before-installation)
3. [Windhawk](#3-windhawk)
4. [Translucent Windows](#4-translucent-windows)
5. [Taskbar Styler](#5-windows-11-taskbar-styler)
6. [Taskbar Height and Icon Size](#6-taskbar-height-and-icon-size)
7. [Taskbar Dock Animation](#7-taskbar-dock-animation)
8. [Start Menu Styler](#8-windows-11-start-menu-styler)
9. [File Explorer Styler](#9-windows-11-file-explorer-styler)
10. [YASB](#10-yasb)
11. [CEF Spotify Tweaks](#11-cef-spotify-tweaks)
12. [Spicetify](#12-spicetify)
13. [Fluent Flyouts](#13-fluent-flyouts)
14. [Applying Updates](#14-applying-updates)
15. [Troubleshooting](#15-troubleshooting)
16. [Restoring Your Original Configuration](#16-restoring-your-original-configuration)

---

# 1. Requirements

## Operating System

This project is designed primarily for:

* Windows 11
* Dark mode recommended
* A Windows build compatible with the installed Windhawk mods

Compatibility may change after Windows updates because the styling targets used by Windows UI components can change.

---

## Required Software

| Component                 | Software                        |
| ------------------------- | ------------------------------- |
| Windows UI customization  | Windhawk                        |
| Taskbar                   | Windows 11 Taskbar Styler       |
| Start Menu                | Windows 11 Start Menu Styler    |
| File Explorer             | Windows 11 File Explorer Styler |
| System transparency       | Translucent Windows             |
| Taskbar sizing            | Taskbar height and icon size    |
| Taskbar animation         | Taskbar Dock Animation          |
| Custom top bar            | YASB                            |
| Spotify customization     | Spicetify                       |
| Spotify CEF customization | CEF Spotify Tweaks              |
| System/media flyouts      | Fluent Flyouts                  |


## Recommended Installation Order

For the closest result to the project preview, install the components in this order:

### Core Windows UI

1. Install [Windhawk](https://windhawk.net/)
2. Install Translucent Windows
3. Install Windows 11 Taskbar Styler
4. Install Taskbar Height and Icon Size
5. Install Windows 11 Start Menu Styler
6. Install Windows 11 File Explorer Styler

### Additional Windows Components

7. Install Taskbar Dock Animation
8. Install Fluent Flyouts

### Custom Top Bar

9. Install [YASB](https://github.com/amnweb/yasb)
10. Install the [JetBrains Mono Nerd Font](JetBrainsMonoNerdFontPropo-Regular.ttf)
11. Apply `config.yaml`
12. Apply `styles.css`

### Spotify

13. Install [Spotify](https://download.scdn.co/SpotifySetup.exe)
14. Install [Spicetify](https://spicetify.app/docs/getting-started)
15. Apply the Liquid Glass Spotify files
16. Install CEF Spotify Tweaks
17. Apply the CEF configuration


---

# 2. Before Installation

## 1. Create a Backup

Before applying any Windhawk configuration, make a backup of your existing settings.

This repository contains customized configurations intended for this specific Liquid Glass setup.

Do not overwrite your existing configuration if you want to preserve your current Windows customization.

---

## 2. Close Applications When Required

Before modifying Spotify:

1. Close Spotify completely.
2. Open Task Manager.
3. Confirm that Spotify is no longer running.
4. Apply the Spicetify configuration.
5. Restart Spotify.

For Windows shell modifications, restart the affected application or restart Windows if a visual change does not appear immediately.

---

# 3. Windhawk

Windhawk is the main platform used for the Windows UI modifications in this project.

Install Windhawk before installing the Windhawk-based components.

## Download

Use the official [Windhawk](https://windhawk.net/) website.

After installation:

1. Launch Windhawk.
2. Open **Mods**.
3. Search for the required mod.
4. Install the mod.
   - CEF/Spotify Tweaks
   - Taskbar Dock Animation
   - Taskbar height and icon size
   - Taskbar Volume Control
   - Translucent Windows
   - Windows 11 File Explorer Styler
   - Windows 11 Notificaton Center Styler
   - Windows 11 Start Menu Styler
   - Windows 11 Taskbar Styler
5. Open the mod's **Settings**.
6. Switch to the appropriate configuration/textual mode when required.
7. Paste the configuration from this repository.
8. Save the settings.
9. Reload the mod.

The official Windows 11 Taskbar Styler guide follows the same general process: install Windhawk, open Mods, install Windows 11 Taskbar Styler, and configure it from the Settings tab.

---

# 4. Translucent Windows

Install the `Translucent Windows` from Windhawk application.

## Installation

1. Open Windhawk.
2. Open **Mods**.
3. Search for **Translucent Windows**.
4. Install the mod.
5. Open **Settings**.
6. Select **Textual mode**.
7. Open:

```text
configs/Translucent Windows/translucent-windows-styler.yaml
```

8. Copy the configuration.
9. Paste it into the Windhawk configuration editor.
10. Save the configuration.
11. Restart/reload the mod.

This configuration provides the system-level translucent/acrylic effect used by the overall theme.

### Spotify Exception

The configuration also contains a Spotify-specific rule.

This is intentional because Spotify has its own transparency and glass styling in:

```text
spotify/
├── color.ini
└── user.css
```

Do not remove the Spotify rule unless you want Spotify to inherit the general Windows transparency behavior.

---

# 5. Windows 11 Taskbar Styler

Install:

```text
Windows 11 Taskbar Styler
```

Repository configuration:

```text
configs/
└── Windows-11-Taskbar-Styler/
    └── taskbar-styler.yaml
```

## Installation

1. Open Windhawk.
2. Open **Mods**.
3. Search for **Windows 11 Taskbar Styler**.
4. Install the mod.
5. Open **Settings**.
6. Select **Textual mode**.
7. Open:

```text
configs/Windows-11-Taskbar-Styler/taskbar-styler.yaml
```

8. Copy the configuration.
9. Paste it into the Windhawk configuration editor.
10. Save the configuration.
11. Restart/reload the mod.

## What it controls

The configuration controls:

* Taskbar positioning
* Taskbar margins
* Rounded corners
* Taskbar border
* Background transparency
* Task item glass
* System tray glass
* Task button spacing
* Running indicators

The current configuration uses the `Fluid` theme identifier.

---

# 6. Taskbar Height and Icon Size

## Installation
 
1. Open Windhawk.
2. Open **Mods**.
3. Search for **Taskbar height and icon size**.
4. Install the mod.
5. Open **Settings**.
6. Select **Textual mode**.
7. Open:

```text
configs/Taskbar-Height-and-Icon-Size/taskbar-icon-size.yaml
```

8. Copy the configuration.
9. Paste it into the Windhawk configuration editor.
10. Save the configuration.
11. Restart/reload the mod.

### Important

Taskbar Styler and Taskbar Height and Icon Size work together.

If you change the taskbar height, you may need to adjust:

* Taskbar margins
* Task button margins
* System tray margins
* YASB alignment
* Dock animation spacing

---

# 7. Taskbar Dock Animation

## Installation

1. Open Windhawk.
2. Open **Mods**.
3. Search for **Taskbar Dock Animation**.
4. Install the mod.
5. Open **Settings**.
6. Select **Textual mode**.
7. Open:

```text
configs/Taskbar-Dock-Animation/taskbar-dock-animation.yaml
```

8. Copy the configuration.
9. Paste it into the Windhawk configuration editor.
10. Save the configuration.
11. Restart/reload the mod.

If you want the standard Liquid Glass appearance without additional animation, you can skip this component.

---

# 8. Windows 11 Start Menu Styler

## Installation

1. Open Windhawk.
2. Open **Mods**.
3. Search for **Windows 11 Start Menu Styler**.
4. Install the mod.
5. Open **Settings**.
6. Select **Textual mode**.
7. Open:

```text
configs/Windows-11-Start-Menu-Styler/start-menu-styler.yaml
```

8. Copy the configuration.
9. Paste it into the Windhawk configuration editor.
10. Save the configuration.
11. Restart/reload the mod.

## Current customization

The configuration includes:

* Liquid Glass background
* Blur
* Transparent elements
* Glass borders
* Pinned application layout
* Recommended section spacing
* All Apps positioning
* Start Menu width
* Start Menu height
* Search window customization

Current Start Menu dimensions are:

```text
Width: 800 px
Height: 600 px
```

---

# 9. Windows 11 File Explorer Styler

## Installation

1. Open Windhawk.
2. Open **Mods**.
3. Search for **Windows 11 File Explorer Styler**.
4. Install the mod.
5. Open **Settings**.
6. Select **Textual mode**.
7. Open:

```text
configs/Windows-11-File-Explorer-Styler/file-explorer-styler.yaml
```

8. Copy the configuration.
9. Paste it into the Windhawk configuration editor.
10. Save the configuration.
11. Restart/reload the mod.

## Current customization

The configuration styles:

* Explorer background
* Navigation bar
* Main/details area
* Thumbnail area
* Command bar
* Borders
* Corner radius
* Blur
* Transparency

The configuration uses:

```text
backgroundTranslucentEffectRegion: entireWindow
```

so the translucent effect is intended to cover the Explorer window.

---

# 10. YASB

YASB is used as the custom Liquid Glass top bar.

YASB is a highly configurable Windows status bar and provides Windows 10/11 installers for x64 and ARM64 systems. The official documentation also recommends Nerd Fonts for custom themes.

## Download

Install [YASB](https://github.com/amnweb/yasb) using its [official release](https://github.com/amnweb/yasb/releases/tag/v2.0.6) or [installation documentation](https://github.com/amnweb/yasb/wiki/Installation).

Repository:

```text
configs/
└── YASB/
    ├── config.yaml
    └── styles.css
```

## Font

The project uses: `JetBrainsMonoNerdFontPropo-Regular.ttf`

Install the font from Repo:
```text
assets/
└── fonts/
    └── JetBrainsMonoNerdFontPropo-Regular.ttf
```

Install the font before launching the final configuration if icons or text appear incorrectly.

## Installation

1. Install YASB.
2. Start YASB once.
3. Close YASB if necessary.
4. Locate the YASB configuration directory. Default location `%AppData\spicetify\Themes`.
5. Back up the existing configuration.
6. Copy this project's `config.yaml`.
7. Copy this project's `styles.css`.
8. Install the included font if it is not already installed.
9. Start YASB again.


## YASB Styling

The included CSS controls:

* Top bar transparency
* Widget spacing
* Rounded widget containers
* Colors
* Fonts
* Workspace indicators
* Weather
* GitHub
* System widgets
* Power menu
* Calendar
* Wallpaper gallery
* Taskbar widgets

---


# 11. CEF Spotify Tweaks

## Installation

1. Open Windhawk.
2. Open **Mods**.
3. Search for **Windows 11 File Explorer Styler**.
4. Install the mod.
5. Open **Settings**.
6. Select **Textual mode**.
7. Open:

```text
configs/CEF-Spotify-Tweaks/Config.yaml
```

8. Copy the configuration.
9. Paste it into the Windhawk configuration editor.
10. Save the configuration.
11. Restart/reload the mod.

Install the corresponding CEF Spotify Tweaks component, then apply the configuration from the repository.

---

# 12. Spicetify

Spicetify is used to customize the Spotify desktop client.

The official Spicetify [documentation](https://spicetify.app/docs/getting-started) provides Windows installation through PowerShell, Winget, Scoop, and Chocolatey.

## Install Spotify First

Install the official [Spotify desktop client](https://download.scdn.co/SpotifySetup.exe) and log in.

Don't use Microsoft version. Spicetify won't work on Microsoft version

For a fresh installation, open Spotify and allow it to initialize before running Spicetify.

---

## Install Spicetify

Use the official Spicetify installation method.

Windows PowerShell installation:

```powershell
iwr -useb https://raw.githubusercontent.com/spicetify/cli/main/install.ps1 | iex
```

Alternatively:

```powershell
winget install Spicetify.Spicetify
```

---

## Verify Installation

Run:

```powershell
spicetify -v
```

Then:

```powershell
spicetify config current_theme
```

The expected theme configuration for this project is:

```text
marketplace
```

---

## Spotify Files

The repository contains:

```text
spotify/
├── color.ini
└── user.css
```

### color.ini

This contains the Liquid Glass color palette.

### user.css

This contains the main visual customization:

* Transparent structural layers
* Glass top bar
* Glass left sidebar
* Glass right sidebar
* Glass middle content
* Glass bottom player
* Transparent action/filter bar
* Rounded cards
* Glass borders
* Card spacing
* Recents spacing
* Removal of unwanted circular overlays

---

## Apply Spotify Customization

Copy the theme files into the appropriate Spicetify theme/custom CSS location.

After copying the files, apply the configuration:

```powershell
spicetify apply
```

Restart Spotify after applying the configuration.

---

## Spotify Updates

Spotify updates can overwrite or invalidate Spicetify modifications.

The official Spicetify documentation recommends reapplying after Spotify updates:

```powershell
spicetify backup apply
```

If required:

```powershell
spicetify update
```

If compatibility problems occur after a Spotify update, check the current Spicetify documentation before modifying the theme files.

---

# 13. Fluent Flyouts

Fluent Flyouts provides customized Windows media/system flyouts and additional taskbar functionality.

## Download

Use the official [Fluent Flyouts](https://github.com/unchihugo/FluentFlyout) GitHub releases.

Install the [latest releases](https://github.com/unchihugo/FluentFlyout/releases/tag/v2.13.1) form the GitHub.

Repository configuration:

```text
configs/
└── Fluent-Flyouts/
    └── FluentFlyout_Settings.xml
```

## Installation

1. Install Fluent Flyouts.
2. Launch the application once.
3. Configure the application as required.
4. Close Fluent Flyouts if necessary.
5. Back up the existing settings file.
6. Replace/import the configuration from:

```text
configs/Fluent-Flyouts/FluentFlyout_Settings.xml
```

7. Restart Fluent Flyouts.

The current configuration enables features including:

* Media flyout
* Media flyout blur
* Acrylic media window
* Acrylic Next Up window
* Acrylic Lock Keys window
* Taskbar widget
* Taskbar widget blur
* Taskbar widget controls
* Taskbar visualizer

---


# 14. Applying the Configuration

After installing all components, restart the affected applications.

Recommended restart sequence:

```text
1. Windhawk
2. Windows Explorer
3. YASB
4. Spotify
5. Fluent Flyouts
```

If the Windows shell does not update correctly, restart Windows.

---

# 15. Troubleshooting

## Taskbar looks incorrect

Check:

* Windows 11 Taskbar Styler is enabled.
* Taskbar Height and Icon Size is enabled.
* The correct configuration was pasted.
* Taskbar margins match the configured height.
* Another taskbar customization is not overriding the styling.

---

## Start Menu is invisible or broken

- Disable the Start Menu Styler mod and verify that the native Start Menu works.
- Then check whether the current Windows build is compatible with the mod.
- Windows UI mods can be affected by Windows updates and changes to internal UI targets.

---

## File Explorer is opaque

Check:

* Translucent Windows is enabled.
* File Explorer Styler is enabled.
* `backgroundTranslucentEffectRegion` is set correctly.
* No other Explorer customization is overriding the background.
* File Explorer has been restarted.

---

## YASB icons are missing

Install:

```text
JetBrainsMonoNerdFontPropo-Regular.ttf
```

Then restart YASB.

Also verify that the CSS font name matches the installed font.

---

## Spotify is still opaque

Check:

1. Spotify is fully closed.
2. Spicetify is installed correctly.
3. `user.css` is in the correct location.
4. `color.ini` is in the correct theme location.
5. The correct theme is selected.
6. Run:

```powershell
spicetify apply
```

7. Restart Spotify.

If Spotify has recently updated, check Spicetify compatibility and reapply the modifications.

---

## Spotify transparency affects other applications

The project uses both:

```text
Translucent Windows
```

and:

```text
Spotify user.css
```

The Translucent Windows configuration contains a Spotify-specific rule to prevent unwanted interaction with the general Windows transparency configuration.

If another application is affected, review the Translucent Windows rules before changing the Spotify CSS.

---

## Changes are not appearing

Try:

```text
1. Save the configuration.
2. Reload the Windhawk mod/application.
3. Restart the affected application.
4. Restart Explorer.
5. Restart Windows if necessary.
```

For Spotify:

```powershell
spicetify apply
```

---

# 16. Restoring Your Original Configuration

Before modifying any existing configuration, create a backup.

For Windhawk mods:

1. Open the affected mod.
2. Open Settings.
3. Save a copy of the current configuration.
4. Disable the mod if necessary.

For YASB:

```text
Back up:
config.yaml
styles.css
```

For Spotify:

```text
Back up:
color.ini
user.css
```

For Fluent Flyouts:

```text
Back up:
FluentFlyout_Settings.xml
```

If a configuration causes instability, disable the corresponding component first rather than removing the entire project.

---

# Repository Configuration Paths

All configurations are organized under:

```text
configs/
├── CEF-Spotify-Tweaks/
├── Fluent-Flyouts/
├── Taskbar-Dock-Animation/
├── Taskbar-Height-and-Icon-Size/
├── Translucent-Windows/
├── Windows-11-File-Explorer-Styler/
├── Windows-11-Start-Menu-Styler/
├── Windows-11-Taskbar-Styler/
└── YASB/
```

Spotify-specific files are stored separately:

```text
spotify/
├── color.ini
└── user.css
```

Visual resources are stored in:

```text
assets/
├── previews/
├── screenshots/
└── wallpapers/
```

---

# Notes

This project is a personal Windows customization configuration.

The exact appearance may vary depending on:

* Windows version
* Windows theme
* Display scaling
* Font installation
* Spotify version
* Spicetify version
* Windhawk version
* Windhawk mod versions
* YASB version
* Fluent Flyouts version
* Other installed Windows customization tools

Do not assume that future versions of Windows or third-party applications will remain compatible with the current configurations.

Always keep a backup before applying major changes.
