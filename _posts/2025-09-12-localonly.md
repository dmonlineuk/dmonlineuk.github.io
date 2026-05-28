# Forcing Windows 11 to Allow a Local-Only Account During First Setup

Windows 11 increasingly pushes users toward signing in with a Microsoft Account during the Out‑Of‑Box Experience (OOBE). However, there are still reliable ways to complete setup using only a local account. This guide covers both older and newer Windows 11 builds.

## Method 1: Older Windows 11 Builds (up to early 24H2)

These builds still include the hidden `ms-cxh:localonly` OOBE path.

1. Install Windows until the **OOBE** begins.
1. Press **Shift + F10** to open Command Prompt.
1. Enter 
```shell
start ms-cxh:localonly
```
1. Follow the prompts to create your local account.
1. Complete the rest of setup and install updates as normal.

**Note:** Some later 24H2 builds block this method. If nothing happens, use Method 2.

## Method 2: Newer Windows 11 Builds (24H2+)

Microsoft has removed the `ms-cxh:localonly` path from newer builds. The remaining options are:

- **Use the domain‑join workflow**, or
- **Temporarily block internet access**

Both methods force Windows to expose the local account creation screen.

### Option A: Domain‑Join Path (Recommended)

This method works even **with an active internet connection.**

1. Continue through OOBE until asked **How would you like to set up this device?**
1. Choose **Set up for work or school.**
1. When prompted to sign in, select **Sign‑in options.**
1. Choose **Domain join instead.**
1. Windows will now prompt you to create a local account.

You don’t need an actual domain, this simply unlocks the local account path.

### Option B: Block Internet Access

If using a physical machine, simply remain disconnected from the network during OOBE. If this is not possible, you can disable networking manually.

1. At the OOBE screen, press **Shift + F10** to open Command Prompt.
1. Enter
```shell
ipconfig /release
```
1. Continue through OOBE until Windows asks you to connect to the internet.
1. Select `I don't have internet` at the bottom of the screen.
1. Windows will now allow you to create a local account.

**Virtual machines:** It’s often easier to install Windows with no virtual NIC attached, then add it after setup.

## Troubleshooting & Notes

- **Wi‑Fi‑only devices:** If Windows forces Wi‑Fi setup before OOBE, use the domain‑join method.
- **Network won't reconnect:** After setup, if your adapter doesn't come back online: 
```shell
ipconfig /release
ipconfig /renew
```
- **Feature limitations:**
    * Features like OneDrive, Store sync, and device backup require a Microsoft Account.
    * You can add a Microsoft Account later under **Settings -> Accounts**