# Installation Guide

This guide explains how to install and configure the components used by the **Windows Liquid Glass Theme**.

The project combines Windhawk mods, YASB, Spicetify, Fluent Flyouts, and additional Windows customization tools to create a consistent translucent and Liquid Glass desktop experience.

---

## Table of Contents

1. [Requirements](#1-requirements)
2. [Before Installation](#2-before-installation)
3. [Windhawk](#3-windhawk)
4. [Translucent Windows](#4-translucent-windows)
5. [Windows 11 Taskbar Styler](#5-windows-11-taskbar-styler)
6. [Taskbar Height and Icon Size](#6-taskbar-height-and-icon-size)
7. [Taskbar Dock Animation](#7-taskbar-dock-animation)
8. [Windows 11 Start Menu Styler](#8-windows-11-start-menu-styler)
9. [Windows 11 File Explorer Styler](#9-windows-11-file-explorer-styler)
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

- Windows 11
- Dark mode recommended
- A Windows build compatible with the installed Windhawk mods

Compatibility may change after Windows updates because the styling targets used by Windows UI components can change.

## Required Software

| Component | Software |
|---|---|
| Windows UI customization | Windhawk |
| Taskbar | Windows 11 Taskbar Styler |
| Start Menu | Windows 11 Start Menu Styler |
| File Explorer | Windows 11 File Explorer Styler |
| System transparency | Translucent Windows |
| Taskbar sizing | Taskbar Height and Icon Size |
| Taskbar animation | Taskbar Dock Animation |
| Custom top bar | YASB |
| Spotify customization | Spotify Desktop + Spicetify |
| Spotify CEF customization | CEF Spotify Tweaks |
| System/media flyouts | Fluent Flyouts |

## Recommended Installation Order

For the closest result to the project preview, install the components in this order.

### Core Windows UI

1. Install [Windhawk](https://windhawk.net/).
2. Install Translucent Windows.
3. Install Windows 11 Taskbar Styler.
4. Install Taskbar Height and Icon Size.
5. Install Windows 11 Start Menu Styler.
6. Install Windows 11 File Explorer Styler.

### Additional Windows Components

7. Install Taskbar Dock Animation.
8. Install Fluent Flyouts.

### Custom Top Bar

9. Install [YASB](https://github.com/amnweb/yasb).
10. Install the JetBrains Mono Nerd Font included in `assets/fonts/`.
11. Apply the repository's `config.yaml`.
12. Apply the repository's `styles.css`.

### Spotify

13. Install the [Spotify Desktop Client](https://download.scdn.co/SpotifySetup.exe).
14. Install [Spicetify](https://spicetify.app/docs/getting-started).
15. Select and install either the Liquid Glass or Misty Forest theme.
16. Install CEF Spotify Tweaks if required.
17. Apply the corresponding CEF configuration.

---

# 2. Before Installation

## 1. Create a Backup

Before applying any Windhawk configuration, make a backup of your existing settings.

This repository contains customized configurations intended for this specific Liquid Glass setup.

Do not overwrite your existing configuration if you want to preserve your current Windows customization.

Recommended backups:

- Existing Windhawk mod configurations
- Existing YASB configuration and styles
- Existing Spicetify theme files
- Existing Fluent Flyouts settings

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
5. Open the mod's **Settings**.
6. Switch to **Textual mode** when required.
7. Open the corresponding configuration file from this repository.
8. Copy the configuration.
9. Paste it into the Windhawk configuration editor.
10. Save the settings.
11. Reload the mod.

The repository contains configurations for:

- Translucent Windows
- Windows 11 Taskbar Styler
- Taskbar Height and Icon Size
- Taskbar Dock Animation
- Windows 11 Start Menu Styler
- Windows 11 File Explorer Styler
- CEF Spotify Tweaks

Some additional Windhawk mods may be required for features that do not have a configuration file included in this repository.

---

# 4. Translucent Windows

Install the **Translucent Windows** mod from Windhawk.

## Installation

1. Open Windhawk.
2. Open **Mods**.
3. Search for **Translucent Windows**.
4. Install the mod.
5. Open **Settings**.
6. Select **Textual mode**.
7. Open:

```text
configs/Translucent Windows/translucent-windows.yaml
```

8. Copy the configuration.
9. Paste it into the Windhawk configuration editor.
10. Save the configuration.
11. Restart/reload the mod.

This configuration provides the system-level translucent/acrylic effect used by the overall theme.

### Spotify Exception

The configuration also contains a Spotify-specific rule.

This is intentional because Spotify has its own transparency and glass styling in its Spicetify theme files.

The Spotify variants are stored separately:

```text
spotify/
├── Liquid-Glass/
│   ├── color.ini
│   └── user.css
│
└── Misty-Forest/
    ├── color.ini
    └── user.css
```

Do not remove the Spotify rule unless you want to change how Spotify interacts with the general Windows transparency configuration.

---

# 5. Windows 11 Taskbar Styler

Install:

```text
Windows 11 Taskbar Styler
```

Repository configuration:

```text
configs/
└── Windows 11 Taskbar Styler/
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
configs/Windows 11 Taskbar Styler/taskbar-styler.yaml
```

8. Copy the configuration.
9. Paste it into the Windhawk configuration editor.
10. Save the configuration.
11. Restart/reload the mod.

## What It Controls

The configuration controls:

- Taskbar positioning
- Taskbar margins
- Rounded corners
- Taskbar border
- Background transparency
- Task item glass
- System tray glass
- Task button spacing
- Running indicators

The current configuration uses the `Fluid` theme identifier.

---

# 6. Taskbar Height and Icon Size

This component adjusts the Windows Taskbar dimensions and icon sizing.

## Installation

1. Open Windhawk.
2. Open **Mods**.
3. Search for **Taskbar height and icon size**.
4. Install the mod.
5. Open **Settings**.
6. Select **Textual mode**.
7. Open:

```text
configs/Taskbar height and icon size/taskbar-icon-size.yaml
```

8. Copy the configuration.
9. Paste it into the Windhawk configuration editor.
10. Save the configuration.
11. Restart/reload the mod.

### Important

Taskbar Styler and Taskbar Height and Icon Size work together.

If you change the taskbar height, you may need to adjust:

- Taskbar margins
- Task button margins
- System tray margins
- Icon dimensions
- YASB alignment

---

# 7. Taskbar Dock Animation

This component provides the dock-style Taskbar animation.

## Installation

1. Open Windhawk.
2. Open **Mods**.
3. Search for **Taskbar Dock Animation**.
4. Install the mod.
5. Open **Settings**.
6. Select **Textual mode**.
7. Open:

```text
configs/Taskbar Dock Animation/taskbar-dock-animation.yaml
```

8. Copy the configuration.
9. Paste it into the Windhawk configuration editor.
10. Save the configuration.
11. Restart/reload the mod.

The animation settings can be adjusted independently of the main Taskbar Styler configuration.

---

# 8. Windows 11 Start Menu Styler

This component customizes the Windows 11 Start Menu.

## Installation

1. Open Windhawk.
2. Open **Mods**.
3. Search for **Windows 11 Start Menu Styler**.
4. Install the mod.
5. Open **Settings**.
6. Select **Textual mode**.
7. Open:

```text
configs/Windows 11 Start Menu Styler/start-menu-styler.yaml
```

8. Copy the configuration.
9. Paste it into the Windhawk configuration editor.
10. Save the configuration.
11. Restart/reload the mod.

## Current Customization

The configuration is designed to provide:

- Rounded Start Menu surfaces
- Transparent and translucent backgrounds
- Custom margins and spacing
- Liquid Glass visual styling

The final appearance depends on the Windows build and the installed mod version.

---

# 9. Windows 11 File Explorer Styler

This component customizes File Explorer to match the Liquid Glass appearance.

## Installation

1. Open Windhawk.
2. Open **Mods**.
3. Search for **Windows 11 File Explorer Styler**.
4. Install the mod.
5. Open **Settings**.
6. Select **Textual mode**.
7. Open:

```text
configs/Windows 11 File Explorer Styler/file-explorer-styler.yaml
```

8. Copy the configuration.
9. Paste it into the Windhawk configuration editor.
10. Save the configuration.
11. Restart/reload the mod or File Explorer.

## Current Customization

The configuration includes styling for:

- File Explorer backgrounds
- Navigation panel
- Command bar
- Translucent surfaces
- Rounded UI elements
- Consistent visual appearance

---

# 10. YASB

YASB is used as the custom Liquid Glass top bar.

It provides a customizable Windows status bar with widgets, system information, and custom CSS styling.

## Download

Install [YASB](https://github.com/amnweb/yasb) using its [official releases](https://github.com/amnweb/yasb/releases) or [installation documentation](https://github.com/amnweb/yasb/wiki/Installation).

## Repository Configuration

```text
configs/
└── yasb/
    ├── config.yaml
    └── styles.css
```

## Font

The project uses:

```text
JetBrainsMonoNerdFontPropo-Regular.ttf
```

The font is included in:

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
4. Locate the YASB configuration directory.
5. Back up the existing configuration.
6. Copy this project's `config.yaml`.
7. Copy this project's `styles.css`.
8. Install the included font if it is not already installed.
9. Start YASB again.

The default YASB configuration directory on Windows is:

```text
%USERPROFILE%\.config\yasb
```

The final directory should contain:

```text
.config/
└── yasb/
    ├── config.yaml
    └── styles.css
```

## YASB Styling

The included CSS controls:

- Top bar transparency
- Widget spacing
- Rounded widget containers
- Colors
- Fonts
- Workspace indicators
- Weather
- GitHub
- System widgets
- Power menu
- Calendar
- Wallpaper gallery
- Taskbar widgets

---

# 11. CEF Spotify Tweaks

CEF Spotify Tweaks is used for additional Spotify-related customization through Windhawk.

## Installation

1. Open Windhawk.
2. Open **Mods**.
3. Search for **CEF Spotify Tweaks**.
4. Install the mod.
5. Open **Settings**.
6. Select **Textual mode**.
7. Open:

```text
configs/CEF-Spotify Tweaks/config.yaml
```

8. Copy the configuration.
9. Paste it into the Windhawk configuration editor.
10. Save the configuration.
11. Restart/reload the mod.

Install the corresponding CEF Spotify Tweaks component before applying the repository configuration.

---

# 12. Spicetify

Spicetify is used to customize the Spotify desktop client.

The repository contains two independent Spotify Liquid Glass appearances:

1. Liquid Glass
2. Misty Forest

Both themes have their own `color.ini` and `user.css`.

## Install Spotify First

Install the official [Spotify Desktop Client](https://download.scdn.co/SpotifySetup.exe) and log in.

**Important:** Use the official standalone Spotify Desktop installer rather than the Microsoft Store version.

For a fresh installation, open Spotify and allow it to initialize before running Spicetify.

---

## Install Spicetify

Use the official [Spicetify installation documentation](https://spicetify.app/docs/getting-started).

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

To check the current theme:

```powershell
spicetify config current_theme
```

To inspect the current Spicetify configuration:

```powershell
spicetify config
```

---

## Spotify Theme Files

The repository contains two theme directories:

```text
spotify/
│
├── Liquid-Glass/
│   ├── color.ini
│   └── user.css
│
└── Misty-Forest/
    ├── color.ini
    └── user.css
```

### Liquid Glass

Location:

```text
spotify/Liquid-Glass/
```

This theme provides:

- Dark translucent interface
- Glass top bar
- Glass left sidebar
- Glass right sidebar
- Floating middle content
- Glass bottom player
- Transparent action/filter bar
- Rounded cards and controls
- Custom Spotify colors and spacing

### Misty Forest

Location:

```text
spotify/Misty-Forest/
```

This theme provides:

- Forest-inspired green glass appearance
- Mint-colored accents
- Translucent interface panels
- Enhanced background blur and saturation
- Diagonal glass highlights
- Wallpaper-coordinated appearance

### color.ini

Contains the color palette used by the corresponding Spotify theme.

### user.css

Contains the visual customization, including:

- Transparent structural layers
- Glass panels
- Rounded controls
- Borders and backgrounds
- Button spacing
- Track-list styling
- Sidebar styling
- Player styling
- Hover behavior

Each theme has its own independent files. Do not combine the two configurations into one theme folder.

---

## Apply the Liquid Glass Theme

### 1. Locate the Spicetify Themes Directory

The default location is:

```text
%APPDATA%\spicetify\Themes
```

Open it using File Explorer or PowerShell:

```powershell
explorer "$env:APPDATA\spicetify\Themes"
```

### 2. Create the Theme Folder

Create:

```text
Liquid-Glass
```

The resulting path should be:

```text
%APPDATA%\spicetify\Themes\Liquid-Glass
```

### 3. Copy the Theme Files

Copy the following files from this repository:

```text
spotify/Liquid-Glass/
├── color.ini
└── user.css
```

Paste them into:

```text
%APPDATA%\spicetify\Themes\Liquid-Glass/
```

The final structure should be:

```text
Themes/
└── Liquid-Glass/
    ├── color.ini
    └── user.css
```

### 4. Activate the Theme

Run:

```powershell
spicetify config current_theme Liquid-Glass
```

Then apply:

```powershell
spicetify apply
```

Restart Spotify if necessary.

---

## Apply the Misty Forest Theme

### 1. Create the Theme Folder

Inside:

```text
%APPDATA%\spicetify\Themes
```

Create:

```text
Misty-Forest
```

### 2. Copy the Theme Files

Copy:

```text
spotify/Misty-Forest/
├── color.ini
└── user.css
```

Paste them into:

```text
%APPDATA%\spicetify\Themes\Misty-Forest/
```

The final structure should be:

```text
Themes/
└── Misty-Forest/
    ├── color.ini
    └── user.css
```

### 3. Activate the Theme

Run:

```powershell
spicetify config current_theme Misty-Forest
```

Then apply:

```powershell
spicetify apply
```

Restart Spotify if necessary.

---

## Switching Between Spotify Themes

Both variants can remain installed simultaneously.

To switch to Liquid Glass:

```powershell
spicetify config current_theme Liquid-Glass
spicetify apply
```

To switch to Misty Forest:

```powershell
spicetify config current_theme Misty-Forest
spicetify apply
```

Only the selected theme is active at a time.

### Optional: Development Workflow

For theme development, you can edit the active theme's `user.css` directly.

If you maintain a symbolic link from the Spicetify Themes directory to your repository, edits can be made directly in VS Code without copying files repeatedly.

Spicetify also provides a watch command:

```powershell
spicetify watch
```

Use this from the active theme development directory when working with supported theme file changes.

---

## Spotify Updates

Spotify updates can overwrite or invalidate Spicetify modifications.

After a Spotify update, check Spicetify compatibility and reapply the modifications if required.

Use the official [Spicetify documentation](https://spicetify.app/docs/getting-started) for current recovery and backup instructions.

---

# 13. Fluent Flyouts

Fluent Flyouts provides customized Windows media/system flyouts and additional taskbar functionality.

## Download

Use the official [Fluent Flyouts GitHub repository](https://github.com/unchihugo/FluentFlyout).

Download the latest version from [GitHub Releases](https://github.com/unchihugo/FluentFlyout/releases).

## Repository Configuration

```text
configs/
└── Fluent Flyouts/
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
configs/Fluent Flyouts/FluentFlyout_Settings.xml
```

7. Restart Fluent Flyouts.

The current configuration includes features such as:

- Media flyout
- Media flyout blur
- Acrylic media window
- Acrylic Next Up window
- Acrylic Lock Keys window
- Taskbar widget
- Taskbar widget blur
- Taskbar widget controls
- Taskbar visualizer

Available settings may vary depending on the installed Fluent Flyouts version.

---

# 14. Applying Updates

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

For Spotify theme changes, run:

```powershell
spicetify apply
```

---

# 15. Troubleshooting

## Taskbar Looks Incorrect

Check:

- Windows 11 Taskbar Styler is enabled.
- Taskbar Height and Icon Size is enabled.
- The correct configuration was pasted.
- Taskbar margins match the configured height.
- Another taskbar customization is not overriding the styling.

## Start Menu Is Invisible or Broken

- Disable the Start Menu Styler mod and verify that the native Start Menu works.
- Check whether the current Windows build is compatible with the mod.
- Windows UI mods can be affected by Windows updates and changes to internal UI targets.

## File Explorer Is Opaque

Check:

- Translucent Windows is enabled.
- File Explorer Styler is enabled.
- The configuration has been applied correctly.
- No other Explorer customization is overriding the background.
- File Explorer has been restarted.

## YASB Icons Are Missing

Install:

```text
assets/fonts/JetBrainsMonoNerdFontPropo-Regular.ttf
```

Then restart YASB.

Also verify that the CSS font name matches the installed font.

## Spotify Is Still Opaque

Check:

1. Spotify is fully closed.
2. Spicetify is installed correctly.
3. `user.css` is in the correct theme folder.
4. `color.ini` is in the correct theme folder.
5. The correct theme is selected.
6. Run:

```powershell
spicetify apply
```

7. Restart Spotify.

If Spotify has recently updated, check Spicetify compatibility and reapply the modifications.

## Spotify Theme Is Not Switching

Check the selected theme:

```powershell
spicetify config current_theme
```

For Liquid Glass:

```powershell
spicetify config current_theme Liquid-Glass
spicetify apply
```

For Misty Forest:

```powershell
spicetify config current_theme Misty-Forest
spicetify apply
```

Verify that the selected theme folder exists inside:

```text
%APPDATA%\spicetify\Themes
```

Also verify that the folder contains both `color.ini` and `user.css`.

## Spotify Transparency Affects Other Applications

The project uses both:

- Translucent Windows
- Spotify `user.css`

The Translucent Windows configuration contains a Spotify-specific rule to prevent unwanted interaction with the general Windows transparency configuration.

If another application is affected, review the Translucent Windows rules before changing the Spotify CSS.

## Changes Are Not Appearing

Try:

1. Save the configuration.
2. Reload the Windhawk mod/application.
3. Restart the affected application.
4. Restart Explorer.
5. Restart Windows if necessary.

For Spotify:

```powershell
spicetify apply
```

---

# 16. Restoring Your Original Configuration

Before modifying any existing configuration, create a backup.

## Windhawk Mods

1. Open the affected mod.
2. Open Settings.
3. Save a copy of the current configuration.
4. Disable the mod if necessary.

## YASB

Back up:

```text
config.yaml
styles.css
```

Restore your previous files in:

```text
%USERPROFILE%\.config\yasb
```

## Spotify

Back up the currently installed theme files.

```text
color.ini
user.css
```

To restore the original appearance, select your previous Spicetify theme or restore your backed-up files.

## Fluent Flyouts

Back up:

```text
FluentFlyout_Settings.xml
```

Restore the previous settings file and restart Fluent Flyouts.

If a configuration causes instability, disable the corresponding component first rather than removing the entire project.

---

# Repository Configuration Paths

All Windows configurations are organized under:

```text
configs/
│
├── CEF-Spotify Tweaks/
│   └── config.yaml
│
├── Fluent Flyouts/
│   └── FluentFlyout_Settings.xml
│
├── Taskbar Dock Animation/
│   └── taskbar-dock-animation.yaml
│
├── Taskbar height and icon size/
│   └── taskbar-icon-size.yaml
│
├── Translucent Windows/
│   └── translucent-windows.yaml
│
├── Windows 11 File Explorer Styler/
│   └── file-explorer-styler.yaml
│
├── Windows 11 Start Menu Styler/
│   └── start-menu-styler.yaml
│
├── Windows 11 Taskbar Styler/
│   └── taskbar-styler.yaml
│
└── yasb/
    ├── config.yaml
    └── styles.css
```

Spotify themes are stored separately:

```text
spotify/
│
├── Liquid-Glass/
│   ├── color.ini
│   └── user.css
│
└── Misty-Forest/
    ├── color.ini
    └── user.css
```

Visual resources are stored in:

```text
assets/
├── fonts/
├── previews/
├── screenshots/
└── wallpapers/
```

---

# Notes

This project is a personal Windows customization configuration.

The exact appearance may vary depending on:

- Windows version
- Windows theme
- Display scaling
- Font installation
- Spotify version
- Spicetify version
- Windhawk version
- Windhawk mod versions
- YASB version
- Fluent Flyouts version
- Other installed Windows customization tools

Do not assume that future versions of Windows or third-party applications will remain compatible with the current configurations.

Always keep a backup before applying major changes.