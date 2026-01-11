# hyprland-conf

**NOTE**: If you have not updated Hyprland to version 0.53.0 (late Dec 2025), the syntax for the window rules in ```~/.config/hypr/hyprland.conf``` will be different, as well as the syntax for hyprpaper, which is used to display the wallpaper. Update your system or uncomment the old syntax to resolve the errors.

## Configuration

To open your hyprland configuration in your editor of choice (I will use nvim in this example), enter the following into your terminal
```
nvim ~/.config/hypr/hyprland.conf
```

I use hyprpaper to display my wallpaper. If you do not already have this installed, you can install it on Arch by entering
```
sudo pacman -S hyprpaper
```

And the config is located at
```
~/.config/hypr/hyprpaper.conf
```

Edit your hyprpaper config to match the following syntax
```
wallpaper {
    monitor = ...
    path = ~/path/to/my/wallpaper
}
```
My wallpaper is in [this repository](https://github.com/sonatatatina/hyprland-conf/blob/main/Wallpapers/snowy-map.png), but any wallpaper matching the catppuccin mocha color scheme will work well with this configuration. Download your wallpaper, place it in a folder, and copy the exact path to that folder above. 

You can copy my [hyprland configuration](https://github.com/sonatatatina/hyprland-conf/blob/main/hyprland.conf) to ```~/.config/hypr/hyprland.conf``` and the ```exec-once = hyprpaper``` line will display your wallpaper on startup. The other wallpaper in that folder is the background I use for Firefox, which you can edit directly in your browser with ease.

If you are not on a desktop and do not need to control the LEDs on your fans, you can delete the line ```exec-once = openrgb -p keyboard_match```

## fastfetch

To install (arch):
```
sudo pacman -S fastfetch
```

Generate basic config:
```
fastfetch --gen-config
```

To use my configuration, open the default config in your editor of choice and replace the default config.jsonc with [mine](https://github.com/sonatatatina/hyprland-conf/blob/main/fastfetch/config.jsonc). To open in nvim, for example
```
nvim ~/.config/fastfetch/config.jsonc
```
To use a different image for your logo than the one I've included, change the  ```"source": "~/.config/fastfetch/logo/sephiroth.png",``` line in config.jsonc to the path for whichever image you would like to use, and tweak the height, width, padding, etc. accordingly. To use the default logo, change ```"type":``` from ```"kitty-direct"``` to ```"auto"``` and ```"source":``` to ```"arch"```.


**NOTE:** If the icons for the modules do not properly render on your device, select your own suitable icons for widgets [here](https://emojicombos.com/).

## kitty 

This terminal theme uses the catppuccin mocha color scheme and the Iosevka Nerd Font. Prior to configuring you must install this font, or any nerd font of your choosing [here](https://www.nerdfonts.com/font-downloads). 

Ensure that the font is properly unzipped and placed in the correct directory, otherwise the default font will be used instead. 

If you would not like a transparent-blurred terminal, delete the following lines
```
background_opacity 0.8
background_blur 1
```

## waybar 

To install (arch):
```
sudo pacman -S waybar
```

This includes two files by default, ```config.jsonc``` and ```style.css```. The modules being displayed are selected in the ```config.jsonc``` and styled in ```style.css```. 

If you choose to use the default waybar configuration or make your own, be sure to replace the ```sway``` with ```hyprland``` in the lines in your config that look like
```
"modules-left": ["hyprland/workspaces"],
```

The modules in this configuration are well suited for a desktop, and so you may want to add your own if you are on a laptop. 

Note that the syntax in the ```style.css``` used to ```@define-color``` may be outdated on some systems, and you may have to assign colors manually from that palette, rather than using this shorthand.

**NOTE:** If the icons for the modules do not properly render on your device, select your own suitable icons for widgets [here](https://emojicombos.com/).

## nvim 

My nvim configuration is a fork of kickstart.nvim, and is in a [separate repository](https://github.com/sonatatatina/kickstart.nvim).

This config is also catppuccin themed and (for now) suited primarily for LaTeX, python, and app development with Tauri. It is a fairly minimal config, and I have not yet updated this repo to reflect the changes made to this configuration.

## rofi 

I use rofi to quickly load various applications without having to use the command line. My configuration is from [https://github.com/catppuccin/rofi](https://github.com/catppuccin/rofi), and I have not edited it beyond that. I strongly recommend you use this, as it will make your life a lot easier.

