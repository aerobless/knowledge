---
aliases:
  - obsidian
---
# My Obsidian Setup

I’ve originally used Notion for my [[💡 Knowledge Management#Second Brain|Second Brain]] and GitBook for my [[💡 Knowledge Management#Digital Garden |Digital Garden]]. So I’ve always had my private and public notes completely separate in two different apps.

But since switching to Obsidian these notes are now combined in the same application. In fact this is one of the reasons why I wanted to switch to Obsidian. It allows me to extend my private notes with public ones.

For my public notes I’ve already had a [knowledge](https://github.com/aerobless/knowledge) git repo and I wanted to continue using this - both to preserve the history of my commits and to have an alternate way of accessing my notes. So the setup I’ve ended up with looks like this:

* **/private *(Git Repo: github/aerobless/private)***
	* /FileOrganizer
	* /archive
	* /projects
	* /recordings
	* /templates
	* /topics
	* …
	* **/public  *(Git Submodule: github/aerobless/knowledge)***
		* SaaS & Web
		* Locations & Travel
		* Project Management
		* …

# Mobile Access

Currently I’m using [[📱 iOS#Useful apps|Working Copy]] to pull my private repo and public submodule from GitHub on [[📱 iOS]]. This is a bit bothersome but I’ve set up a Shortcuts Automation to pull & open Obsidian in one go.

# Important Shortcuts

- `CMD + O` Quick switcher to open any note
- `CMD + P` Execute a command
- `CMD + SHIFT + F` Global search