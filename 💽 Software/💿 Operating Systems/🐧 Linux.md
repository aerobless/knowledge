# Useful shell commands

* Kill IntelliJ `kill -9 $(ps aux | grep intellij | awk '{print $2}')`

# Ubuntu Installation

* [Ubuntu doesn't use full disk when automatically partitioning -> resize disk](https://askubuntu.com/questions/1269493/ubuntu-server-20-04-1-lts-not-all-disk-space-was-allocated-during-installation)

# 🧙♂ Proxmox VE

Proxmox VE is a complete, open-source server management platform for enterprise virtualization. I run [Proxmox VE](https://www.proxmox.com/en/) on a Intel NUC as a host for [Home Assistant (VM install method)](🏠%20Home%20Automation.md), [Yunohost](https://yunohost.org/#/) and a Ubuntu Server based dev env.

## Download ISO image to Proxmox server

```
cd /var/lib/vz/template/iso
wget http://url/to/image.iso
```

# 🍇 Raspian

## Headless OS Setup

{% embed url="https://gist.github.com/aerobless/54ce05c092a216b6cf52b8c2946f93ba" %}

## Autostart application after boot

{% embed url="https://gist.github.com/aerobless/2c466e1643c26b2081f4ff0afec5f1a2" %}
