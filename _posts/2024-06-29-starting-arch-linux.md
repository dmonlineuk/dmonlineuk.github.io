## Starting in Arch Linux

If you've come straight here from my previous blog post, then you already now I've arrived! But, it was an interesting journey.

I initially wanted to write a set of posts with simple code snippets of what I found along the way, but somehow this has turned into a story-telling exercise instead.

So, let me tell the story...

### To "Arch", or not to "Arch"

I have no emotional attachment to software. At least I don't believe I do. And, for _most_ of the people out there that appear to get all "tribal" about their chosen OS, I do not believe they are emotionally attached either. But, how we interact with out computers is an emotional connection.

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

```console
Arch Linux 6.8.8-arch1-1 (tty1)

archiso login: root (automatic login)

To install Arch Linux follow the installation guide:
https://wiki.archlinux.org/title/Installation_guide

For Wi-Fo, authenticate to the wireless network using the iwctl utility.
For mobile broadband (WWAN) modems, connect with the mmcli utility.
Ethernet, WLAN and WWAN interfaces using DHCP should work automatically.

After connecting to the internet, the installation guide can be accessed via the convenience script Installation_guide
```

---

### This is a header

#### Some T-SQL Code

```tsql
SELECT This, [Is], A, Code, Block -- Using SSMS style syntax highlighting
    , REVERSE('abc')
FROM dbo.SomeTable s
    CROSS JOIN dbo.OtherTable o;
```

#### Some PowerShell Code

```powershell
Write-Host "This is a powershell Code block";

# There are many other languages you can use, but the style has to be loaded first

ForEach ($thing in $things) {
    Write-Output "It highlights it using the GitHub style"
}
```
