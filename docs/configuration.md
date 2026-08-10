# Configuration Guide

This document explains the main configuration values used by the
Windows Liquid Glass Theme and how they affect the appearance.

The configurations are organized by application/mod.

---

# Table of Contents

1. [Taskbar Styler](#1-taskbar-styler)
2. [Taskbar Height and Icon Size](#2-taskbar-height-and-icon-size)
3. [Taskbar Dock Animation](#3-taskbar-dock-animation)
4. [Start Menu Styler](#4-start-menu-styler)
5. [File Explorer Styler](#5-file-explorer-styler)
6. [Translucent Windows](#6-translucent-windows)
7. [YASB](#7-yasb)
8. [Spotify](#8-spotify)
9. [Fluent Flyouts](#9-fluent-flyouts)
10. [Customization Tips](#10-customization-tips)

---

# 1. Taskbar Styler

### Configuration:

```text
configs/Windows-11-Taskbar-Styler/taskbar-styler.yaml
```

### Theme
```
theme: Fluid
```
- This selects the Windhawk Taskbar Styler theme configuration.

### Taskbar Corner Radius

|Value|Effects|
|----|------------------|
| 10 | slightly rounded |
| 15 | medium rounding |
| 20 | current configuration |
| 30| strongly rounded |

### Taskbar Modules
|Module|Value|Effects|
|---|----|------------------|
|**Taskbar Corner Radius**| CornerRadius=20 | Controls how rounded the taskbar container is. |
| **Taskbar Border** | BorderThickness=1 | Controls the outline around the taskbar |
|  | BorderBrush=#40FFFFFF | `40` = opacity & `FFFFFF` = white |
| **Taskbar Margin** | Margin=-20,0,-20,-8 | The four values represent: Left, Top, Right, Bottom |
| **Taskbar Frame** |HorizontalAlignment=Center | Controls the positioning of the taskbar frame |
|  | Margin: 8,6,8,6 | Controls the spacing of the taskbar frame |
| **Root Grid Margin** | Margin=10,0,10,10 | Controls the spacing around the main taskbar root |
| **Root Grid Padding** | Padding=20,0,20,0 | Controls the internal horizontal spacing|
| **System Tray** | Margin=5,5,14,6 | Controls the system tray area |
||CornerRadius=15 ||
||BorderThickness=0 ||
|**Task Buttons**|Margin=3,3.5,5,3|Increase `CornerRadius` for more rounded buttons|
||CornerRadius=10|Increase `Margin` for more space between buttons |

---

# 2. Taskbar Height and Icon Size

Configuration:
```
configs/Taskbar-Height-and-Icon-Size/taskbar-icon-size.yaml
```
Current values:
```
TaskbarHeight: 62
IconSize: 24
TaskbarButtonWidth: 46
IconSizeSmall: 16
TaskbarButtonWidthSmall: 32
```
Controls the overall height of the taskbar.

|Module|Value|Effects|
|---|----|------------------|
|**Main Icon Size**|IconSize: 24|Controls the size of normal taskbar icons|
|**Task Button Width**|TaskbarButtonWidth: 46|Controls the width allocated to normal task buttons|
|**Small Icon Size**|IconSizeSmall: 16|Controls smaller taskbar icons|
|**Small Button Width**|TaskbarButtonWidthSmall: 32|Controls the width of smaller task buttons|

|Value|Effects|
|----|------------------|
| 50 | compact |
| 56 | medium |
| 62 | current |
| 70 | large |

Changing this may require corresponding Taskbar Styler margin
adjustments.

---

# 3. Taskbar Dock Animation

### Configuration:
```
configs/Taskbar-Dock-Animation/taskbar-dock-animation.yaml
```
Important values:
```
MaxScale: 145
EffectRadius: 100
SpacingFactor: 50
BounceDelay: 500
FocusDuration: 150
LerpSpeed: 60
DisableBounce: 1
```
### Modules definations:
|Module|Value|Effects|
|---|----|------------------|
|Max Scale|**MaxScale: 145**|Controls how large icons can become during the dock animation|
|**EffectRadius**|EffectRadius: 100|Controls how far the animation effect extends around the pointer|
|**SpacingFactor**|SpacingFactor: 50|Controls spacing behavior during the dock animation|
|**FocusDuration**|FocusDuration: 150|Controls the duration of the focus animation|
|**LerpSpeed**|LerpSpeed: 60|Controls the interpolation/smoothness of the animation|
|**DisableBounce**|DisableBounce: 1|The current configuration disables the bounce effect, `0` to enabled|

# 4. Start Menu Styler
Configuration:
```
configs/Windows-11-Start-Menu-Styler/start-menu-styler.yaml
```
Start Menu Width
```
- target: Grid#MainMenu
  styles:
    - Width=800
```
Controls the Start Menu width.

Example:
|Value|Effects|
|----|------------------|
|600 | narrow
|700 | medium
|800 | current
|900 | wide

### Start Menu Height
```
- target: Grid#FrameRoot
  styles:
    - Height=600
```
Controls the Start Menu height.

### Pinned List Height
```
- target: StartMenu.PinnedList
  styles:
    - Height=50
```
Controls the vertical size of the pinned application section.

### Recommended List Margin
```
- target: GridView#RecommendedList
  styles:
    - Margin=0,0,0,0 #(Left, Top, Right, Bottom)
```
Controls spacing around the Recommended section.

### All Apps Heading Margin
```
- target: Grid#AllListHeading
  styles:
    - Margin=0,0,0,0
```
Controls spacing around the All Apps heading.

### All Apps Position

The configuration uses a  **RenderTransform** on:
```
Windows.UI.Xaml.Controls.GridView#AllAppsGrid
```
This can be used to shift the All Apps grid horizontally or vertically.

For example:
```
X = -15
```
moves the content to the left.

### Search

The Search customization is contained inside the Start Menu Styler
configuration.

Search dimensions can be controlled using:
```
Width=825
Height=600
```
A translation transform can also be used to adjust its vertical
position.

# 5. File Explorer Styler

Configuration:
```
configs/Windows-11-File-Explorer-Styler/file-explorer-styler.yaml
```

|Module|command|Effects|
|---|----|------------------|
|**Translucent Effect Region**|backgroundTranslucentEffectRegion: entireWindow |This specifies that the translucent effect applies to the entire **Explorer window**|
|**Navigation Bar**|Grid#NavigationBarControlGrid|Controls the Explorer navigation/top area, includes a Windhawk blur background|
|**Main Details Area**|Grid#DetailsViewControlRootGrid|Controls the main Explorer content/details area|
|**Thumbnail Area**|StackPanel#DetailsViewThumbnail|Controls the thumbnail area and its bottom border|
|**Command Bar**|Grid#CommandBarControlRootGrid, BorderThickness=1, BorderBrush=#40FFFFFF, CornerRadius=2 |Increase CornerRadius for more rounded command bar|

---

# 6. Translucent Windows

Configuration:
```
configs/Translucent-Windows/translucent-windows.yaml
```

|Module|Value|Effects|
|---|----|------------------|
|**Theme Background**|ThemeBackground: 1|Controls the theme background rendering behavior|
|**Accent Color Controls**|AccentColorControls: 1|Controls whether accent colors are used by the rendering configuration|
|**Acrylic Blur**|type: acrylicblur|Selects the acrylic blur effect|
|**Accent Blur Behind**|AccentBlurBehind: 3A232323|`3A` → alpha/opacity, `23` → red, `23` → green, `23` → blue, Increasing the alpha value makes the background more opaque|

### Spotify Rule
The configuration includes a separate Spotify rule.

This allows Spotify to have its own rendering behavior rather than
simply inheriting the general Windows transparency configuration.

---

# 7. YASB

Files:
```
configs/YASB/
├── config.yaml
└── styles.css
```
The YASB appearance is primarily controlled by: `styles.css`

### Main Colors

The CSS defines variables such as:
```
--rosewater
--flamingo
--pink
--mauve
--red
--yellow
--green
--teal
--blue
--lavender
--text
--subtext1
--subtext0
```

These can be changed to create a different color palette.

### Main Bar Background
```
.yasb-bar {
    background-color: var(--crust);
}
```
Change the `--crust` variable to change the top bar background.

### Widget Spacing
```
.widget {
    padding: 0 12px;
}
```
Increase the horizontal padding to create more space between widgets.

### Widget Containers
```
.widget-container {
    border-radius: 12px;
}
```
Increase the value for more rounded widgets.

### Workspace Indicators

The workspace styles include:
```
.ws-btn.populated
.ws-btn.active
```
These control the appearance of populated and active workspaces.

# 8. Spotify

Files:
```
spotify/
├── color.ini
└── user.css
```
## Spotify Colors

`color.ini` contains:
```
[LiquidGlass]
main = 081522
sidebar = 07111D
player = 081522
card = 18334A
shadow = 000000
selected-row = 29506B
button = 63C7F5
button-active = 7DD8FF
text = F5FAFF
subtext = B9C9D8
```
These values control the basic Spotify theme colors.

## Spotify Glass Variables

The main user.css defines:
```
--gap: 8px;
--radius: 18px;
--glass-bg: rgba(30, 35, 40, 0.25);
--glass-blur: 10px;
--glass-sat: 100%;
--glass-border: rgba(255, 255, 255, 0.18);
--glass-hover: rgba(255, 255, 255, 0.08); 
```


### Gap
```
--gap: 8px;
```
Controls the spacing between the floating Spotify glass panels.

Increase it for more space.

Example:
```
4px  → compact
8px  → current
12px → spacious
```
### Corner Radius
```
--radius: 18px;
```
Controls the common corner radius of the glass islands.

Example:
```
10px → subtle
18px → current
24px → very rounded
```
### Glass Background
```
--glass-bg: rgba(30, 35, 40, 0.25);
```
The last value controls opacity.

For example:
```
rgba(30, 35, 40, 0.10) is more transparent.

rgba(30, 35, 40, 0.40) is more opaque.
```
### Glass Blur
```
--glass-blur: 10px;
```
Controls the blur applied behind the glass panels.

Higher values create stronger blur.

### Saturation
```
--glass-sat: 100%;
```
Controls the saturation applied through the backdrop filter.

### Glass Border
```
--glass-border: rgba(255, 255, 255, 0.18);
```
Controls the brightness and transparency of the glass border.

The last value controls opacity.

### Hover Background
```
--glass-hover: rgba(255, 255, 255, 0.08);
```
Controls the highlight shown when hovering over certain Spotify
elements.

---

## Spotify Top Bar

The top bar uses:
```
.main-topBar-container
.main-globalNav-container
.main-globalNav-globalNav
.Root__globalNav
```
The common values are:
```
margin: var(--gap);
background: var(--glass-bg);
backdrop-filter: blur(var(--glass-blur));
border: 1px solid var(--glass-border);
border-radius: var(--radius);
```
These values control the top floating glass island.

## Spotify Left Sidebar

The left navigation uses:
```
.Root__nav-bar
.main-navBar-navBar
```
It uses the same:
```
gap
glass background
blur
border
corner radius
```
as the other panels.

## Spotify Right Sidebar

The right sidebar uses:
```
.Root__right-sidebar
```
The same Liquid Glass variables control its appearance.

## Spotify Bottom Player

The bottom player uses:
```
.main-nowPlayingBar-container
```
The common glass variables are applied here as well.

## Spotify Middle Panel

The main content area uses:
```
.Root__main-view
```
It is styled as another floating Liquid Glass island.

## Spotify Action Bar

The sticky filter/action bar uses selectors such as:
```
.main-actionBarBackground-background
.main-actionBar-ActionBarBackground
```
The configuration makes the background transparent and then restores
the filter buttons as glass pills.

## Spotify Cards

Cards are styled using:
```
.main-card-card
```
Current properties include:
```
background: rgba(43, 57, 70, 0.20);
border-radius: 12px;
```
Change these values to modify the card appearance.

# 9. Fluent Flyouts

Configuration:
```
configs/Fluent-Flyouts/FluentFlyout_Settings.xml
```
Important settings include:
```
<MediaFlyoutBackgroundBlur>1</MediaFlyoutBackgroundBlur>
<MediaFlyoutAcrylicWindowEnabled>true</MediaFlyoutAcrylicWindowEnabled>
<NextUpAcrylicWindowEnabled>true</NextUpAcrylicWindowEnabled>
<LockKeysAcrylicWindowEnabled>true</LockKeysAcrylicWindowEnabled>
```
These control the acrylic/blur behavior of the flyouts.

The acrylic opacity is:
```
<AcrylicBlurOpacity>150</AcrylicBlurOpacity>
```
# 10. Customization Tips
## Make Everything More Transparent

For Spotify, reduce: `--glass-bg`

For example:
```
--glass-bg: rgba(30, 35, 40, 0.12);
```
## Make Everything More Opaque

Increase the alpha value:
```
--glass-bg: rgba(30, 35, 40, 0.35);
```
## Increase Glass Blur

Change:
```
--glass-blur: 10px;
```
to:
```
--glass-blur: 20px;
```

### Increase Corner Rounding

Change:
```
--radius: 18px;
```
to:
```
--radius: 24px;

```
## Reduce Panel Spacing

Change:
```
--gap: 8px;
```
to:
```
--gap: 4px;
```

## Increase Panel Spacing

Change:
```
--gap: 8px;
```
to:
```
--gap: 12px;
```

## Important

Change one group of values at a time.

After changing a configuration:

1. Save the file.
2. Apply/reload the corresponding mod.
3. Check the result.
4. Keep a backup of the previous working version.

Do not modify several independent components simultaneously when
troubleshooting. This makes it difficult to identify which change
caused a problem.
