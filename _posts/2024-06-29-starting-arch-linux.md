## Starting in Arch Linux

If you've come straight here from my previous blog post, then you already now I've arrived! But, it was an interesting journey.

I initially wanted to write a set of posts with simple code snippets of what I found along the way, but somehow this has turned into a story-telling exercise instead.

So, let me tell the story...

### To "Arch", or not to "Arch"

I have no emotional attachment to software. At least I don't believe I do. And, for _most_ of the people out there that appear to get all "tribal" about their chosen OS, I do not believe they are emotionally attached either. But, how we interact with our computers is an emotional connection.

Am I weird? Let me try to explain.

We feel with our hands, the keyboard and mouse. We take in with our eyes what we see on screen. How we are made up from our thoughts to our emotions is tied to both of these interactions. So, when we turn on our machines, and we hear that distinct "I'm here and ready!" noise from our PC speakers, we feel something.

At least, that's how it works for me. Whether it was the optional MS Plus Pack experience with Windows 95, the gentle inviting music on first-boot of Windows XP, or Cortana's "Hi there," in Windows 10.

It "means" nothing, not substantial, but I still felt like I'd achieved something. But this all comes at a cost. Extra bells and whistles inevitably mean "wasted" bits. Now, the quotes are valid, since the value of "waste" is subjective, if _you_ value those bits making the audio-visual spectacle you enjoy, then they're not wasted, are they.

This is where I find myself in the weird space I find myself. I have never been comfortable with bloat. I comfort myself in knowing that when I install Windows, I get everything I'm supposed to, and more. Therefore, I should never be without anything...and yet.

We _know_ Microsoft add more than _we_ need, they add their own telemetry collecting stuff. They add features we never will use, but "just in case" we do, they are there. And yet, we still find ourselves downloading Power Toys or other MS Garage tools e.g. Mouse without Borders or the like.

Really, though, that's fine. No single entity can know in advance the _exact_ setup we need, and we can't complain about the telemetry collection if we also expect Microsoft to provide the exactly correct set of tools for our specific use case, when we're not prepared to let then see what our exact use case _is_.

But, _I_ DO complain about the bloated Windows install, because _I_ DO NOT want Microsoft to decide for me what my tools should be, regardless of my use case. I, the user, reserve the right to decide what my machine should have.

And so, I have finally decided that I want to build my setup around my very personal use case. I do not have an emotional connection with my OS, but I do want to guide the OS to where I want it to be.

(This is a long-winded way of saying "I choose Arch as it's user-focused")

### Ok, ISO ready, now what?

I chose to burn to DVD, because I have spare empty discs from years ago. They're not getting used otherwise, it's such a waste! (Alternatively, Rufus can be used to "burn" to a USB device.)

My first problem: Secure boot! Turns out it's a whole other thing that Linux users have fought Microsoft over in the past, apparently Windows just works, but only because Main board manufacturers have already added the Microsoft keys to their devices! So I quickly (after about 2 hours of reading) got over myself on this, settled to just turn it off and trust the process.

Now I'm booted, and am at the console:

```none
Arch Linux 6.8.8-arch1-1 (tty1)

archiso login: root (automatic login)

To install Arch Linux follow the installation guide:
https://wiki.archlinux.org/title/Installation_guide

For Wi-Fi, authenticate to the wireless network using the iwctl utility.
For mobile broadband (WWAN) modems, connect with the mmcli utility.
Ethernet, WLAN and WWAN interfaces using DHCP should work automatically.

After connecting to the internet, the installation guide can be accessed via the convenience script Installation_guide

##################################
root@archiso ~ # _
```

I then try unsuccessfully to understand all the specific stuff I need to do, trying to get stuff installed and chroot in etc. However, once again [Typecraft](https://www.youtube.com/@typecraft_dev) to the rescue! After watching his recent "Linux for Newbs" episodes I learned that even though it's not described in the Installation guide, there is now a script to help with this exact issue.

```bash
archinstall
```

And that's it! Ok, so there are menu options, but if you're not new to OS setup then you would get the _general_ idea.

I chose my gaming laptop to be my first device for this treatment, so I had two nvme devices. I wanted the 500GB drive to hold the boot and root, then the 1TB can be my entire home location. This would be where I would hold my Steam library.

I'm in the UK so I needed to change default locale and keyboard layout info, set appropriate mirrors etc.

### Storage Encryption

For my laptop __only__, I have decided to add disk encryption. This should be obvious, but I'll explain anyway for any uninitiated: Security is never a complete-nothing-gets-past-me-now solution. There are always holes, and some are larger than others. Hence the term "swiss-cheese-security" meaning where possible you want to add as many layers as possible, and you hope none of the holes in the layers actually line up! 

But, there's the inconvenience factor. Having to enter a password everytime you want to access a device is inconvenient. Having to enter a password _and_ use a second factor of authentication is worse. And how bad does it feel when you need _three_ factors?

Therefore, some layers are considered overly inconvenient, considering the added security they confer. So, for my machines that stay in my house, I consider my physical security good enough to ensure someone isn't accessing my devices in a physical way, therefore much more unlilkely to be stealing or intercepting my data.

My laptop is different. I take this outside. I therefore consider disk encryption an absolute __must__ for this device.

(TLDR: security cost-benefit analysis performed for portable laptop)

### Environment Type

I had no idea what I wanted for this, so I just followed [Typecraft's](https://www.youtube.com/@typecraft_dev) suggestion - I initially installed Gnome with gdm and added i3wm later.

GPU drivers...my decision was based on best gaming performance. From what I could gather from the [wiki](https://wiki.archlinux.org/title/NVIDIA), for Nvidia GPU users it makes sense to try the proprietary drivers for your device. I wasn't sure if this was the best way for my laptop, since this has added complexity when wanting to use the iGPU of the Intel CPU with DisplayPort-ALT mode over USB-C. (It also seems the external HDMI port is not directly attached to the Nvidia GPU and therefore is not supported.)

In any case, this proved to be ideal for my Gaming PCs once I was confident to replicate here. I did briefly have success with my laptop when driving external devices via a USB dock, but not without fiddling with additional drivers (details to follow in future blog posts)

### Printer/Scanner

This is a pretty big ordeal for me unfortunately. I have a Lexmark CX310DN MFD device which works very well for what I need it to do, when using Windows. The catch here is that I have become very reliant on the in-built web UI and java-applet combination (😯)

I know, I know, what a security risk! But, since I know the applet and trust what it's doing, I kinda have been happy to continue to use it. It produces beautiful multi-page PDFs from my scans, in the exact paper dimensions I request, without needing third-party software. These days I find this can only be produced from using a fully NPAPI supporting browser (I use [Pale Moon](https://www.palemoon.org/)) and the official Sun Java download (always kept up-to-date of course!)

For Linux, this is far from ideal. I have been able to get Pale Moon installed, but I am pretty certain there is nobody realy interested in the insecure retro-grade step of enabling an unsupported java applet and lettin git run loose on a Linux distribution!

Oh well...I guess I'll keep my Windows VM on my UNRAID server around for just this purpose until I work out an alternative. One such alternative may be using bottles with the official Lexmark software and using that to capture scans to PDF. I can also use the printer's built-in scan-to-email function. Let's see what works in the long-run.

### Conclusion

So, again, here I am blogging from my Arch install on one of my gaming PCs. I'll add some code snippets as github gists and list them here for posterity as a testament to my adventures so far.

---

#### Snippets (via gists)

[Example archinstall user_configuration.json](https://gist.github.com/dmonlineuk/46b6dd626f09d5dcf9f0803679d66227)

[Linux equivalent to NET USE for network share drive mapping](https://gist.github.com/dmonlineuk/f921a0836297a3401ac38ba90cf2760b)

[Enable Multilib packages](https://gist.github.com/dmonlineuk/1fd3820dff2df328aec28bbbe2a95b37)

[Install yay for user package installations](https://gist.github.com/dmonlineuk/f5a2787b04075960aab40bf9a26b909c)

[Install printer server and drivers](https://gist.github.com/dmonlineuk/f10f837d1ebe5da170246830d1d46dfa)

[Install other software](https://gist.github.com/dmonlineuk/399937da3c2da47f62733febafafdea1)