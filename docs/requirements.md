# Requirements

This project combines several Windows customization tools and applications. Each component can be installed independently depending on the customization features you want to use.

## Core Requirements

| Component | Required Software |
|---|---|
| Taskbar | Windhawk + Windows 11 Taskbar Styler |
| Start Menu | Windhawk + Windows 11 Start Menu Styler |
| File Explorer | Windhawk + Windows 11 File Explorer Styler |
| Windows Transparency | Windhawk + Translucent Windows |
| Taskbar Animation | Windhawk + Taskbar Dock Animation |
| Taskbar Size | Windhawk + Taskbar height and icon size |
| Spotify CEF Tweaks | Windhawk + CEF Spotify Tweaks |
| System Flyouts | Fluent Flyouts |
| Top Bar | YASB |
| Spotify Theme | Spotify Desktop + Spicetify |

## Fonts

YASB uses:

`JetBrainsMonoNerdFontPropo-Regular.ttf`

The font is included in the repository:

```text
assets/
└── fonts/
    └── JetBrainsMonoNerdFontPropo-Regular.ttf
```

The font is used by the YASB stylesheet.

```css
font-family: "JetBrainsMono NFP";
```

Install the font before applying the YASB configuration if it is not already available on your system.

## Windows

The configurations in this repository are intended for Windows 11.

Compatibility may depend on the Windows build and the version of each customization tool.

## Compatibility

### Windows Updates

Windows updates may change the internal UI structure used by Windhawk mods.

As a result, a configuration that works on one Windows build may require modification on another build.

If a Windhawk configuration stops working after a Windows update:

- Disable the affected mod.
- Confirm that Windows itself is functioning normally.
- Check whether a newer version of the mod is available.
- Check the project's configuration for updated selectors.
- Reapply the configuration only after confirming compatibility.

### Spotify Updates

Spotify updates can affect:

- Spicetify
- CSS selectors
- Theme behavior
- CEF modifications
- Transparency
- UI layout

This repository includes two Spotify Liquid Glass theme variants:

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

**Liquid Glass**

A dark translucent Spotify interface featuring floating glass panels, rounded controls, subtle borders, and customized backgrounds.

**Misty Forest**

A forest-inspired Spotify appearance featuring green-tinted glass surfaces, mint accents, enhanced blur, and diagonal glass highlights.

Each variant has its own independent `color.ini` and `user.css` configuration.

After a Spotify update, either theme may require reapplication or modification.

Check Spicetify compatibility before assuming that the CSS itself is broken.

### YASB Updates

YASB updates may change:

- Widget names
- Configuration syntax
- CSS selectors
- Widget behavior

Keep a backup of the previous configuration before updating YASB.

## Software Download Links

### Windhawk

[Windhawk Official Website](https://windhawk.net/)

### YASB

[YASB Official GitHub](https://github.com/amnweb/yasb)

[YASB Installation Document](https://github.com/amnweb/yasb/wiki/Installation)

[YASB Latest Release](https://github.com/amnweb/yasb/releases)

### Spicetify

[Spicetify Official Website](https://spicetify.app/)

[Spicetify Installation Guide](https://spicetify.app/docs/getting-started)

### Fluent Flyouts

[Fluent Flyouts Official GitHub](https://github.com/unchihugo/FluentFlyout)

[Fluent Flyouts Latest Release](https://github.com/unchihugo/FluentFlyout/releases)

## Important Notes

This repository contains personal Windows customization configurations.

The configurations are not official configurations for Windows, Windhawk, YASB, Spotify, Spicetify, or Fluent Flyouts.

Compatibility may change due to:

- Windows updates
- Windows UI changes
- Spotify updates
- Spicetify updates
- YASB updates
- Windhawk mod updates
- Third-party software updates

Always maintain a backup of your original configuration.

## Disclaimer

Use these configurations at your own discretion.

The author is not responsible for configuration conflicts, incompatibilities, unexpected UI behavior, application problems, or data loss resulting from third-party customization software.

If a component causes problems, disable that component first and restore the backed-up configuration.