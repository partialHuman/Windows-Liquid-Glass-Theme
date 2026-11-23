# Troubleshooting

This guide covers common problems that may occur while installing or using the Windows Liquid Glass Theme.

Because this project combines several independent customization tools, troubleshooting should normally be performed **one component at a time**.

---

# Table of Contents

1. [General Troubleshooting](#1-general-troubleshooting)
2. [Windhawk](#2-windhawk)
3. [Taskbar](#3-taskbar)
4. [Start Menu](#4-start-menu)
5. [Search](#5-search)
6. [File Explorer](#6-file-explorer)
7. [Translucent Windows](#7-translucent-windows)
8. [YASB](#8-yasb)
9. [Spotify](#9-spotify)
10. [CEF Spotify Tweaks](#10-cef-spotify-tweaks)
11. [Fluent Flyouts](#11-fluent-flyouts)
12. [Performance](#12-performance)
13. [Updates](#13-updates)
14. [Restoring the Original Configuration](#14-restoring-the-original-configuration)

---

# 1. General Troubleshooting

If something suddenly stops working:

1. Identify the affected component.
2. Disable only that component.
3. Check whether Windows/application functionality returns to normal.
4. Restore the previous working configuration.
5. Re-enable components one at a time.

Do not change multiple configuration files simultaneously while troubleshooting.

---

# 2. Windhawk

## Windhawk Mod Is Not Applying

Check:

- Windhawk is running.
- The required mod is installed.
- The mod is enabled.
- The configuration was pasted correctly.
- There are no YAML syntax errors.
- The affected application has been restarted.

Try:

```text
Windhawk
1. Open the affected mod
2. Settings
3. Save
4. Reload the mod
```

If the problem persists, disable the mod and verify that Windows works normally without it.

## Windhawk Shows an Error

If Windhawk reports an error:

1. Read the error message.
2. Check whether the affected selector still exists.
3. Check whether Windows has recently updated.
4. Check whether the Windhawk mod has received an update.
5. Restore the previous working configuration.

Do not assume that a configuration designed for one Windows build will work unchanged on every future build.

---

# 3. Taskbar

Configuration:

```text
configs/Windows 11 Taskbar Styler/taskbar-styler.yaml
```

Taskbar dimensions are controlled separately:

```text
configs/Taskbar height and icon size/taskbar-icon-size.yaml
```

## Taskbar Is Too High or Too Low

The current taskbar height is:

```yaml
TaskbarHeight: 62
```

If you change the taskbar height, you may also need to adjust the Taskbar Styler margins.

Relevant settings include:

```text
Margin
Padding
CornerRadius
```

## Taskbar Has Too Much Empty Space

Check:

```text
Margin
Padding
```

In the Taskbar Styler configuration, the main taskbar root currently uses:

```text
Margin=10,0,10,10
Padding=20,0,20,0
```

Reducing the padding can bring the task contents closer together.

## Taskbar Buttons Are Too Close Together

Check the task item:

```text
Margin=3,3.5,5,3
```

Increase the margin values to create more spacing.

## Taskbar Buttons Are Not Rounded Enough

Check:

```text
CornerRadius=10
```

Increase the value for more rounded task buttons.

## Taskbar Border Is Too Strong

The current border is:

```text
BorderBrush=#40FFFFFF
```

Reduce the alpha component:

```text
40
```

to a smaller value.

For example:

```text
#20FFFFFF
```

creates a weaker white border.

## Taskbar Background Is Not Transparent

Check:

```text
Rectangle#BackgroundStroke
```

and:

```text
Rectangle#BackgroundFill
```

The configuration intentionally uses transparent/background resource settings for these elements.

Also check whether another Windows customization tool is overriding the taskbar background.

---

# 4. Start Menu

Configuration:

```text
configs/Windows 11 Start Menu Styler/start-menu-styler.yaml
```

## Start Menu Is Too Small

Current dimensions:

```text
Width=800
Height=600
```

Increase:

```text
Width
Height
```

independently.

For example:

```text
Width=850
Height=650
```

## Start Menu Is Too Wide

Reduce:

```text
Width=800
```

to a smaller value.

Example:

```text
Width=750
```

## Start Menu Has Uneven Left/Right Spacing

Check the All Apps transform:

```text
RenderTransform:=<TranslateTransform X="-15" Y="0" />
```

The X value shifts the All Apps content horizontally.

For example:

```text
X="-15"
```

moves it to the left.

A value closer to zero moves it toward the right.

## Start Menu Has Too Much Internal Spacing

Check:

```text
Margin=0,0,0,0
```

for:

```text
RecommendedList
AllListHeading
CategoryControl
```

Also check:

```text
StartMenu.PinnedList
```

and its height.

---

# 5. Search

Search customization is contained in:

```text
configs/Windows 11 Start Menu Styler/start-menu-styler.yaml
```

There is no separate Search configuration in this repository.

## Search Window Is Too High or Too Low

Check the Search target:

```text
Cortana.UI.Views.TaskbarSearchPage
```

The configuration uses a vertical transform.

Adjust the `Y` value to move the Search window vertically.

## Search Window Is Too Wide

Adjust:

```text
Width=825
```

to the desired width.

## Search Window Is Too Short

Adjust:

```text
Height=600
```

to the desired height.

---

# 6. File Explorer

Configuration:

```text
configs/Windows 11 File Explorer Styler/file-explorer-styler.yaml
```

## Explorer Is Not Transparent

Check:

```yaml
backgroundTranslucentEffectRegion: entireWindow
```

Also check that:

- Translucent Windows is enabled if your setup depends on it.
- File Explorer Styler is enabled.
- Explorer has been restarted.

## Explorer Navigation Bar Looks Different

The navigation area is controlled by:

```text
Grid#NavigationBarControlGrid
```

Check its:

```text
Background
BorderThickness
BorderBrush
```

settings.

## Explorer Main Area Is Too Opaque

The main details area uses a Windhawk blur background.

Check:

```text
Grid#DetailsViewControlRootGrid
```

The background tint and opacity can be adjusted there.

## Explorer Borders Are Too Strong

The configuration uses white ARGB borders such as:

```text
#25FFFFFF
#40FFFFFF
```

Reduce the alpha value to make the borders weaker.

## Explorer Command Bar Is Too Sharp

The command bar currently uses:

```text
CornerRadius=2
```

Increase the value for more rounded corners.

Example:

```text
CornerRadius=8
```

---

# 7. Translucent Windows

Configuration:

```text
configs/Translucent Windows/translucent-windows.yaml
```

## Other Applications Are Becoming Transparent

Translucent Windows operates at a system/application level.

If another application is affected unexpectedly:

1. Identify the application.
2. Check the `RuledPrograms` section.
3. Add or adjust an application-specific rule if supported.
4. Test the affected application again.

Do not immediately modify the Spotify CSS to fix a problem caused by the Windows-level transparency configuration.

## Spotify Looks Different After Enabling Translucent Windows

This project contains a Spotify-specific rule in the Translucent Windows configuration.

Spotify also has its own theme configurations:

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

Both layers can affect the final appearance.

Check both configurations before changing either one.

---

# 8. YASB

Configuration:

```text
configs/yasb/config.yaml
configs/yasb/styles.css
```

Font:

```text
assets/fonts/JetBrainsMonoNerdFontPropo-Regular.ttf
```

## YASB Does Not Start

Check:

- YASB is installed.
- The configuration path is correct.
- `config.yaml` contains valid YAML.
- Required fonts are installed.
- Required widgets are available.

Try launching YASB without the custom configuration first.

If the default YASB configuration works, restore the Liquid Glass configuration and identify the problematic section.

## YASB Icons Are Missing

Install:

```text
assets/fonts/JetBrainsMonoNerdFontPropo-Regular.ttf
```

Then restart YASB.

If icons are still missing, check:

```text
font-family
```

in:

```text
configs/yasb/styles.css
```

## YASB Widgets Are Too Close Together

Check the widget padding:

```css
.widget {
    padding: 0 12px;
}
```

Increase the horizontal padding for more spacing.

## YASB Widgets Are Too Rounded

Check:

```css
border-radius: 12px;
```

Reduce the value.

## YASB Bar Is Too Opaque

Check the background of:

```css
.yasb-bar
```

and the corresponding color variable in:

```text
configs/yasb/styles.css
```

---

# 9. Spotify

Spotify customization is managed through Spicetify.

This repository contains two independent Spotify themes:

1. Liquid Glass
2. Misty Forest

Each theme has its own color configuration and CSS file.

## Theme Files

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

## Spotify Is Not Transparent

First check:

```text
Spicetify
```

Then run:

```powershell
spicetify apply
```

Restart Spotify completely.

If transparency still does not appear, check whether Spotify has updated and whether the current Spicetify version is compatible.

Also verify that the correct theme is selected.

## Spotify Theme Is Not Switching

Check the active theme:

```powershell
spicetify config current_theme
```

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

Verify that the selected theme folder exists inside:

```text
%APPDATA%\spicetify\Themes
```

Each installed theme folder should contain:

```text
color.ini
user.css
```

## Spotify Has a Strong Colored Background

The Liquid Glass main glass background is controlled by:

```css
--glass-bg: rgba(43, 57, 70, 0.14);
```

To make it more transparent:

```css
--glass-bg: rgba(43, 57, 70, 0.12);
```

To make it more opaque:

```css
--glass-bg: rgba(43, 57, 70, 0.35);
```

For Misty Forest, the panel backgrounds are controlled separately:

```css
--panel-top: rgba(9, 44, 25, 0.5);
--panel-nav: rgba(9, 44, 25, 0.52);
--panel-main: rgba(9, 44, 25, 0.48);
--panel-right: rgba(9, 44, 25, 0.52);
--panel-player: rgba(9, 44, 25, 0.56);
```

Adjust the alpha values to change the transparency of individual panels.

## Spotify Blur Is Too Strong

Liquid Glass:

```css
--glass-blur: 10px;
```

Reduce the value:

```css
--glass-blur: 6px;
```

for weaker blur.

Misty Forest:

```css
--glass-blur: 25px;
```

Reduce the value to decrease the blur strength.

## Spotify Panels Have Too Much Space Between Them

Both variants currently use:

```css
--gap: 8px;
```

Reduce it:

```css
--gap: 4px;
```

## Spotify Panels Are Too Rounded

Liquid Glass:

```css
--radius: 18px;
```

Misty Forest:

```css
--radius: 22px;
```

Reduce the corresponding value to make the panels less rounded.

## Spotify Borders Are Too Visible

Liquid Glass:

```css
--glass-border: rgba(255, 255, 255, 0.18);
```

Misty Forest:

```css
--glass-border: rgba(225, 250, 235, 0.26);
--glass-border-soft: rgba(225, 250, 235, 0.16);
```

Reduce the alpha value to make the borders weaker.

## Spotify Bottom Player Is Too Opaque

Check:

```css
.main-nowPlayingBar-container
```

For Liquid Glass, the bottom player uses the shared `--glass-bg` variable.

For Misty Forest, check:

```css
--panel-player
```

Changes to these values affect the corresponding player background.

## Spotify Top Bar Is Not Transparent

Check the selectors responsible for:

```text
Root__top-container
main-topBar-container
main-globalNav-container
```

Make sure their background is not being overridden by another CSS rule.

## Spotify Filter/Action Bar Is Still Colored

Check the selectors for the action/filter bar in the active theme's `user.css`.

The project uses separate styling for the structural action bar and its individual filter buttons.

If a Spotify update changes these selectors, the existing CSS may no longer target the correct element.

## Spotify Gradient or Glass Highlight Is Too Strong

For Liquid Glass:

1. Find the corresponding gradient/background rule in `user.css`.
2. Reduce its opacity.
3. Reduce the length of the gradient.
4. Test Spotify again.

For Misty Forest, inspect the `--sheen` and `--rim` variables and their corresponding CSS rules.

Do not remove the entire gradient unless you want the underlying Spotify background completely exposed.

---

# 10. CEF Spotify Tweaks

Configuration:

```text
configs/CEF-Spotify Tweaks/config.yaml
```

## Spotify CEF Changes Are Not Applied

Check:

- Spotify is completely closed.
- CEF Spotify Tweaks is installed in Windhawk.
- The configuration is loaded.
- Spotify has been restarted.

If Spotify recently updated, check compatibility before modifying the configuration.

---

# 11. Fluent Flyouts

Configuration:

```text
configs/Fluent Flyouts/FluentFlyout_Settings.xml
```

## Flyouts Are Not Transparent

Check the acrylic and blur settings in the Fluent Flyouts configuration.

The configuration contains settings for:

- Media Flyout
- Next Up
- Lock Keys
- Taskbar Widget

Make sure Fluent Flyouts is running.

## Flyout Blur Is Too Strong

Inspect the acrylic and blur settings in:

```text
configs/Fluent Flyouts/FluentFlyout_Settings.xml
```

The exact setting names and available controls depend on the installed Fluent Flyouts version.

Avoid changing XML element names without verifying that they exist in the installed version's configuration format.

---

# 12. Performance

If the desktop becomes less responsive after enabling all components, disable optional effects first.

Recommended order:

1. Disable Taskbar Dock Animation.
2. Disable Fluent Flyouts visualizer.
3. Reduce blur strength.
4. Reduce YASB visual effects.
5. Reduce Spotify blur.
6. Disable unnecessary widgets.

Do not disable all components simultaneously if you want to identify the source of a performance problem.

---

# 13. Updates

## Windows Updates

Windows updates can change the internal UI structure used by Windhawk mods.

After a major Windows update:

1. Check whether the Windhawk mods are still enabled.
2. Check whether the mods have updated.
3. Test Taskbar Styler.
4. Test Start Menu Styler.
5. Test File Explorer Styler.
6. Test Translucent Windows.

If only one component is broken, troubleshoot that component instead of changing the entire configuration.

## Spotify Updates

Spotify updates can affect Spicetify CSS selectors and CEF behavior.

If Spotify suddenly becomes opaque or the layout changes:

1. Check the Spotify version.
2. Check Spicetify compatibility.
3. Run:

```powershell
spicetify apply
```

4. Restart Spotify.
5. Check the active theme's `user.css` selectors.

Do not immediately replace the entire Spotify configuration.

## YASB Updates

After a YASB update:

1. Back up `config.yaml`.
2. Back up `styles.css`.
3. Start YASB with the default configuration if necessary.
4. Check widget compatibility.
5. Reapply the project configuration.

## Complete Theme Not Matching the Preview

If individual components work but the overall desktop does not look like the repository screenshots, check:

```text
Windows scaling
Windows theme
Accent color
Taskbar height
Taskbar margins
YASB bar height
Spotify zoom/scaling
Display resolution
```

The Liquid Glass appearance depends on the interaction between several independent applications.

## Conflicting Customization Tools

Avoid running multiple tools that modify the same Windows UI element.

Potential conflicts can occur when multiple applications modify:

```text
Taskbar
Start Menu
File Explorer
Window backgrounds
Spotify
```

If you experience unexpected behavior:

1. Disable other customization tools temporarily.
2. Test the Liquid Glass components.
3. Re-enable other tools one at a time.

---

# 14. Restoring the Original Configuration

If a component causes problems, restore the original configuration instead of removing the entire theme.

## Windhawk

Disable the affected Windhawk mod.

Restore the previous configuration if necessary.

## YASB

Restore:

```text
config.yaml
styles.css
```

## Spotify

Restore the original active theme files:

```text
color.ini
user.css
```

Then run:

```powershell
spicetify apply
```

if required.

If you want to return to the original Spotify theme, select its previous theme name rather than deleting the other theme variant.

## Fluent Flyouts

Restore the original:

```text
FluentFlyout_Settings.xml
```

## Emergency Recovery

If the Windows desktop becomes unusable:

1. Disable the most recently enabled customization.
2. Restart Windows Explorer.
3. If necessary, restart Windows in Safe Mode.
4. Disable the problematic customization software/mod.
5. Restore the backup configuration.

Always keep a copy of the original configurations before applying major changes.

## Reporting a Problem

When reporting an issue, include:

```text
Windows version/build:
Windhawk version:
Affected mod:
Mod version:
YASB version:
Spotify version:
Spicetify version:
Fluent Flyouts version:
Display scaling:
```

Also include:

- A screenshot of the issue
- The relevant configuration
- Any error message shown by the affected application

This makes it easier to determine whether the issue is caused by the configuration, software version, or Windows build.