#### Windscribe VPN module for POLYBAR

#### Example:

Left click to Enable vpn

Right click to Disable vpn

![](demo/vpn-off.jpg)

![](demo/vpn-on.jpg)

config file to `~/.config/polybar/scripts/`

```

[module/isvpn]
type = custom/script
exec = ~/.config/polybar/scripts/isvpn.sh
interval = 2
click-left = windscribe connect
click-right = windscribe disconnect
format-prefix = "  "
format-prefix-foreground = #FFBB00
label = %output%
format-background = 
format-foreground = 

```

` chmod +x ~/.config/polybar/scripts/isvpn.sh `

### Please don't forgot paste your ip at script ->

```
#!/bin/bash

SERVICE_NAME="windscribe"

if [ "$(curl -4 -sf 2ip.io)" != "your_ip" ]
then
    echo "%{F#00ff00} $(curl -4 -sf 2ip.io)"
else
    echo "%{F#ed5858} VPN OFF"
fi

"$@"
```
