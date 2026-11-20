+++
author = "Joe W"
title = 'Linux Desktop And Deployment Scripts'
date = 2026-11-19T22:27:11-08:00
description = "003 - follow the yellowbrick road to freedom."
tags = [
    "markdown",
    "Homelab",
    "journey",
    "Linux",
    "Blog Post",
    "Scripting"
]
hideReply = false
+++

## Overview:

I have been a long-time Windows user since Win95 on my grandparents’ dial-up, but change is constant. As of January 2025, I have been using Linux full time as my go-to. The world wants you to plug in via your phone. Maybe it’s my hand size, but mostly I think it’s the productivity that keeps me on a mouse and keyboard, and ideally, multiple screens. Combine this with the fact that I LOVE to learn and tinker, i have a rugged history with borking my OS. Combine that with the history of building PCs and being in deployment roles, I have always had some sort of deployment script for my personal standard of my daily drive, so no stress to flash an OS quickly. So let’s dive into my Linux history & personal script for a desktop environment.

## My Linux History & Distro:

I have had several shoulder rubs with Linux over the years with attempting to use it as a daily driver (not to mention professional or homelab server experience), but mostly it’s always fallen off for me after a few weeks do to the complexity of gaming, Nvidia drivers, and many versions of common game anti-cheats not running on Linux. Gaming has always won out because of the connection it brings with friends, so Windows has been a constant companion. With the age of [Proton Compatibility Layer](https://github.com/ValveSoftware/Proton) being driven by Valve and [others](https://github.com/GloriousEggroll/proton-ge-custom), the privacy concerns of [windows](https://www.privacyguides.org/en/os/windows/#privacy-notes) and the general [enshitification](https://doctorow.medium.com/https-pluralistic-net-2024-04-04-teach-me-how-to-shruggie-kagi-caaa88c221f2) of Windows OS, I have fully moved on.

#### Primary Needs from my distro of choice:

- While I love to play with tech and push it till it breaks, I want something that just works when I sit down to use it. So I need reliability, support (community and developer) and something that just works out of the box.
    
- Gaming Support
    
- Dual monitor and 144hz support
    
- Support or adjacent tooling that supports a few of my favorite programs. IE. VScode, Scrivener Tintero, Obsidian, Brave Browser, etc.
    

#### Distro Experience for daily drivers:

**Pop OS** - 2025-01-01 till 2025-11-01 - overall went with this because of its “up and coming” hotness, wide recommendation for gaming, continuous support and development, lots of community support and similarity to Windows GUI. 

- Why I moved on: I moved on less because of my issues, granted I had some, and more because of better longstanding history, support and reliability of my next distro. 
    

**Linux Mint** - 2025-11-02 till 2026-01-20 - with this shift, both my machined (laptop & desktop) have been shifted to this as my attention was grabbed by a dedicated Nvidia driver manager, more customization, better software updater (granted I have a habit of just doing it via cli) and better support for 144hz monitors.

- Why I moved on: Looking to try other systems and was interested in the gaming-first approach of CachyOS and wanted to dabble in an Arch Based Distro for experience.
    

**CachyOS** - 2026-01-20 till 2026-05-20 - I had just moved my main device over due to out of the box support for gaming and focus on an in-house proton fork for CachyOS, seeking some niche gaming needs of the time.

- Why I moved on: I use three monitors nowadays for gaming, which CachyOS does not support beyond two monitors and will crash and brick the OS into a nasty boot at that point in time. I enjoyed the native gaming support being buttery smooth.
    

**Linux Mint** - 2026-05-20 till now - All my household devices now run on Mint again, and I doubt I will change soon because of the massive support of the distro.

### Is Linux worth it for me?

Very much so, I really would hate to move back to Windows for my personal device. My ability to customize and work with the under the hood with ease is very much empowering and a desire at this point. Most of all, it works with all my core needs, homelab management, development interest and rarely do I have to tinker with gaming.

## The Script

### What is this script?

While the OS has changed, the methods and languages are different, and the code details have shifted, the core goal remains the same.

- Be as quick as possible to get a desktop environment running for me.

### Script History:

This project, while new to GitHub, has been around for about 10 years, starting with some simple PowerShell scripting. It has grown as my needs grew, even existing as an unattended-install deployment for Windows machines for a while. But now it sits in its current iteration here: [https://github.com/SJW-sys/DailyDriverSetup](https://github.com/SJW-sys/DailyDriverSetup)

This script used to be hard coded, but now sits as functions with a simple CLI interface to allow various “files-as-code” to be called and allow for robust flexibility in my deployments. Should I need something different, I simply edit the files. While I now rely on Ansible for servers, this is my quick and dirty method for server deployments in my home environments.

There is much to still code and support future growth, but for now, it saves enough time as it is. It pushes all basic software and system requirements to meet my needs at a standard I am happy with.

### Scripting forward?

With AI OSs popping up and actively being adopted, along with the effects of FLOSS still being heavily affected by uncertainty in code, it’s hard to say where this will go. But for now, I see a lot of value in knowing how to code as human in the loop approaches to AI will be critical to ensure reliable clean code. This will remain as a project under my wing to keep my skills sharp, and my environments to my standards, and most important, quick to deploy.