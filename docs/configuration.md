# Configuration Guide

This document explains the main configuration values used by the Windows Liquid Glass Theme and how they affect the appearance.

The configurations are organized by application and customization component. Each section includes the configuration file location, important settings, and examples of how to customize them.

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

### Configuration

```text
configs/Windows 11 Taskbar Styler/taskbar-styler.yaml
```

### Theme

```yaml
theme: Fluid
```

This selects the Fluid theme configuration for Windows 11 Taskbar Styler.

### Taskbar Corner Radius

The taskbar container uses:

```yaml
- CornerRadius=20
```

| Value | Appearance |
|---|---|
| 10 | Slightly rounded |
| 15 | Medium rounding |
| 20 | Current configuration |
| 30 | Strongly rounded |

### Taskbar Modules

| Module | Configuration | Effect |
|---|---|---|
| Taskbar Corner Radius | `CornerRadius=20` | Controls taskbar corner rounding |
| Taskbar Border | `BorderThickness=1` | Controls border thickness |
| Border Color | `BorderBrush=#40FFFFFF` | Controls border color and opacity |
| Taskbar Margin | `Margin=-20,0,-20,-8` | Controls taskbar background positioning |
| Taskbar Frame | `HorizontalAlignment=Center` | Controls frame positioning |
| Frame Margin | `Margin: 8,6,8,6` | Controls frame spacing |
| Root Grid Margin | `Margin=10,0,10,10` | Controls spacing around the root grid |
| Root Grid Padding | `Padding=20,0,20,0` | Controls internal horizontal spacing |
| System Tray | `Margin=5,5,14,6` | Controls system tray positioning |
| System Tray Radius | `CornerRadius=15` | Controls system tray rounding |
| Task Buttons | `CornerRadius=10` | Controls task button rounding |
| Task Button Margin | `Margin=3,3.5,5,3` | Controls task button spacing |

### Task Item Background

The task item background is defined through a style constant:

```yaml
TaskItemBackground=<AcrylicBrush TintColor="{ThemeResource SystemChromeAltHighColor}" TintOpacity="0.4" FallbackColor="{ThemeResource SystemChromeMediumColor}" />
```

### System Item Background

```yaml
SystemItemBackground=<AcrylicBrush TintColor="{ThemeResource SystemChromeAltHighColor}" TintOpacity="0" FallbackColor="{ThemeResource SystemChromeLowColor}" />
```

These values control the appearance of task buttons and system buttons.

### Taskbar Background

The background uses a Windhawk blur element:

```yaml
- Fill:=<WindhawkBlur BlurAmount="5" TintColor="{ThemeResource SystemChromeAltHighColor}" TintOpacity="0.4" />
```

Increasing the blur amount creates a stronger blur effect.

---

# 2. Taskbar Height and Icon Size

### Configuration

```text
configs/Taskbar height and icon size/taskbar-icon-size.yaml
```

### Current Values

```yaml
TaskbarHeight: 62
IconSize: 24
TaskbarButtonWidth: 46
IconSizeSmall: 16
TaskbarButtonWidthSmall: 32
```

### Configuration Parameters

| Parameter | Current Value | Effect |
|---|---:|---|
| TaskbarHeight | 62 | Controls overall taskbar height |
| IconSize | 24 | Controls normal taskbar icon size |
| TaskbarButtonWidth | 46 | Controls normal task button width |
| IconSizeSmall | 16 | Controls smaller taskbar icon size |
| TaskbarButtonWidthSmall | 32 | Controls smaller task button width |

### Taskbar Height Examples

| Value | Appearance |
|---|---|
| 50 | Compact |
| 56 | Medium |
| 62 | Current configuration |
| 70 | Large |

Changing the taskbar height may require corresponding adjustments to Taskbar Styler margins and YASB positioning.

---

# 3. Taskbar Dock Animation

### Configuration

```text
configs/Taskbar Dock Animation/taskbar-dock-animation.yaml
```

### Current Values

```yaml
AnimationType: 0
MaxScale: 145
EffectRadius: 100
SpacingFactor: 50
BounceDelay: 500
FocusDuration: 150
MirrorForTopTaskbar: 0
DisableVerticalBounce: 0
TaskbarLabelsMode: 0
ExcludeSystemButtonsMode: 0
LerpSpeed: 60
DisableBounce: 1
```

### Important Parameters

| Parameter | Current Value | Effect |
|---|---:|---|
| AnimationType | 0 | Selects animation type |
| MaxScale | 145 | Controls maximum icon scaling |
| EffectRadius | 100 | Controls the area affected by the animation |
| SpacingFactor | 50 | Controls spacing behavior |
| BounceDelay | 500 | Controls bounce delay |
| FocusDuration | 150 | Controls focus duration |
| LerpSpeed | 60 | Controls animation interpolation speed |
| DisableBounce | 1 | Disables the bounce effect |

### Maximum Scale

```yaml
MaxScale: 145
```

Controls how large icons can become during the dock animation.

### Effect Radius

```yaml
EffectRadius: 100
```

Controls how far the animation effect extends around the pointer.

### Animation Smoothness

```yaml
LerpSpeed: 60
```

Controls interpolation behavior during the animation.

### Bounce Effect

```yaml
DisableBounce: 1
```

The current configuration disables the bounce effect.

---

# 4. Start Menu Styler

### Configuration

```text
configs/Windows 11 Start Menu Styler/start-menu-styler.yaml
```

### Start Menu Width

```yaml
- target: Grid#MainMenu
  styles:
    - Width=800
```

Controls the Start Menu width.

| Value | Appearance |
|---|---|
| 600 | Narrow |
| 700 | Medium |
| 800 | Current configuration |
| 900 | Wide |

### Start Menu Height

```yaml
- target: Grid#FrameRoot
  styles:
    - Height=600
```

Controls the Start Menu height.

### Pinned List Height

```yaml
- target: StartMenu.PinnedList
  styles:
    - Height=50
```

Controls the vertical size of the pinned application section.

### Recommended List Margin

```yaml
- target: GridView#RecommendedList
  styles:
    - Margin=0,0,0,0
```

Controls spacing around the Recommended section.

### All Apps Heading Margin

```yaml
- target: Grid#AllListHeading
  styles:
    - Margin=0,0,0,0
```

Controls spacing around the All Apps heading.

### All Apps Position

The configuration uses a `RenderTransform` on:

```yaml
- target: GridView#AllAppsGrid
  styles:
    - RenderTransform:=<TranslateTransform X="-15" Y="0" />
```

The X and Y values control horizontal and vertical positioning.

For example:

```text
X = -15
```

Moves the content to the left.

### Search Dimensions

The search customization is contained inside the Start Menu Styler configuration.

```yaml
- target: Cortana.UI.Views.TaskbarSearchPage
  styles:
    - Width=825
    - Height=600
    - RenderTransform:=<TranslateTransform Y="145" />
```

These values control search dimensions and vertical positioning.

---

# 5. File Explorer Styler

### Configuration

```text
configs/Windows 11 File Explorer Styler/file-explorer-styler.yaml
```

### Main Configuration

```yaml
theme: Translucent Explorer11
backgroundTranslucentEffectRegion: entireWindow
explorerFrameContainerHeight: 0
```

The configuration applies translucent styling across the Explorer window.

### Control Styling

| Module | Target | Effect |
|---|---|---|
| Navigation Bar | `Grid#NavigationBarControlGrid` | Controls the navigation area background |
| Details View | `Grid#DetailsViewControlRootGrid` | Controls the main details area |
| Thumbnail Area | `StackPanel#DetailsViewThumbnail` | Controls thumbnail styling |
| Command Bar | `Grid#CommandBarControlRootGrid` | Controls command bar border and rounding |

### Navigation Bar

```yaml
- target: Grid#NavigationBarControlGrid
  styles:
    - Background:=<WindhawkBlur BlurAmount="1" TintColor="#18202020" TintOpacity="0.25"/>
    - BorderThickness=0,0,0,0
    - BorderBrush=#30FFFFFF
```

Controls the translucent navigation area.

### Details View

```yaml
- target: Grid#DetailsViewControlRootGrid
  styles:
    - Background:=<WindhawkBlur BlurAmount="10" TintColor="#18202020" TintOpacity="0.25"/>
    - BorderThickness=0,0,1,1
    - BorderBrush=#25FFFFFF
```

Controls the background and border of the main details area.

### Command Bar

```yaml
- target: Grid#CommandBarControlRootGrid
  styles:
    - BorderThickness=1
    - BorderBrush=#40FFFFFF
    - CornerRadius=2
```

Controls the command bar border and corner rounding.

Increasing `CornerRadius` creates more rounded corners.

---

# 6. Translucent Windows

### Configuration

```text
configs/Translucent Windows/translucent-windows.yaml
```

### Main Configuration

```yaml
RenderingMod:
  ThemeBackground: 1
  SysColors: 0
  AccentColorControls: 1

BackgroundEffects:
  type: acrylicblur
  AccentBlurBehind: 3A232323

FlyoutsEffects: 1
```

### Configuration Parameters

| Parameter | Current Value | Effect |
|---|---|---|
| ThemeBackground | 1 | Controls theme background rendering |
| SysColors | 0 | Controls system color behavior |
| AccentColorControls | 1 | Enables accent color controls |
| type | acrylicblur | Selects the acrylic blur effect |
| AccentBlurBehind | `3A232323` | Defines the blur-behind tint |
| FlyoutsEffects | 1 | Enables flyout effects |

### Accent Blur Behind

```yaml
AccentBlurBehind: 3A232323
```

The value is represented as an ARGB hexadecimal color:

| Part | Value | Meaning |
|---|---|---|
| Alpha | `3A` | Opacity |
| Red | `23` | Red component |
| Green | `23` | Green component |
| Blue | `23` | Blue component |

Increasing the alpha value makes the background more opaque.

### Spotify Rule

The configuration includes a separate rule for Spotify:

```yaml
RuledPrograms:
  - target: Spotify.exe
    RenderingMod:
      ThemeBackground: 1
      AccentColorControls: 1
    BackgroundEffects:
      type: acrylicblur
      AccentBlurBehind: ''
```

This allows Spotify to use its own rendering behavior rather than simply inheriting the general Windows transparency configuration.

Spotify's detailed appearance is controlled separately through Spicetify.

---

# 7. YASB

YASB provides the custom top bar and widget system.

### Configuration Files

```text
configs/yasb/
├── config.yaml
└── styles.css
```

The configuration is divided into two main files:

| File | Purpose |
|---|---|
| `config.yaml` | Controls bars, widgets, positions, dimensions and widget behavior |
| `styles.css` | Controls colors, typography, borders, spacing and visual appearance |

### Main Bar Configuration

The main bar is configured in `config.yaml`.

```yaml
bars:
  primary-bar:
    enabled: true
    screens: ["*"]
    class_name: "yasb-bar"
    alignment:
      position: "top"
      center: false
    dimensions:
      width: "100%"
      height: 30
```

### Bar Dimensions

| Parameter | Current Value | Effect |
|---|---|---|
| width | 100% | Controls bar width |
| height | 30 | Controls bar height |
| position | top | Places the bar at the top |
| center | false | Controls centered alignment |

### Widget Placement

```yaml
widgets:
  left: ["active_window"]
  center: ["clock","apps"]
  right: ["ai","github","wallpapers","volume","power_menu"]
```

This controls which widgets appear on the left, center and right sides of the bar.

### Main Colors

The stylesheet defines the following color variables:

```css
:root {
    --rosewater: #f5e0dc;
    --flamingo: #f2cdcd;
    --pink: #f5c2e7;
    --mauve: #cba6f7;
    --red: #f38ba8;
    --maroon: #eba0ac;
    --peach: #fab387;
    --yellow: #f9e2af;
    --green: #a6e3a1;
    --teal: #94e2d5;
    --sky: #89dceb;
    --sapphire: #74c7ec;
    --blue: #89b4fa;
    --lavender: #b4befe;
    --text: #cdd6f4;
    --subtext1: #bac2de;
    --subtext0: #aeb4cf;
    --base: #1e1e2e;
    --crust: rgba(15, 30, 45, 0.3);
    --border: rgba(255, 255, 255, 0.2);
}
```

Changing these values allows you to customize the YASB color palette.

### Main Bar Background

```css
.yasb-bar {
    background-color: var(--crust);
    border: 1px solid var(--border);
}
```

Change `--crust` to modify the bar background.

Change `--border` to adjust border visibility.

### Widget Spacing

```css
.widget {
    margin: 0 2px !important;
    padding: 0 5px !important;
    border-radius: 12px !important;
}
```

- `margin` controls spacing outside the widget.
- `padding` controls internal spacing.
- `border-radius` controls widget rounding.

### Widget Containers

```css
.widget-container {
    border-radius: 12px;
}
```

Controls the rounding of individual widget containers.

### Workspace Indicators

The workspace styles include:

```css
.ws-btn.populated
.ws-btn.active
```

These control the appearance of populated and active workspaces.

### Font

The project uses:

```text
assets/fonts/JetBrainsMonoNerdFontPropo-Regular.ttf
```

The stylesheet references:

```css
font-family: "JetBrainsMono NFP";
```

Install the font before applying the YASB configuration if it is not already installed.

---

# 8. Spotify

Spotify customization is managed through Spicetify.

The repository contains two independent Spotify themes:

1. Liquid Glass
2. Misty Forest

Each theme has its own `color.ini` and `user.css`.

### Theme Files

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

## 8.1 Liquid Glass

### Configuration Files

```text
spotify/Liquid-Glass/
├── color.ini
└── user.css
```

### Color Configuration

The `color.ini` file defines the Spotify theme palette.

```ini
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

| Variable | Current Value | Effect |
|---|---|---|
| main | `081522` | Main background color |
| sidebar | `07111D` | Sidebar color |
| player | `081522` | Player background |
| card | `18334A` | Card background |
| shadow | `000000` | Shadow color |
| selected-row | `29506B` | Selected track background |
| button | `63C7F5` | Button accent |
| button-active | `7DD8FF` | Active button accent |
| text | `F5FAFF` | Main text |
| subtext | `B9C9D8` | Secondary text |

### Glass Variables

The main `user.css` defines:

```css
:root {
    --gap: 8px;
    --radius: 18px;
    --glass-bg: rgba(43, 57, 70, 0.14);
    --glass-blur: 10px;
    --glass-sat: 130%;
    --glass-border: rgba(255, 255, 255, 0.18);
    --glass-hover: rgba(255, 255, 255, 0.08);
}
```

### Gap

```css
--gap: 8px;
```

Controls the spacing between the floating Spotify glass panels.

| Value | Appearance |
|---|---|
| 4px | Compact |
| 8px | Current configuration |
| 12px | Spacious |

### Corner Radius

```css
--radius: 18px;
```

Controls the common corner radius of the glass panels.

| Value | Appearance |
|---|---|
| 10px | Subtle |
| 18px | Current configuration |
| 24px | Very rounded |

### Glass Background

```css
--glass-bg: rgba(43, 57, 70, 0.14);
```

The last value controls opacity.

For example:

```css
rgba(43, 57, 70, 0.10)
```

Creates a more transparent appearance.

```css
rgba(43, 57, 70, 0.40)
```

Creates a more opaque appearance.

### Glass Blur

```css
--glass-blur: 10px;
```

Controls the blur applied behind the glass panels.

Higher values create stronger blur.

### Saturation

```css
--glass-sat: 130%;
```

Controls saturation applied through the backdrop filter.

### Glass Border

```css
--glass-border: rgba(255, 255, 255, 0.18);
```

Controls the brightness and transparency of the glass outline.

### Hover Background

```css
--glass-hover: rgba(255, 255, 255, 0.08);
```

Controls the highlight shown when hovering over supported elements.

### Additional Layout Variables

```css
--topbar-h: 64px;
--playerbar-h: 90px;
```

These values are used for top bar and bottom player layout spacing.

---

## 8.2 Misty Forest

### Configuration Files

```text
spotify/Misty-Forest/
├── color.ini
└── user.css
```

Misty Forest uses a separate green-tinted palette and glass styling system.

### Color Configuration

```ini
[LiquidGlass]
main = 081714
sidebar = 07130F
player = 081714
card = 163329
shadow = 000000
selected-row = 25493C
button = 9FD8B7
button-active = BDEBD0
text = F2F7F2
subtext = BCCFC4
```

| Variable | Current Value | Effect |
|---|---|---|
| main | `081714` | Main background color |
| sidebar | `07130F` | Sidebar color |
| player | `081714` | Player background |
| card | `163329` | Card background |
| shadow | `000000` | Shadow color |
| selected-row | `25493C` | Selected track background |
| button | `9FD8B7` | Mint button accent |
| button-active | `BDEBD0` | Active button accent |
| text | `F2F7F2` | Main text |
| subtext | `BCCFC4` | Secondary text |

### Panel Background Variables

The `user.css` defines separate background colors for the main Spotify panels.

```css
--panel-top:    rgba(9, 44, 25, 0.5);
--panel-nav:    rgba(9, 44, 25, 0.52);
--panel-main:   rgba(9, 44, 25, 0.48);
--panel-right:  rgba(9, 44, 25, 0.52);
--panel-player: rgba(9, 44, 25, 0.56);
```

| Variable | Effect |
|---|---|
| `--panel-top` | Top bar background |
| `--panel-nav` | Navigation panel background |
| `--panel-main` | Main content background |
| `--panel-right` | Right sidebar background |
| `--panel-player` | Bottom player background |

Changing the alpha component adjusts panel opacity.

### Corner Radius

```css
--radius: 22px;
```

Controls the common rounding of the glass panels.

### Gap

```css
--gap: 8px;
```

Controls spacing between the floating panels.

### Glass Blur

```css
--glass-blur: 25px;
```

Controls backdrop blur intensity.

Higher values create stronger background softening.

### Saturation

```css
--glass-sat: 180%;
```

Controls saturation behind the translucent panels.

### Glass Borders

```css
--glass-border: rgba(225, 250, 235, 0.26);
--glass-border-soft: rgba(225, 250, 235, 0.16);
```

These variables control the stronger and softer glass outlines.

### Glass Accents

```css
--glass-accent: #a9e6c3;
--glass-text: #f6fbf7;
--glass-muted: #c6d9ce;
```

| Variable | Effect |
|---|---|
| `--glass-accent` | Mint accent color |
| `--glass-text` | Main text color |
| `--glass-muted` | Secondary text color |

### Glass Tiles and Cards

```css
--glass-tile: rgba(200, 245, 225, 0.10);
--glass-tile-hover: rgba(200, 245, 225, 0.18);

--glass-card: rgba(200, 245, 225, 0.09);
--glass-card-hover: rgba(200, 245, 225, 0.17);
```

These variables control the appearance of tiles and cards, including their hover states.

### Glass Sections and Fields

```css
--glass-section: rgba(200, 245, 225, 0.08);
--glass-field: rgba(8, 28, 23, 0.34);
```

These control section backgrounds and input fields.

### Glass Chips

```css
--glass-chip: rgba(200, 245, 225, 0.13);
--glass-chip-hover: rgba(200, 245, 225, 0.22);
```

Controls the appearance of chip-style controls and their hover states.

### Hover Background

```css
--glass-hover: rgba(210, 255, 235, 0.14);
```

Controls the general hover highlight.

### Spotify Theme Selection

The two themes can remain installed simultaneously.

To select Liquid Glass:

```powershell
spicetify config current_theme Liquid-Glass
spicetify apply
```

To select Misty Forest:

```powershell
spicetify config current_theme Misty-Forest
spicetify apply
```

Only one theme is active at a time.

---

# 9. Fluent Flyouts

### Configuration

```text
configs/Fluent Flyouts/FluentFlyout_Settings.xml
```

The XML configuration contains the Fluent Flyouts application settings.

The available options depend on the installed Fluent Flyouts version.

### Configuration Areas

The settings file includes configuration for:

- Media flyout
- Media flyout blur
- Acrylic media window
- Acrylic Next Up window
- Acrylic Lock Keys window
- Taskbar widget
- Taskbar widget blur
- Taskbar widget controls
- Taskbar visualizer

Modify the corresponding XML values to customize supported features.

Keep the XML structure intact when editing the file.

---

# 10. Customization Tips

## Increase Taskbar Rounding

Change the taskbar configuration:

```yaml
- CornerRadius=20
```

For example:

```yaml
- CornerRadius=28
```

## Increase Taskbar Height

Change:

```yaml
TaskbarHeight: 62
```

To:

```yaml
TaskbarHeight: 70
```

Check the taskbar margins after changing its height.

## Change YASB Background

In `configs/yasb/styles.css`, modify:

```css
--crust: rgba(15, 30, 45, 0.3);
```

## Change Spotify Background Opacity

For Liquid Glass, modify:

```css
--glass-bg: rgba(43, 57, 70, 0.14);
```

For Misty Forest, modify the relevant panel variables:

```css
--panel-top: rgba(9, 44, 25, 0.5);
```

## Increase Spotify Glass Blur

Liquid Glass:

```css
--glass-blur: 10px;
```

Misty Forest:

```css
--glass-blur: 25px;
```

Increase the value for stronger blur.

## Increase Spotify Corner Rounding

Liquid Glass:

```css
--radius: 18px;
```

Misty Forest:

```css
--radius: 22px;
```

## Reduce Panel Spacing

Both Spotify variants use:

```css
--gap: 8px;
```

Change to:

```css
--gap: 4px;
```

## Increase Panel Spacing

Change to:

```css
--gap: 12px;
```

## Important

Change one group of values at a time.

After changing a configuration:

1. Save the file.
2. Apply or reload the corresponding mod/application.
3. Check the result.
4. Keep a backup of the previous working version.

Do not modify several independent components simultaneously when troubleshooting. This makes it difficult to identify which change caused a problem.