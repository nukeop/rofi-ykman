# rofi-ykman
Yubikey manager script for rofi

## Dependencies
* ykman for Yubikey
* rofi
* xclip
* libnotify client for showing notifications (optional)

## Usage
Assuming you copy this script to ~/.config/rofi/rofi-ykman, add this to your i3 config:
```
bindsym --release $mod+o exec --no-startup-id "~/.config/rofi/rofi-ykman"
```

After pressing $mod+o, you will see a rofi prompt listing available TOTP keys. Choose one and the code will be copied to your clipboard. If you forgot to insert yubikey, you'll get a notification saying so.
