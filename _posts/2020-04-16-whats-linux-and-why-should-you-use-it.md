---
layout: post
title:  "What's Linux and why should you use it?"
date: 2020-04-16
background: /img/posts/areyouahacker/linux_interface.png
---
<!--
Structure:
1. what is linux?
2. whats the difference to Windows?
3. What are the advantages of using Linux?
4. Why is nobody using Linux than?
5. Summary
-->

Since I got asked way to often "Why does your Windows look so weird?", I decided to write a blog post about 'my weird windows' (spoiler: it's Linux). This way I can answer the next person "You can read about it in my blog.", just like the hipster I'm trying not to be.

I will write about:

1. [What's Linux?]

2. [What are the advantages of Linux?]

3. [Why is nobody using Linux?][Why is nobody using Linux then?]

4. [Some tips for switching to Linux.][Convinced?]

Obviously I can't just go full-nerd-mode without doing the classic anime-person-pushes-glasses-up move.

![](/img/posts/areyouahacker/anime_glasses.gif){width=90%}

## What's Linux?

> "Linux is a family of open source Unix-like operating systems based on the Linux kernel, an operating system kernel first released on September 17, 1991, by Linus Torvalds. Linux is typically packaged in a Linux distribution."
> <sub> Source: [Wikipedia](https://en.wikipedia.org/wiki/Linux) (Look at me guilt-free quoting Wikipedia! Having a blog is great!)

This basically means that some Finnish guy, called Linus Torvalds, was annoyed by the fact that all Unix-like systems were commercial so he developed his own kernel and called it Linux (Linus+Unix).

Because Linus was such a humble guy he made the kernel open-source. This means that everybody is allowed to copy, modify or even sell the code for free. Shortly after people started building their own operating systems based on it. To get an impression of the amount of Linux distributions (that's what we call the different adaptations) you can look at this [distribution-tree](https://commons.wikimedia.org/wiki/File:Linux_Distribution_Timeline.svg#/media/File:Linux_Distribution_Timeline.svg) (zoom in).

## What are the advantages of Linux?

Maybe you ask yourself why anyone would use such an unknown system instead of Windows or MacOS. That's why I want to show you some of the advantages that Linux has over other systems. Some of these points may be applicable to other systems as well, but only Linux combines all of them.

### 1. Open-source code
By far the most important advantage of Linux is that it's open-source. This basically means that there are many more eyes on the code of Linux than on proprietary systems. Especially in terms of privacy this can be crucial. In case you didn't know: By default Windows 10 is sending most your activities to the servers of Microsoft.

Many of the next advantages can be traced back to the open-source nature of Linux but I want to mention them anyway.

### 2. The price
One advantage of being open-source is that Linux distributions are generally free. This isn't necessarily a sign of quality but it definitely opens the platform up to every person that wants to contribute without having to go through a paywall.

It is also great that you don't need to worry about your license when you do a hardware upgrade to your PC.

Last but not least a free OS is especially great for all kind of maker-projects like multimedia PCs, 3D-printers or home servers.

### 3. Security
Security isn't really an advantage but a disadvantage of Windows. I mean come on, you need to install an additional software to fix the loopholes in you system? And then this 'anti-virus' software is often so bad that is could be considered a virus itself? That is just bad software design.

But why is Linux considered to be the most secure system? There are two main reasons for this:

1. Due to the code being open-source there are just more eyes on the code of Linux than on the code of any other system.
2. Security patches get rolled out immediately and not only on fixed dates like it is common for Windows systems.

### 4. Customizability
For me personally this is the most important reason. If there is something that is bothering me about my Linux system there is always a way to change it to my liking. That also means that **everything** that happens on my system including the design, the software and the handling is like it is because I decided on it.

But of course there are people who don't want to think about customization at all. For these people there are a bunch of distributions that come perfectly pre-configured. The most common one is probably Ubuntu which I always recommend to beginners.

To get an overview of how far the Linux-customization can go I recommend having a look at [/r/unixporn](https://www.reddit.com/r/unixporn).

![<sub> My current setup. (Manjaro Linux, i3wm, solarized)](/img/posts/areyouahacker/linux_interface.png){width=90%}

### 5. Ease of use
I know, I know this is a sensitive topic. For many people this is the only reason to not use Linux. And many of them (I'm talking from personal experience) get very butthurt when someone argues against the believe that Linux is soooo hard to learn.

I don't understand how the misconception "You have to be a hacker to understand Linux!" is still in the head of some people. Just to clarify: I have absolutely no clue about programming and I still manage to get around my Linux system.

To ease the fear of this system I will give some examples for how easy and comfortable it is to use and maintain a Linux OS.

#### Installing the operating system

The installation process for Linux is basically the same as with Windows, with the exception that you neither have to worry about license keys nor about opting-out of installing spy software on you PC.

#### Installing software

To install a new software you just open your package manager, and search for the software you need. Then you click 'install'.
That's it! Can it be any easier? By doing this you will always get the newest version of the software and you can be sure that the software is virus-free. Also in contrast to the Microsoft-Store basically every program is available through some Linux repository.

#### Updating software and the system

If you want to update **all** your installed software you open your package manager again and click on the 'Update' button, this also updates your Linux system (no restart required).

Don't even get me started on how stupidly complicated the same process is on Windows where each software has it's own updating mechanism and updating the Systems generally requires a restart.

#### Getting help

Whatever problem you have with your system, it is very likely that somebody else had a similar problem and you can find a solution online. Most solutions are given in the form of terminal commands which you can be easily copied and executed (Though it's recommended to try to understand what the command does).

To get information on basically everything regarding your Linux system, you can visit one of the many, well maintained, community wikis (my favorite one is the [Arch Wiki](https://wiki.archlinux.org/).

## Why is nobody using Linux then?

The answer to this question is less an answer than a statement: Everybody is using Linux. Gotcha!

Whenever a system has to be reliable and secure Linux is used. This becomes clear when we look at the OS usage share for different types of applications ([according to Wikipedia](https://en.wikipedia.org/wiki/Usage_share_of_operating_systems)).

- Mobile devices: #1 Android (Linux kernel)
- Public servers on the internet: #1 Linux
- Supercomputers: #1 Linux ( [just recently](https://itsfoss.com/linux-runs-top-supercomputers/) 100% of the supercomputers became Linux driven)
- Embedded Systems: #1 Linux
- Desktop or laptop computers: #1 Windows

After seeing these statistics we have to change the headline for this chapter:

## Why is nobody using Linux on their home computer?

According to the statistics above it would seem logically that everyone who wants a save and reliable system would use Linux. Because nobody wants to lose hours of work due to some random bluescreen or spend their time to get rid of malware.

If you ask people why they are not using Linux most of them will either say "What's Linux?" or "Because it's to complicated to learn". It is true that there was a time where you needed some basic knowledge to set up a Linux system but these times are long gone. Today it is much easier to properly setup Linux then to setup Windows, considering that you have to create an account and navigate through a bunch of opt-out traps in the process of installing Windows 10.

Even in daily use I find most Linux based systems much easier to use, **especially** for beginners. This may sound strange at first but I have seen tech illiterates using both Windows and Linux and from my experience the beginners on a Linux system barely mess up their system and even manage to keep the software up-to-date whereas the Windows user constantly install malware, don't update old software, and install weird search bars in their browser.

One reason for why I was not using Linux for a long time myself is the incompatibility with some software. Especially computer games and specialized software for my field of study were often not supported on Linux. But even in this regards a lot has changed over the past few years. This is mostly due to the efforts of Valve (may [insert your favorite deity] bless Gabens soul). Since the release of proton [75% of the top 100 games on steam](https://www.protondb.com/) are seemlessly playable on Linux and even non-steam games like the Blizzard games can be played with Proton. And whoever thinks that 75% is not good enough can still get the rest of the games and softwares running with [wine](https://www.winehq.org/).

Another likely reason for the high market share of Windows is that Microsoft just has more money to spend on advertising and to pay hardware manufacturers for pre-installing Windows on their devices.

## Convinced?

If you made it this far you are probably really desperate to find a better operating system for your PC. In that case I want to give you some more hints on where to get started with your own Linux system.

Since the compatibility of Linux is absolutely fantastic it is highly likely that you can just install Linux on your current PC.

Many Linux distributions are available as live systems which means that you can test them on a USB-stick before installing them definitively.

[This](https://help.ubuntu.com/community/SwitchingToUbuntu/FromWindows) is a great page that concentrates on the differences in operating a Linux system versus a Windows system and could be very helpful.

If you are also looking for a new computer there are many choices for computers with pre-installed Linux:

- [Dell](https://www.dell.com/en-us/work/shop/overview/cp/linuxsystems) sells some amazing ultrabooks with pre-installed Ubuntu which I can strongly recommend from personal experience.
- If you like gaming or need high-end computing power for some other task [system76](https://system76.com/) sells heavy duty PCs and Laptops with pre-installed Pop!Os.
- or you can just buy any computer without a pre-installed operating systems and install Linux yourself (by skipping the pre-installed Windows you also save some money).

If you have **any** questions about your system you can ask in one of the countless forums,
[like this](https://askubuntu.com/),
[or this](https://ubuntuforums.org/),
[or this](https://bbs.archlinux.org/),
[or this](https://www.linuxquestions.org/).

Thank's for reading!
