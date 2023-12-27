# 💻 macOS

## Useful Shell Commands

### Kill application on port

* Command: `lsof -ti:port | xargs kill`
* Example Usage: `lsof -ti:8049 | xargs kill`

### System information

* Fan speed, CPU temperature etc.: `sudo powermetrics`&#x20;

### SCP

* Upload: `scp filename.txt username@ipOrDomain.ch:/var/lib/location/on/server`
* Download: `scp username@ipOrDomain.ch:/var/lib/location/on/server/filename.txt ./`

### Recovery

* Boot to Recovery Mode: hold `cmd-R` during reboot
* Disable system protection to make protected changes (e.g. disable/uninstall daemons): `csrutil disable`
* Re-enable system protection: `csrutil enable`

### Homebrew Commands

* Show installed brew packages `brew list`

## System locations

* Hosts file: `../../etc/hosts`

## Format SD card

When Disk Utility does not show the full capacity of an SD card there is likely a linux partion on the there. To format the card fully the following commands can be used:

```bash
// Identify the disk with
diskutil

// Format it with
sudo diskutil eraseDisk FAT32 SDCARD MBRFormat /dev/diskNUMBER
```

## Delete Google Chrome Auto Complete Suggestion

[Select unwanted suggestion](https://superuser.com/a/835787) and press `Fn + Shift + Delete`

## Shortcuts

* Show/hide hidden files in Finder: `CMD + SHIFT + .`
* Show emoji selector: `CRTL + CMD + SPACE BAR`

## Useful apps

#### General purpose

* [Google Chrome](https://www.google.com/chrome/): Browser of choice
* [Notion](https://www.notion.so): Personal note-taking & organisation app

#### Graphics & art

* [Gifski](https://github.com/sindresorhus/Gifski): Convert videos to high-quality gifs.
* [Pixelmator Pro](https://www.pixelmator.com/pro/): All encompassing photo & image editor. I find it more user-friendly than Krita and with a price point of around 25$ it's easily worth the expense. It also includes some useful ML utilities such as removing unwanted objects, upscaling images, and automatic selection of subjects.
* [Krita](https://krita.org/en/): Free open source photoshop alternative, great for creating textures, concept art and illustrations - personally I find it more comfortable to use than GIMP. (I've stopped using this in fasvor of Pixelmator)

#### Entertainment

* [Calibre](https://calibre-ebook.com): eBook management software that can be extended with plugins. Useful to convert ebooks from various formats into the format needed for a specific ebook reader.
  * [Spotlight & Quicklook Plugin for ePub Files](https://github.com/GenjiApp/EPUB-Plugins): Allows to use macOS native spotlight & quicklook feature for ePub files.
* [VLC](https://www.videolan.org/vlc/): Universal video player
* [Spotify](https://www.spotify.com/us/download/mac/): Best music streaming service

#### System utilities

* [Rectangle](https://rectangleapp.com/): Re-size windows with keyboard commands (e.g. use half, quarter screen etc.)
* [Owly](https://apps.apple.com/us/app/owly-prevent-display-sleep/id882812218?mt=12): Prevent the mac from falling asleep, useful when streaming video to TV
* [MonitorControl](https://github.com/MonitorControl/MonitorControl): Lets me control the volume & brightness of my external monitor (connected via USB-C & Thunderbolt Dock) via the native mac keys. Normally macOS doesn't allow this making it awkward to change the audio volume when connected to the external monitor.
* [Displaperture](https://apps.apple.com/us/app/displaperture/id1543920362?mt=12): Fake rounded corners on older macbooks.
* [Scroll Reverser](https://pilotmoon.com/scrollreverser/): Lets you change the scroll behaviour of mice to be in line with e.g. Windows. Useful if you often have to switch between multiple OS and it throws you off.
* [Raycast](https://www.raycast.com/): Spotlight replacement with tons of extensions. Useful to integrate e.g. with Notion or similar applications that can't be searched via spotlight. It also has tons of quality of life utilities, e.g. killing apps, opening quick links, notes etc.
  * [Static Marks - Bookmark Search for Raycast](https://www.raycast.com/aerobless/static-marks#readme)
* [Tailscale](https://tailscale.com/): Wireguard-based VPN service, available on the mac appstore

#### Development

* [Visual Studio Code](https://code.visualstudio.com): Free text editor/mini IDE of choice when not using IntelliJ.
* [iTerm2](https://www.iterm2.com): Terminal replacement
* [Homebrew](http://brew.sh): Packet manager, like apt-get on linux, simplifies installing development dependencies etc. Note 12.2022: I'm not a huge fan of this anymore, Homebrew appears to compile a lot of stuff on device and this takes too much time imho. Manual installs are often faster.. which kinda defeats the purpose for me to use a package manager.
* [IntelliJ IDEA](https://www.jetbrains.com/idea/): Java & Kotlin IDE from Jetbrains
* [CotEditor](https://coteditor.com/): Simple text editor

#### Various

* [Anki](https://apps.ankiweb.net): Flash card manager to learn vocabulary etc. It supports syncing with a web-based version and has algorithms for learning. It's also available for windows, linux and mobile. Although the mobile client is not free.

## Tricks

* [Disable Device Enrollment Program (DEP)](https://gist.github.com/henrik242/65d26a7deca30bdb9828e183809690bd): Allows dual booting mac OS on a enrolled mac
  * `gdmf.apple.com` needs to be re-enabled for macOS updates

## OS files .gitignore

{% @github-files/github-code-block %}
