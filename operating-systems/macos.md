# 💻 macOS

## Useful Shell Commands

### Kill application on port

* Command: `lsof -ti:port | xargs kill`
* Example Usage: `lsof -ti:8080 | xargs kill`

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

``

## Delete Google Chrome Auto Complete Suggestion

[Select unwanted suggestion](https://superuser.com/a/835787) and press `Fn + Shift + Delete`

## Shortcuts

* Show/hide hidden files in Finder: `CMD + SHIFT + .`
* Show emoji selector: `CRTL + CMD + SPACE BAR`

## Useful apps

* [Visual Studio Code](https://code.visualstudio.com): Free text editor/mini IDE of choice when not using IntelliJ.
* [Rectangle](https://rectangleapp.com/): Re-size windows with keyboard commands (e.g. use half, quarter screen etc.)
* [Owly](https://apps.apple.com/us/app/owly-prevent-display-sleep/id882812218?mt=12): Prevent the mac from falling asleep, useful when streaming video to TV
* [MonitorControl](https://github.com/MonitorControl/MonitorControl): Lets me control the volume & brightness of my external monitor (connected via USB-C & Thunderbolt Dock) via the native mac keys. Normally macOS doesn't allow this making it awkward to change the audio volume when connected to the external monitor.
* [Displaperture](https://apps.apple.com/us/app/displaperture/id1543920362?mt=12): Fake rounded corners on older macbooks.
* [Scroll Reverser](https://pilotmoon.com/scrollreverser/): Lets you change the scroll behaviour of mice to be in line with e.g. Windows. Useful if you often have to switch between multiple OS and it throws you off.
* [iTerm2](https://www.iterm2.com): Terminal replacement
* [Homebrew](http://brew.sh): Packet manager, like apt-get on linux, simplifies installing development dependencies etc.
* [Google Chrome](https://www.google.com/chrome/): Browser of choice
* [Notion](https://www.notion.so): Personal note-taking & organisation app
* [Parallels](https://www.parallels.com): Although you need to buy an upgrade for almost every new version of macOS it's still the best virtualisation software for mac. I use it occasionally when I need to run windows software. It's main advantage over competitors (e.g. VirtualBox) is that it support GPU acceleration and advanced chipset virtualisation without any special configuration. It is also very well integrated into macOS. It's perfectly possible to run 3D games in a Parallels VM when necessary.
* [Anki](https://apps.ankiweb.net): Flash card manager to learn vocabulary etc. It supports syncing with a web-based version and has algorithms for learning. It's also available for windows, linux and mobile. Although the mobile client is not free.
* [Gifski](https://github.com/sindresorhus/Gifski): Convert videos to high-quality gifs.
* [Krita](https://krita.org/en/): Free open source photoshop alternative, great for creating textures, concept art and illustrations - personally I find it more comfortable to use than GIMP.
* [Calibre](https://calibre-ebook.com): eBook management software that can be extended with plugins. Useful to convert ebooks from various formats into the format needed for a specific ebook reader.
* [Raycast](https://www.raycast.com/): Spotlight replacement with tons of extensions. Useful to integrate e.g. with Notion or similar applications that can't be searched via spotlight. It also has tons of quality of life utilities, e.g. killing apps, opening quick links, notes etc.

## Tricks

* [Disable Device Enrollment Program (DEP)](https://gist.github.com/henrik242/65d26a7deca30bdb9828e183809690bd): Allows dual booting mac OS on a enrolled mac
  * `gdmf.apple.com` needs to be re-enabled for macOS updates

## OS files .gitignore

{% embed url="https://github.com/github/gitignore/blob/main/Global/macOS.gitignore" %}
