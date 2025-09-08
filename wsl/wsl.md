# Wsl installation

_From 2023 VG151 teaching team, wr_

_Modified by zzjc_

## Windows (using wsl)

### Requirements

- Windows 10 1709 Fall Creators Update 64bit or later.
- Windows Subsystem for Linux feature is enabled.

1. To enable Linux feature

![](./1.png)

![](./2.png)

Then run on `Powershell` with administrator

```bash
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

![](./3.png)

### Reminder

When you use WSL2, Hyper-V is enabled, which is **NOT** compatible with other vm platforms like VMWare and VirtualBox.

Think twice before using it.

2. Check whether your PC support WSL2:

   - In cmd run `systeminfo`
   - Scroll down to Hyper-V section
   - If there are 4 "Yes" OR " A hypervisor has been detected. Features required for Hyper-V will not be displayed." ("已检测到虚拟机监控程序。将不显示 Hyper-V 所需的功能。"), then your PC is OK
   - Otherwise it's not OK, please use WSL1 or other vm platform

3. Setup wsl2

```bash
wsl --set-default-version 2
```

![](./4.png)

#### Case 1: No error

- Just enjoy your WSL2

#### Case 2: Error with link https://aka.ms/wsl2kernel attatched

- Go to https://aka.ms/wsl2kernel and download a patch
- start wsl2 again
- If network is slow, consider use winget to install wsl and turn on your proxy

#### Case 3: Error telling you Hyper-V is not enabled

- Go to Control Panel (控制面板) > Programs (程序) > Turn Windows features on or off (启用或关闭Windows功能)
- Find Hyper-V

##### Case 3.1: No Hyper-V Settings

- You should check whether your PC support WSL2. See above.

##### Case 3.2: All 4 settings in Hyper-V can be ticked

- Tick all settings
- Restart your PC
- Try to start wsl2 again

##### Case 3.3: Some of the settings can't be ticked

This might be an issue with your hardware. Please refer to section "How to Enable Hardware Virtualization in BIOS" in https://www.makeuseof.com/windows-11-enable-hyper-v/ and try to enable hardware virtualization. (My laptop thinkpad has this issue)

##### Case 3.4 Otherwise

- Search online with error message on your screen (better go to stackoverflow/microsoft doc/github issues)
- Just use WSL1. It has no big issue.

4. Install Linux (Ubuntu/arch, you only need choose **one**)

### Jbox

I download latest ubuntu, debian and arch packages from ms official website, you can download **one of them**. If you use ubuntu and debian, just click the file and everything will be done automatically. If you use arch, you need to run `wsl --install --from-file <file-path>`. By arch wiki simply run ` wsl --install archlinux` is fine, but it is not tested by us.

The following tutorial is from old version, you can check them if you get stuck by previous methods.

### Ubuntu

Go to Microsoft Store and search "Ubuntu"

![](./5.png)

Download one of them.

Open your terminal and choose `ubuntu`.

Setup your user name and password.

![](./7.png)

run

```bash
$ sudo apt update
$ sudo apt install build-essential
$ gcc --version
```

![](./8.png)

### Arch

You may refer to the official website.

Here, we demonstrate the first method.

1. [Download](https://github.com/yuk7/ArchWSL/releases/latest) the installer zip.

![](./9.png)

2. Extract all files in zip file to the same directory. Please extract to a folder that you have write permission. For example, `C:\Program Files` cannot be used since the rootfs cannot be modified there.

![](./10.png)

3. Run `Arch.exe` to extract the rootfs and register to WSL

![](./11.png)

As a side note, the executable name is what is used as the WSL instance name. If you rename it, you can have multiple installs.

4. Open your terminal and choose `arch`.

![](./12.png)

5. Setting the root password

```bash
passwd
```

![](./13.png)

6. Set up the default user

```bash
$ echo "%wheel ALL=(ALL) ALL" > /etc/sudoers.d/wheel
$ useradd -m -G wheel -s /bin/bash {username}
$ passwd {username}
```

![](./14.png)

```bash
$ exit
$ Arch.exe config --default-user {username}
```

![](./15.png)

If the default user has not been changed ([issue #7](https://github.com/yuk7/ArchWSL/issues/7)), please reboot the computer or alternatively, restart the LxssManager in an Admin command prompt. _Please refer to the official documentation._

7.  initialize the keyring

```bash
$ sudo pacman-key --init
$ sudo pacman-key --populate
$ sudo pacman -Sy archlinux-keyring
$ sudo pacman -Su
```

![](./16.png)

8. Install gcc

```bash
$ sudo pacman -S gcc
```

![](./17.png)

9. test gcc

```bash
$ gcc --version
```

![](./18.png)
