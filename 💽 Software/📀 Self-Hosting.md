
## Docker

* [Runtipi.io](https://www.runtipi.io/): Easy self-hosted platform to run docker containers. Has an app store with predefined templates and looks quite nice. I tried this and it worked nice, but when you start messing with the docker stacks yourself you can break it easily. Therefor personally I don't use it anymore, I've switched fully to managing stacks myself in Portainer. But this could be very useful for someone who doesn't want to learn about docker and just wants a really nice app store to install self-hosted software. I would totally recommend this to less technical people.
* [Portainer](https://www.portainer.io/): UI for docker & kubernetes clusters. Makes managing docker stacks easier. Personally I use a private GitHub repo for all my docker-compse and .env files. These can then be pulled into portainer where I can deploy & redeploy them. Although there's a community version for portainer, you can also just get a free business license for up to 5 environments. Should be more than enough for a small home server.

# Finance

* [Firefly III](https://firefly-iii.org/): A free and open source personal finance manager. Can be installed via Yunohost, Unraid or via docker compose. Is inteded to track expenses & budgets, doesn't track investments, stocks etc.
* [Ghostfol.io](https://ghostfol.io/en/home/overview): Open source wealth management software by a swiss developer. Focused on investments, stocks etc. Complementary to Firefly. Can be installed via unraid or docker compose. Is also available as SaaS version free & paid. Still relatively new and therefor unproven how long it will stay around. I don't use this since I'm already using the application [Portfolio Performance](https://www.portfolio-performance.info/en/) to track my investments.

# Location Tracking

- [[📍 Thereabout|Thereabout]]: A self-hosted replacement for Google Location History that I’ve developed myself. It supports importing your existing Google Location History and adding new data via [[📱 iOS#Useful apps|Overland]]. The stored data can be visualised as a heat map or day-by-day view.

# Time Tracking

* [TIMETagger](https://timetagger.app/): Can be used as SaaS or self hosted via docker. Very nice UI to manually track what you did when in a timeline fashion. Probably less useful for billing etc. there are other apps that do this.

# (Browser) Start Page

A page containing bookmarks and useful information when you're opening a new tab in a browser.

* [Homepage](https://github.com/benphelps/homepage): dockerised home page with support for a bunch of services such as plex, adguard, sonar etc. - looks nice, but since I don't currently have the infrastructure to easily run docker containers I'm not using it (yet)
* [Static Marks](https://github.com/darekkay/static-marks): Static site generator for a bookmarks start page. There's a github pipeline available that lets you easily edit your bookmarks.yaml & re-generate the home page. I'm currently using this for my start page on all browsers.
  * I've also made a [raycast extension](https://www.raycast.com/aerobless/static-marks#readme) for it. So the same yaml file can be used to easily access your bookmarks via [[💻 macOS#System utilities |Raycast]].

# Photo & media

* [Immich](https://immich.app/): High performance self-hosted photo and video management solution. It's open source and appears fairly mature. The design & usability is similar to Google Photos and it also has mobile photo backup clients. The web app itself also has some fairly advanced features like ML subject detection, geolocation of photos etc. If I ever were to migrate away from Google Photos this would likely be my number one self-hosted choice.

# Server software

* [[🐧 Linux#🧙♂ Proxmox VE |Proxmox VE]]: open source virtualisation platform
* [Yunohost](https://yunohost.org/): Base Image to run self-hosted applications
* [Unraid OS](https://unraid.net/product): A combination of Yunohost and Proxmox. Paid OS that has a nice UI that allows the creation of VMs and installation of pre-packaged self-hosted software such as Firefly etc. One-time purchase. I don't use this, but if I had to setup a new server I would seriously consider it.

## Various

* [Reddit user washglad3114s 40 container self-hosted setup](https://www.reddit.com/r/selfhosted/comments/10wyzxh/40\_containers\_counting/?utm\_source=share\&utm\_medium=ios\_app\&utm\_name=iossmf): looks interesting, although a bit heavy on the piracy front :P
* [Awesome-Hub](https://awesomehub.js.org/list/selfhosted): Find self-hosted software for various categories.
