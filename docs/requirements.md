# Requirements

This project combines several Windows customization tools and
applications. Each component can be installed independently.

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
| Spotify Theme | Spicetify |


## Fonts

YASB uses: `JetBrainsMonoNerdFontPropo-Regular.ttf`

The font is included in the repository:
```text
configs/
└── YASB/
    └── JetBrainsMonoNerdFontPropo-Regular.ttf
```
and is used by the YASB stylesheet.
```text
font-family: "JetBrainsMono NFP";
```

## Windows

The configurations in this repository are intended for Windows 11.

Compatibility may depend on the Windows build and the version of each
customization tool.

## Compatibility

Windows Updates

Windows updates may change the internal UI structure used by
Windhawk mods.

As a result, a configuration that works on one Windows build may
require modification on another build.

If a Windhawk configuration stops working after a Windows update:

- Disable the affected mod.
- Confirm that Windows itself is functioning normally.
- Check whether a newer version of the mod is available.
- Check the project's configuration for updated selectors.
- Reapply the configuration only after confirming compatibility.


## Spotify Updates

Spotify updates can affect:

- Spicetify
- CSS selectors
- Theme behavior
- CEF modifications
- Transparency
- UI layout

After a Spotify update, the Liquid Glass theme may require
reapplication or modification.

Check Spicetify compatibility before assuming that the CSS itself is broken.

## YASB Updates

YASB updates may change:

- Widget names
- Configuration syntax
- CSS selectors
- Widget behavior

Keep a backup of the previous configuration before updating YASB.

## Software Download Links

[Windhawk Official website](https://windhawk.net/)

[YASB Official GitHub](https://github.com/amnweb/yasb)

[YASB Installation Document](https://github.com/amnweb/yasb/wiki/Installation)

[YASB Latest Release](https://github.com/amnweb/yasb/releases)

[Spicetify Official website](https://spicetify.app/)

[Spicetify Installation Guide](https://spicetify.app/docs/getting-started)

[Fluent Flyouts Official GitHub](https://github.com/unchihugo/FluentFlyout)

[Fluent Flyouts Latest Release](https://github.com/unchihugo/FluentFlyout/releases)


## Important Notes

This repository contains personal Windows customization
configurations.

The configurations are not official configurations for Windows,
Windhawk, YASB, Spotify, Spicetify, or Fluent Flyouts.

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

The author is not responsible for configuration conflicts,
incompatibilities, unexpected UI behavior, application problems, or
data loss resulting from third-party customization software.

If a component causes problems, disable that component first and
restore the backed-up configuration.
