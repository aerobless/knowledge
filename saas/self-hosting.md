# 📀 Self-Hosting

## Finance

* [Firefly III](https://firefly-iii.org/): A free and open source personal finance manager. Can be installed via Yunohost, Unraid or via docker compose. Is inteded to track expenses & budgets, doesn't track investments, stocks etc.
* [Ghostfol.io](https://ghostfol.io/en/home/overview): Open source wealth management software by a swiss developer. Focused on investments, stocks etc. Complementary to Firefly. Can be installed via unraid or docker compose. Is also available as SaaS version free & paid. Still relatively new and therefor unproven how long it will stay around. I don't use this yet because it's not supported by Yunohost and setting it up would be a bit manual work. But it looks good.

## (Browser) Start Page

A page containing bookmarks and useful information when you're opening a new tab in a browser.

* [Homepage](https://github.com/benphelps/homepage): dockerised home page with support for a bunch of services such as plex, adguard, sonar etc. - looks nice, but since I don't currently have the infrastructure to easily run docker containers I'm not using it (yet)
* [Static Marks](https://github.com/darekkay/static-marks): Static site generator for a bookmarks start page. There's a github pipeline available that lets you easily edit your bookmarks.yaml & re-generate the home page. I'm currently using this for my start page on all browsers.
  * I've also made a [raycast extension](https://www.raycast.com/aerobless/static-marks#readme) for it. So the same yaml file can be used to easily access your bookmarks via [raycast](../operating-systems/macos.md#useful-apps).

## Server software

* [Proxmox VE](../operating-systems/proxmox-ve.md): open source virtualisation platform
* [Yunohost](https://yunohost.org/): Base Image to run self-hosted applications
* [Unraid OS](https://unraid.net/product): A combination of Yunohost and Proxmox. Paid OS that has a nice UI that allows the creation of VMs and installation of pre-packaged self-hosted software such as Firefly etc. One-time purchase. I don't use this, but if I had to setup a new server I would seriously consider it.

## Various

* [Reddit user washglad3114s 40 container self-hosted setup](https://www.reddit.com/r/selfhosted/comments/10wyzxh/40\_containers\_counting/?utm\_source=share\&utm\_medium=ios\_app\&utm\_name=iossmf): looks interesting, although a bit heavy on the piracy front :P
* [Awesome-Hub](https://awesomehub.js.org/list/selfhosted): Find self-hosted software for various categories.
