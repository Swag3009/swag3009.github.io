---
title: "Making Your macOS Terminal Look Awesome"
description: "I turned my macOS terminal from dull and plain to stylish and good looking and in this blog, I’ll walk you through the process of doing the same."
date: 2025-09-01
categories: ["MacOS", "Terminal", "Developer Productivity", "Customization"]
tags: ["oh-my-zsh", "oh-my-posh", "warp"]
author: Swagatika
image:
  path: "https://res.cloudinary.com/dduot1vgo/image/upload/v1756698121/Terminal_ushx7s.png"
  alt: Terminal
---

# Introduction

My first operating system was Windows and I guess that’s the case for most people. As a coder, I occasionally used the command prompt, but apart from a few basic Git commands, I was never very comfortable with it. Then, like many developers, I stumbled upon countless YouTube videos saying, “If you’re a coder, you must work on a Unix-based system, because the terminal is powerful, and you should spend more time there than in the GUI.”

That’s when I shifted to Ubuntu through dual-booting my system, and I started relying more on the terminal and keyboard than the GUI and mouse. Fast forward to today, I’ve made my final upgrade, my new Mac... But wait, doesn’t the terminal look terrible?

Being a coder, the first thing I opened on my Mac after the initialization was the terminal, and the moment I entered it, I wanted to get out, let alone work on it. On Linux, my terminal wasn’t fancy, but it still looked decent enough to work with. So I decided that before doing anything on my Mac, the first thing I would do was change the look of the terminal, and then move on to other setups on the terminal as well as the system.

# Necessary installations and setups

## [Homebrew](https://brew.sh/)

Homebrew is the essential package manager for macOS, allowing you to easily install and manage command-line tools that aren't available on the App Store.

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## [Oh My Zsh](https://ohmyz.sh/)

Oh My Zsh is an open-source, community-driven framework for managing your Zsh configuration. It's not a shell itself, but rather a layer that sits on top of Zsh to make it more powerful, customizable, and user-friendly. Think of it as a pre-packaged collection of themes, plugins, and helpers that takes the tedious work out of setting up a highly functional and beautiful Zsh terminal.

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## [Warp](https://www.warp.dev/)

Warp is a modern, block-based terminal that reimagines the command line. It's built for speed and collaboration, integrating IDE-like features and a powerful AI assistant to supercharge your workflow.

```shell
brew install --cask warp
```

## [Oh My Posh](https://ohmyposh.dev/)

Oh My Posh is a powerful, cross-platform theme engine that transforms your terminal prompt into a beautiful and informative tool. It provides dynamic segments that show key details like Git status and execution time, making your command line both more functional and visually appealing.

### Install

```shell
brew install jandedobbeleer/oh-my-posh/oh-my-posh
```

### Font Setup

```shell
oh-my-posh font install meslo
```

In both the Mac terminal and Warp, set the font type to "MesloLGM Nerd Font."

### Configure shell to use oh-my-posh

```shell
echo 'eval "$(oh-my-posh init zsh)"' >> ~/.zshrc
exec zsh
```

### Theme select and change

Select a theme from the [oh-my-posh themes](https://ohmyposh.dev/docs/themes) and replace _theme_name_ with your chosen theme’s name.

```shell
echo 'eval "$(oh-my-posh init zsh --config theme_name)"' >> ~/.zshrc
exec zsh
```

# Conclusion

Other appearance changes can be customized in the Warp settings. And if you prefer to stick with the default terminal, you can still adjust it to your liking through its preferences. I believe that when the tools you work with look good, you naturally enjoy working with them more. I hope you found this blog helpful, thank you for reading until the end!
