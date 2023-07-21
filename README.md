# rofi-ykman

YubiKey OATH integration for Rofi

## Dependencies

- [ykman](https://github.com/Yubico/yubikey-manager)
- [Rofi](https://github.com/davatorium/rofi)
- [Bash](https://www.gnu.org/software/bash/)
- [xclip](https://github.com/astrand/xclip) for X11 clipboard support (optional)
- [xdotool](https://github.com/jordansissel/xdotool) for X11 typing support (optional)
- [wl-clipboard](https://github.com/bugaevc/wl-clipboard) for Wayland clipboard support (optional)
- [wtype](https://github.com/atx/wtype) for Wayland typing support (optional)
- [libnotify](https://gitlab.gnome.org/GNOME/libnotify) and a suitable [notification server](https://wiki.archlinux.org/title/Desktop_notifications#Notification_servers) for showing notifications (optional)

## Usage

```
Usage: rofi-ykman [command]

Commands:
  clipboard   Copy the code to the clipboard (default).
  type        Type the code.
```

When selecting an an entry, the code will by copied to the clipboard or typed, depending on the selected command. Alternatively, you can use one of the shortcuts to choose a different command dynamically:

| Shortcut | Command     |
| -------- | ----------- |
| `Alt+1`  | `type`      |
| `Alt+2`  | `clipboard` |

### Usage in [i3](https://i3wm.org/) or [Sway](https://swaywm.org/)

Assuming you have copied this script to `~/.config/rofi/rofi-ykman`, add this to your i3 or Sway config:

```
bindsym --release $mod+o exec --no-startup-id "~/.config/rofi/rofi-ykman"
```

When you press `$mod+o`, you will see a Rofi prompt listing available TOTP accounts. Choose one and the code will be copied to your clipboard. If you forgot to insert YubiKey, you'll get a notification saying so.

You are of course free to put the script in a different location or use a different keybinding.
