---
aliases:
  - obsidian
---
[Obsidian](https://obsidian.md/) is a powerful note-taking and knowledge management application that allows users to create interconnected notes using markdown, fostering a personal knowledge base through a unique graph view.

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
- `CMD + R` Reveal file in navigator

# Useful plugins

- [@ Symbol Linking](https://github.com/Ebonsignori/obsidian-at-symbol-linking): Reference to people via @ symbol, e.g. @theo. Can be restricted to a specific folder that contains all the people.
- [AI File Organizer 2000](https://github.com/different-ai/file-organizer-2000): Tags, renames, and moves files to the most appropriate folders in your vault.
- [Broken Links](https://github.com/ipshing/obsidian-broken-links): Find broken links. Especially useful when migrating from another note-taking app that may not be fully compatible with Obsidian.
- [Calendar](https://github.com/liamcain/obsidian-calendar-plugin): Adds a calendar view to the navigation panel on the right. Can be used to navigate between daily notes and create new ones for days where none exist yet.