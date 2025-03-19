
# Introduction
Before coming out with the succesfull rooting I have tried lot of things previously that didn't end up working out, but they made lot of sense.
So here I would like to talk aabout a few ideas of what I have tried.

## 1. Extracting the boot.img from the phone & patch it in the magisk app

The idea was to have access to the boot.img of the phone.
Once in the twrp menu I would do in the computer
```
adb shell
dd if=/dev/block/bootdevice/by-name/boot of=/sdcard/boot.img
```
and I will extract the `boot.img`. Later on I would reboot the system and go to the Magisk app, patch the boot.img so that later on I can flash my own modifyed boot.img. It never worked out because all the time it was saying the boot.img was corrupted.

## 2. Extracting the boot.img from the firmware I provided

On the internet most of the time they say that after decompressing the firmware, you will find a `boot.sin` which you would convert to `boot.img` using a tool.
The reality is that in none of the firmware I have downloaded and extracted there is a boot.img. After searching (I have pointed out in the sources section of the README.md) I found out that you you could use flashtool (the program we used to flash the firmware), in the "sin editor mode" and you could dump the raw data and the headers. The output file will be a `kernel.elf` in which you later on will rename to `boot.img`. Neigher trying to patch on magisk or trying to boot it in twrp mode was working.

## 3. Installing a custom room like lineage OS
The problem with the boot.img of device that comes by default is that it comes in a propietary format, that's why we have to use a custom `boot.img` or kernel. In the case that I never found any boot.img on the internet or wasn't able to match mine I would have actually installed lineage OS (see README.md sources at the end of the file).
I have also found kernels that weren't compiled but that is a mess compiling all yourself, I never tried that.

## 4. Other tools that I don't really understand
There are lot of tools I have downloaded that I will upload some of them to "irrelevant_files" of this repo. Most of them I get lost on the tutorials they talk about them so I never used them for anything. Some of them can be useful for some things.

