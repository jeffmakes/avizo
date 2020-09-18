# Avizo

Avizo is a simple notification daemon, mainly intended to be used for multimedia keys for example with Sway.

![Screenshot of Avizo's volume notification](https://raw.githubusercontent.com/misterdanb/avizo/master/github/screenshot.png)

## Sway config

```
bindsym XF86AudioRaiseVolume exec volumectl raise
bindsym XF86AudioLowerVolume exec volumectl lower
bindsym XF86AudioMute exec volumectl mute

bindsym XF86MonBrightnessUp exec lightctl raise
bindsym XF86MonBrightnessDown exec lightctl lower

for_window [app_id="avizo-service"] border pixel 0
for_window [app_id="avizo-service"] sticky toggle
no_focus [app_id="avizo-service"]

exec "avizo-service"
```

## Install

### Manually

```
meson build
ninja install
```

### Arch User Repository

A package called avizo is also available in the Arch Linux User Repository.

## Jeff's modifications

* I've added some really hacky stuff to set all PA sink volumes equal to that of the default sink
* Also, the window is now highlighted with a red tint when the sink volume is >100%, so the user knows to balance it by increasing the source volume.
