# Ramblings about the Steam Deck

About two weeks ago, I've finally gotten my Steam Deck. Now, I'm gonna ramble about it for a bit.

## Package contents and initial impressions

The package contained Steam Deck inside a protective case, 45W USB-C PD charging brick with a captive cable, cleaning cloth (hear this Apple - Valve is giving them out for free) and a small bag for the charger.

The case is sturdy - I have no trouble believing it'll protect my Deck whiel I cart it around with me. It also has a recess for storing the charging brick. Unfortunately, whoever designed the case only took into account the shape of US plugs. I live in Poland, which has slightly larger plugs - it still fits, but creates a bulge in the bottom of the case, not allowing it to lie flat. You know what does fit perfectly in its place, though? USB-C hub I bought - [Anker PowerExpand+ 7-in-1 A8346](https://us.anker.com/collections/hubs/products/a8346). So that's something. 

One more thing about the charging brick - I wish it did not have a captive cable. It looks thick and durable, but we all know that cables tend to get damaged and in cases such as this dead cable equals dead brick. At least it won't be hard to find a replacement. I tested [Anker PowerPort III 65W Pod](https://www.amazon.com/dp/B086YGHRNP) along with [Apple's Official 2m USB-C to USB-C cable](https://www.apple.com/shop/product/MLL82AM/A/usb-c-charge-cable-2-m) and they charged my Steam Deck without any problems.

## First boot and setup

I plugged in the Deck's charger, powered the Deck up, did most of the initial configuration - which included connecting to my Wi-Fi 5 network - and watched it update and restart. Once it booted up again I had to do the configuration again, but luckily the device remembered settings I inputted previously. Then it updated - again - and said it was gonna restart, but shut down instead. I was scared for a minute, but luckily it turned on without any issues. This time I was asked to log in to Steam. Login failed with error code 53. I tried a couple more times, but to no avail. After a bit of Googling I found out that this may be a network issue and remembered that a yellow exclamation mark kept showin up on top of the network status during my login attempts. I switched to Wi-Fi 4 and this time managed to completed the process.

## Wi-Fi issues

This feels like a good place to talk about the Steam Deck's Wi-Fi issues. It seems that the device has a power saving setting, which - when enabled - is supposed to put Wi-Fi to sleep to conserve battery when the DEck is not being actively used. Unfortunately it doesn't work right - and is enabled by default. Other than preventing me from logging in, this setting also causes downloading games and syncing saves with the Steam Cloud to fail. What's even worse there's no way to disable it from the settings app in desktop mode and in gaming mode it's hidden under developer's settings tab. And yes, Wi-Fi 4 works better than 5, bu the issues are still present. Hopefully Valve will fix this mess soon - if they haven't already.

## Installing software

Steam Deck comes with SteamOS 3 - and Steam itself - preinstalled. The only programs that can be installed in gaming mode are apps from Steam store - obviously. If there's an SD card present, Steam will detect it and setup a second library. The default library can be easily switched in the settings. Attempting to install game not marked as fully supported will result in a warning, but it is possible. What is not possible is choosing which library the game is to be installed in. If there's an SD card present, the game will be installed there - but it can be moved to the SSD once the installation is complete. The only way to install directly to the SSD, while the SD card is present, is to switch to desktop mode and use desktop version of Steam client.

There are initially 4 ways of installing software in desktop mode: [pacman](https://archlinux.org/pacman/), [FlatPak](https://flatpak.org/) store, [AppImages](https://appimage.org/), and using Steam client. `pacman` is effectively disabled by default - trying to use it will result in failure to validate downloaded software packages due to missing GPG keys. Installing those keys isn't hard - if one knows what they're doing - but it won't make `pacman` work: this time it'll complain about the read-only file system. Of course it's posbile to enable writing, but Valve warns that due to the way SteamOS update process works all changes will be lost after a system update. FlatPak store works like Apple AppStore or Microsoft Store - except, of course, that all applications there are free. AppImages are not installed _per se_ - you need to download them and put the somewhere in your home directory - I put mine in `~/Applications`. The very first one I installed is [appimaged](https://github.com/probonopd/go-appimage/tree/master/src/appimaged), which is supposed to help manage the others, but I'm not sure it's doing anything - it's not designed for SteamOS. On the other hand, those AppImages I have do show in the start menu and I didn't put them there manually, so either `appimaged` did or there's something else baked in the OS.

## Afterword

That's it for now. If you read this far and are intersted in more of my ramblings, let me know in the comments.