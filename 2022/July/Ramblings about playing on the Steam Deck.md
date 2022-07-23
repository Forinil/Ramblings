# Ramblings about playing on the Steam Deck
I've had my Steam Deck for a while now and I want to talk about playing games on it.

## More on buying games

In my last story, I mentioned that I could not log in to PayPal in Steam in _Gaming Mode_. Now I have an update on that.

A couple of days ago at 2 AM I've been watching one of Eric Landon's [channels](https://www.youtube.com/c/ErickLandonRPG) and decided to buy one of the games he mentioned. Steam found that suspicious for some reason and decided to ask me to log in to PayPal again. Like last time, instead of seeing a login window, I got a blank screen. This time around, however, once I pressed **B**, instead of getting back to the previous screen, I got the login window I needed. From there I finished my shopping without a problem.

I don't know if Valve made some fixes or if I got lucky this time, but apparently, it's possible to shop using PayPal payments without using _Desktop Mode_. Good to know!

Now back to scheduled content.

## Steam games

Steam games are divided into four categories, depending on their compatibility with Steam Deck:
- _Unknown_ (icon: question mark) - the game was not tested by Valve,
- _Unsupported_ (icon: diagonally crossed-out circle) - the game was tested and found not working,
- _Playable_ (icon: black letter _i_ on yellow background) - the game was tested and found playable
- but with some issues,
- _Verified_ (icon: black checkmark on a green background) - the game was tested and found 100% percent compatible with Steam Deck.

Since the Windows games use Proton to run on Linux, instead of relying on Steam Deck Verified status, one can also check [ProtonDB](https://www.protondb.com/), which is a community-driven database of reports about running games using Proton. Games are assigned one of five medals:
- _Borked_ - the game won't start or is crucially unplayable,
- _Bronze_ - the game runs, but often crashes or has issues that prevent comfortable playing
- _Silver_ - the game runs with minor issues
- _Gold_ - the game runs perfectly after some tweaks
- _Platinum_ - the game runs perfectly out-of-the-box

### The Legend of Heroes: Trails in the Sky: First Chapter

Genre: JRPG
Status: _Unsupported_
Medal: _Gold_
Playtime: the entire game
FPS: 60

At some point, I'm gonna have to write a story about this entire game series, but for now, I'm just gonna say that it's currently my favorite RPG series.

According to its status, the game should have not launched at all, but the opposite turned out to be true. Not only did I not have any trouble launching and playing it, but it even comes with an official Steam Controller profile. There were a couple of glitches, but as far as I can tell they were the result of me playing using _Turbo_ (increasing the game speed up to 6x), which the game engine - made for PSP - was not designed to handle.

Yes, this game was originally released for PSP and later ported to PC, so it's not very demanding when it comes to hardware and I expected that if it would run at all, it would run smoothly. Being a port from PSP comes with one inconvenience.

The PC version has many options that were unnecessary on PSP - graphic quality for one. Instead of remaking the in-game menu to add all those options, the developers decided to ship it with a separate configuration app. For some reason, on the Steam Deck, the resolution selector in this app does not have a scroll bar. So to get the highest possible resolution (1200x800), I had to open said selector, select the bottom-most option, close the selector, open it again and then repeat the process until I got to the very bottom.

I should also mention that this game comes with two executables: one that uses DirectX 8 and a default one that uses - I believe  - DirectX 9. I mostly played the default but checked the DX8 one and it worked without any issues as well.

I have no idea why Valve thinks this game is unplayable.

### The Legend of Heroes: Trails in the Sky: Second Chapter

Genre: JRPG
Status: _Unsupported_
Medal: _Gold_
Playtime: the entire game
FPS: 60

The second part of the trilogy is also marked as _Unsupported_ and also works without any issues. This did not surprise me as it uses the same engine as the first one. The experience I has with it was almost the same as with the previous entry in the series, so I won't repeat myself.

There is one difference though between FC and SC. The SC has a bug in a dialogue in the final chapter (the game is called _Second Chapter_ and is itself divided into chapters, confusing I know) which makes it impossible to finish it using a controller. The workaround is trivial - just use the mouse for that one interaction. Steam Deck, of course, does not come with a mouse. What it does come with is a _Mouse Only_ Steam Controller profile template and an ability to switch controller profiles on the fly. As such, once I reached the buggy conversation, it was a trivial matter to temporarily switch controller layout to _Mouse Only_, get past it, and then switch back to the official one.

Again, I have no idea why Valve marked this game as _Unsupported_.

### The Legend of Heroes: Trails in the Sky the 3rd
_See the pattern yet?_

Genre: JRPG
Status: _Verified_
Medal: _Gold_
Playtime: the entire game
FPS: 60

The only game in the trilogy that is marked as _Steam Deck Verified_ and ironically the only one that has crashed on me and had some issues with graphics - weird artifacts during a couple of animations. This game has the same cannot-finish-with-the-controller bug in chapter six that the previous one had in the final chapter. This time around I found an even simpler workaround - clicking the option using the touchscreen - no changing of controller profiles necessary. Other than that I had the same great experience as with the previous two entries in this series.

### Age of Empires II HD _aka_ Age of Empires II (2013)

Genre: RTS
Status: _Verified_
Medal: _Gold_
Playtime: None
FPS: Unknown

Valve claims it's Steam Deck _Verified_. ProtonDB gave it a _Gold_ medal. It should work great, right?

Not really. The intro cinematic does not play. The game presents a black screen with four buttons on the left and some links on the right. It is a flip of a coin if clicking on the _Play_ button works or crashes the game. Thank goodness I already had a player profile made on PC, since making one requires keyboard input and the game does not recognize the on-screen keyboard at all. I managed to launch a scenario but got quickly frustrated with the controls - Steam Deck enables the first one of the community controller profiles since there is no official one - and quit. To be fair, the controls are fully customizable, so if I wanted to, I could've probably made ones that suit me.

I tried various versions of Proton and Proton-GE to no avail. The issues persist. If the game is super-stable after that initial black screen, I can see it getting _Gold_ on ProtonDB, but how on Earth is this Deck-verified!?

### Age of Empires II Definitive Edition

Genre: RTS
Status: _Unsupported_
Medal: _Gold_
Playtime: None
FPS: Unknown

According to ProtonDB, it should run, but I can't get it to work. The furthest I got was a Microsoft account login screen.

### Conclusion

Steam verification process does not seem to be reliable at all. ProtonDB is better, but its medals denote general Linux performance and are not Steam Deck-specific. It seems the only real way to know if any given game will run - and how well - is to try it.

## Non-Steam games

I did not test any non-Steam games that require installation, only ones that can simply be unzipped. Also, rather than discuss specific titles, I'll discuss the game engines they use.

### Ren'Py

Ren'Py games generally come with three executables: _game-title.exe_ for Windows, _game-title.app_ for macOS, and _game-title.sh_ for Linux. The last one generally works out-of-the-box, but in a single case, I had to make it and various executables from the appropriate _lib_ subfolder executable. In case when the game comes without the Linux executable it is possible to run it with Proton, either by adding it to Steam or by using Proton directly, eg. with the script provided by [EmuDeck](https://www.emudeck.com/): [proton-launch.sh](https://github.com/dragoonDorise/EmuDeck/blob/main/tools/proton-launch.sh) - which can be downloaded and used separately from the rest of EmuDeck.

I found no issues with any of the games I tested, except for one instance. When trying to load a different save I accidentally clicked on the save file in the _Save game_ window and a pop-up for inputting a new save name appeared. I wanted to exit this without saving, but that would require pressing the _Escape_ key since the game's developer did not include a _Cancel_ button in the dialog for some reason. The problem was that Steam Deck's on-screen keyboard does not have an _Escape_ key... 

### RPGMaker

All RPGM games I tested come with Windows executable only. I found no problem playing either in _Desktop Mode_ using the aforementioned _proton-launch.sh_ script or in _Gaming Mode_ after adding the game Steam.

### KiriKiri

All the games I tested come from the same developer, so I can't be sure if it's the engine or developer's fault, but they all use a standard menu bar for access to options, save management, etc. As such even though they theoretically run in _Gaming Mode_ (where the menu bar does not show) I could not save or exit the game, merely click through (_KiriKiri_ is a visual novel engine). With that said, they all run without issues in _Desktop Mode_.

## Summary

Many games work flawlessly on a Steam Deck and many don't. As much as I love my Steam Deck and I love playing games on it, I think it'll be a while before it can truly replace a gaming PC.

## Afterword

That's it for now. If you read this far and are interested in more of my ramblings, let me know in the comments.
