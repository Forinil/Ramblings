# More ramblings about the Steam Deck

Time for more ramblings about the Steam Deck.

## Desktop mode and its controls

Steam Deck can operate in two different modes: *Gaming Mode* and *Desktop Mode*. The former is essentially Valve's attempt at delivering the console experience, while the latter allows for using the device as a full-fledged PC.

The Deck boots in _Gaming Mode_. To switch to _Desktop Mode_ you need to press the _Steam_ button, select _Power_ and then _Switch to desktop_. Switching back requires clicking _Return to Gaming Mode_ shortcut on the desktop.

Yes _clicking_, not _double-clicking_, because SteamOS is set up to use single click the way most systems use double click. This is not Valve's invention. You may not be aware of it, but two of of three the major operating systems - Linux and Windows - allow switching from double to single-clicking. Mac OS X used to allow this, but my research - and by that I mean Googling it - suggests it has been removed in Catalina - if any Mac users are reading this and can confirm, please leave a comment.

Back to SteamOS - why would Valve change the default other OS'es use? Simple - Steam Deck does not come with a mouse. Unless you plug one in - via USB or Bluetooth - all you have to control the cursor is the touchscreen and the built-in Steam Controller.

The former works exactly like any other touchscreen, although it's worth noting that the desktop UI was not designed for touch input. As for the latter - the device has two touchpads. When in _Desktop Mode_, the left one only registers clicks - and reports them to the OS as right clicks, while the right one is configured to control the cursor movement and left clicks.

That's right - left-click is on the right and right-click is on the left. Sounds counterintuitive, but I got used to it quickly and it kind of makes sense to use the same finger for moving the cursor and left-clicking.

Desktop, of course, requires not just a mouse, but also a keyboard. SteamOS comes with a keyboard optimized to be used with a controller. In _Desktop Mode_ you can launch it with the _Steam+X_ shortcut. As a bonus, the keyboard also recognizes touch input, so you can type using the touchscreen as well as the touch pads.

All in all, it's not a bad experience, except for one thing - it captures all input from both the touchscreen and the controller, meaning that when the keyboard is active, the mouse does not work. So you have to keep opening the keyboard to type and closing it to click and on top of that there seems to be no way to move it, so if it obscures whatever window you're trying to type into - tough luck.

As an alternative, it is possible to use _Discover_ (the Flatpak store) to install [_CoreKeyboard_](https://flathub.org/apps/details/org.cubocore.CoreKeyboard). It does not monopolize input and can be switched between what I think of as _tablet mode_ and _phone mode_. I find it useful in certain situations but I generally use the default one, simply because it's easier to turn on.

Finally, it's worth mentioning that the built-in Steam Controller is only recognized by the operating system as long as Steam Client is running. Since it's not possible to shut it down in _Gaming Mode_ and it always runs in the background in _Desktop Mode_ it's generally not a problem. This does, however, cause an issue. There can be only one instance of Steam Client running at the time, so if you open a regular Steam Client in _Desktop Mode_, the one running in the background is shut down. If you then shut down the client, it takes the OS a couple of seconds to detect that no Steam Client is running and reboot the background one. The problem is that - at least on my Deck - the OS no longer recognizes touchpad clicks, leaving me with just the ability to move the cursor around. In other words - once you open the desktop Steam Client, keep it open until you switch back to _Gaming Mode_. 

To sum it up, it is possible to use the Steam Deck in _Desktop Mode_ with just the built-in control, but due to the UI not being designed for touch input and the default keyboard designed with _Gaming Mode_ in mind, it's not the best experience. I'd recommend plugging in a regular mouse and keyboard if you want to do more than browse the web or copy some files.

## Buying games

Everyone knows that Valve is selling Steam Decks below costs, hoping to recoup the loss on game sales - the same as console makers. One would think they'd make game buying as easy as possible. That was not my experience - at least with the first purchase.

The only payment method I ever used with Steam is my PayPal account. The way it works in a desktop client is that the first time you pay with it, Steam opens a pop-up window to log in to PayPal and configure which of the preconfigured cards you want to use. This does not work on Steam Deck - at least it did not for me. Ultimately, I had to switch to _Desktop Mode_ to finish my purchase.

The good news is that once that first purchase is out of the way, Steam Client remembers your choices, and buying games is as easy as on any other console or PC.

As a side note - I wrote in my previous story that you cannot select which drive to install the game on when installing from within the _Gaming Mode_. It turns out that I wasn't completely correct - if you install the game immediately after buying it, rather than from the library, you get to make that choice. It's weirdly inconsistent, but hopefully, Valve will fix that eventually.

## External monitors

To keep it short - Steam Deck supports external monitors. If you plug one in while in _Gaming Mode_, it'll act like Nintendo Switch - that is shut down the built-in screen and use only the external display. If you do the same in _Desktop Mode_, you'll get a popup to select if you want to use just the built-in screen, just the external screen, mirror the built-in one, or extend the desktop to the left or right. I experienced no issues with any of the monitors I used.

## Game collections

Steam gives us the possibility to group games we purchased into collections. There are two types - automatic ones that group games based on some criteria and manual ones that we have to add the games into by hand.

This functionality is not something I bothered with on the desktop version - other than setting some automatic ones to see how they work. On Steam Deck, however, I find it easier to find games in my library by using collections rather than searching for them by name. Probably since the latter requires me to use the keyboard - and I cannot type very fast unless I use the touchscreen, which then leaves me with fingerprints I have to clean.

I suspect many people would agree with me - if you do not, please tell me why in the comments - which makes the fact that there seems to be no way to add collections in _Gaming Mode_ confusing. That's right - you need a desktop Steam Client to add new collections, which means either using your PC or the Deck's _Desktop Mode_ and unless you have a mouse and keyboard plugged into the Deck, I'd recommend the former.

# VPNs

I'm sure I'm not the only person, who wanted to use a VPN on their Deck. I have good news and bad news.

Good news - VPNs are supported by the OS. Bad news - they do not work out of the box.

To configure a VPN, switch to _Desktop Mode_, open the _System Settings_ app, then go to _Connections_ and click on the _+_ button. From there you can add a VPN connection of various types or import them from a file - for some reason that last option is at the very bottom of the list in the _Other_ section. Once you do that, you can click on the Wi-Fi symbol on the taskbar. You should see your VPN on the list of available networks. Click on the _Connect_ button... and watch as a new pop-up appears informing you that you need a VPN plugin - specific for the type of VPN you want to use - for it to work.

Unfortunately, there's no way to install one without using the terminal. In my case I wanted to connect to an OpenVPN server, so I opened the _Konsole_ (Steam Deck's - well KDE's actually - terminal app) and run the following commands:

```bash
sudo pacman-key --init # Initialize the GPG keystore
sudo pacman-key --populate archlinux # Populate the keystore with standard Arch Linux keys
sudo steamos-readonly disable # Disable the read-only filesystem
sudo pacman -S networkmanager-openvpn # Install the NetworkManager's OpenVPN plugin
sudo steamos-readonly enable # Reenable the read-only file system
```

And that's it! Now I could connect to my OpenVPN server without any issues. Since the above commands change the read-only part of the filesystem, I suspect I will have to run them again after every SteamOS update.

You can learn more about NetworkManager and its plugins on its website: [networkmanager.dev](https://networkmanager.dev/).

I should also mention that to run any of the above commands, you need to set up Steam Deck's user password - it's not the same as your Steam password. To do that open the _System Settings_ app, go to _Users_, select _Steam Deck User_, and click on the _Change Password_ button. Alternatively, you can run the [`passwd`](https://man7.org/linux/man-pages/man1/passwd.1.html) command in the _Konsole_ app.

## Afterword

I think that's enough rambling for today. Please let me know in the comments if you'd like to read more.







