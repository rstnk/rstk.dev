---
title: "macOS Setup"
date: 2026-06-27
description: "macOS setup"
categories: ["personal"]
tags: ["tech"]
---

I want to use this post as reference for setting up my macOS environment from scratch. Things like default settings, modifications, installations, etc. Time will tell, but hopefully I have captured everything.

---

## System Settings

- iCloud
  - Sign into iCloud account
  - Drive: Disable Desktop & Document Folders

- Accessibility
  - Display: Shake mouse pointer to locate: Disable
  - Increase contrast: Enable
  - Display: Reduce transparency: Enable
  - Differentiate without color: Enable

- Appearance
  - Liquid Glass: Tinted
  - Windows: Sidebar icon size: Small
  - Show scroll bars: Always
  - Click in the scroll bar to: Jump to spot that's clicked

- Apple Intelligence & Siri
  - Disable Apple Intelligence
  - Disable Siri

- Desktop & Dock
  - Position: Left
  - Minimize windows: Genie Effect
  - Double-click a window title: Do Nothing
  - Minimize windows into application icon: Disable
  - Automatically hide and show the Dock: Enable
  - Show suggested and recent apps in Dock: Disable
  - Desktop & Storage Manager: Show items: On Desktop
  - Stage Manager: Disable
  - Widgets: Disable
  - Hot Corners: top-right: Mission Control, bottom-right: Desktop

- Menu Bar
  - Hide everything

- Spotlight
  - Help Apple Improve Search: Disable
  - Disable Spotlight for everything except Applications, Calculator, and System Settings

- Notifications
  - Turn off notifications for everything

- Game Center
  - Disable

- Keyboard
  - Key repeat rate: fastest
  - Delay until repeat: shortest
  - Press fn key to: Do Nothing

- Trackpad
  - Tracking speed: 70%
  - Look up & data detection: Disable
  - Secondary click: Click or Tab with Two Fingers
  - Tab to click: enable
  - Natural scrolling: Disable
  - Secondary click: Right Side
  - Smart zoom: Disable
  - Notification Center: Disable
  - Mission Contro: Swipe Up with Four Fingers
  - Show Desktop: Disable

## Finder Settings

- Toolbar: Back/Forward, Path, Search
- View as columns
- Sort by name
- Hide folders with `chflags hidden <directory>`

- General
  - Show these items on desktop: External disks
  - New Finder windows show: $HOME

- Tags
  - Turn off everything

- Sidebar
  - Show these items in the sidebar: AirDrop, Applications, Desktop, Downloads, $HOME, External disks
  - Recent Tags: Disable

- Advanced
  - Uncheck everything except
    - Show all filename extensions: Enable
    - Keep folders on top: In windows when sorting by name
  - When performing a search: Search This Mac

## Software

- [1Password](https://1password.com/): Password manager
- [Acorn](https://flyingmeat.com/acorn/): Image editor
- [Firefox](https://www.mozilla.org/en-US/firefox/): Web browser
- [Ghostty](https://github.com/ghostty-org/ghostty): Terminal emulator
- [IINA](https://github.com/iina/iina): Media player
- [Itsycal](https://github.com/sfsam/Itsycal): Menu bar calendar
- [Keka](https://github.com/aonez/Keka): Archive manager
- [Jot](https://jot.arunbrahma.com/): Menu bar scratchpad
- [Little Snitch](https://www.obdev.at/products/littlesnitch/): Network monitor
- [mdv](https://www.mowglii.com/mdv/): Markdown viewer and Preview pane extension
- [Mullvad VPN](https://mullvad.net/en): VPN service
- [Rectangle Pro](https://rectangleapp.com/pro): Window manager
- [Sublime Text](https://www.sublimetext.com/): Text editor
- [Swinsian](https://swinsian.com/): Music player
- [Zed](https://zed.dev/): Code editor

## Terminal

Install [Homebrew](https://brew.sh/) and packages:

- 1password-cli: Command-line interface for 1Password
- atuin: Improved shell history for zsh, bash, fish and nushell
- claude-code (--cask): Terminal-based AI coding assistant
- duckdb: Embeddable SQL OLAP Database Management System
- exiftool: Perl lib for reading and writing EXIF metadata
- eza: Modern, maintained replacement for ls
- f2: Command-line batch renaming tool
- ffmpeg: Play, record, convert, and stream audio and video
- gh: GitHub command-line tool
- git: Distributed revision control system
- imagemagick: Tools and libraries to manipulate images in many formats
- lftp: Sophisticated file transfer program
- magic-wormhole: Securely transfers data between computers
- neovim: Ambitious Vim-fork focused on extensibility and agility
- pandoc: Swiss-army knife of markup format conversion
- serie: Rich git commit graph in your terminal
- starship: Cross-shell prompt for astronauts
- wget: Internet file retriever
- yadm: Yet Another Dotfiles Manager
- yt-dlp: Feature-rich command-line audio/video downloader

## Programming

- Xcode will be installed as part of `brew`
- Disable accented character when holding down keys:
  - `defaults write -g ApplePressAndHoldEnabled -bool false`
- Compact menu bar items:
  - `defaults -currentHost write -globalDomain NSStatusItemSpacing -int 2`
  - `defaults -currentHost write -globalDomain NSStatusItemSelectionPadding -int 2`
- [Go](https://go.dev/dl): Go Programming language
- [uv](https://docs.astral.sh/uv/), [ruff](https://docs.astral.sh/ruff/), and [ty](https://docs.astral.sh/ty/): Python tools
- Go tools
  - Update Go tools: `goup` (custom function in the .zfunc file)

## SSH Key and Github

- Generate a new SSH key in [1Password](https://support.1password.com/developer/)
- Add public keys to Github (both Authentication and Signing key types) and sourcehut
- Test connection with `ssh -T git@github.com` and `ssh -T git@git.sr.ht`

## Firefox

- Enable Firefox Sync for bookmarks, addons, and settings
  - Extensions: [Kagi](https://github.com/kagisearch/browser_extensions), [Temporary Containers](https://github.com/stoically/temporary-containers), [uBlock Origin](https://github.com/gorhill/uBlock), [Vimium](https://github.com/philc/vimium)

## Configs

My user settings are either synced in the program or through [yadm](https://github.com/yadm-dev/yadm), which is stored on my private Github repo.

- 1Password for keys, tokens, licenses, etc
- Clone the dotfile repo for settings and configs (.zsh*, .zfunc/, .config/, etc)

## Themes

- eza: [Custom minimal theme](https://gist.github.com/pymk/9a3591e5ada0e964b4e5b5b744fcb85b)
- Ghostty: Default theme with [custom minimal Starship config](https://gist.github.com/pymk/799c73d87fdb11984d79642f42b4cf65)
- Neovim: [One Dark](https://github.com/navarasu/onedark.nvim)
- Zed: [Custom theme](https://github.com/rstnk/zed-theme-go/tree/main)

## Misc

- Prevents npm from automatically running lifecycle scripts: `echo 'ignore-scripts=true' > ~/.npmrc`
