# Delphi-on-Linux-Setup
Scripts and resources to simplify the setup and development with Delphi on Linux. It should work with all x86 64-bit Linux distros that Delphi suports in WSL, Virtual Machines, or running on hardware natively. 

## Updated to support Delphi 13 *Florence* (37.0)

The same script works for both RedHat/Fedora and Ubuntu/Debian. There are a number of other quality of life improvements too. To run it from the web:
```
curl -L https://tinyurl.com/SetupLinux4Delphi | sudo bash
```
The installation location changed now, so it isn't user specific. Also, the same script supports earlier versions of Delphi. It defaults to the latest, but you can specify any different version:

Usage: `sudo SetupUbuntu4Delphi.sh [version]`

Where [version] is one of the following:

* Florence 13.0    = `Florence`, `37.0`, `13.0` or *blank*
* Athens 12.3      = `Athens`, `23.0`, `12.3`, or `12`
* Athens 12.2      = `12.2`
* Athens 12.1      = `12.1`
* Athens 12.0      = `12.0`
* Alexandria 11.3  = `Alexandria`, `22.0`, `11.3`, or `11`
* Alexandria 11.2  = `11.2`
* Alexandria 11.1  = `11.1`
* Alexandria 11.0  = `11.0`
* Sydney 10.4.1    = `Sydney`, `21.0`, or `10.4.1`
* Sydney 10.4.0    = `10.4.0`
* Rio 10.3.3       = `Rio`, `20.0`, `10.3`, or `10.3.3`
* Rio 10.3.2       = `10.3.2`
* Rio 10.3.1       = `10.3.1`
* Rio 10.3.0       = `10.3.0`
* Tokyo 10.2.3     = `Tokyo`, `19.0`, `10.2`, or `10.2.3`
* Tokyo 10.2.0     = `10.2`

The less specific labels are the latest versions, while the more specific labels refer to the exact version.

I tested Delphi 13 Florence against the following distros with this script:

* Debian based
  * Ubuntu 18.04
  * Ubuntu 20.04
  * Ubuntu 22.04
  * Ubuntu 24.04
  * Kali Linux (rolling)
  * Debian 13 (trixie)
  * Pengwin (WSL)
* Fedora bassed
  * Fedora Linux 42
  * Fedora Remix for WSL
  * Rocky Linux 9.6 (Blue Onyx)
  * Alma Linux 9.6 (Safe Margay)
  * Oracle Linux Server 9.5

I wasn't able to log into my Red Hat account to get the latest RHEL, but it is also Fedora based so it should be fine. 

See the [Official Platform Support list](https://docwiki.embarcadero.com/PlatformStatus/en/Main_Page).

It detects the distro and version and works with `apt`, `yum`, and `dnf` package managers as necessary. You can [view the full source](https://github.com/jimmckeeth/Delphi-on-Linux-Setup/blob/main/scripts/SetupLinux4Delphi.sh), which is recommended before running it on your hardware.

Installation changes:

It defaults to a **blank password**. You should _probably_ change that.

The instalation locations are as follows:

* INSTALL_DIR="/opt/PAServer/$FRIENDLY"
* SCRIPT_PATH="/usr/local/bin/pa$FRIENDLY.sh"
* SCRATCH_DIR="/var/tmp/paserver-$FRIENDLY"

Where friendly is 13.0, 12.2, etc. So you launch the Florence PAServer with `pa13.0.sh`

This was originally a series of [GISTs](https://gist.github.com/jimmckeeth/1cb657694d1ea18335782213097c8a33) that myself and [Ian Barker](https://gist.github.com/checkdigits/f910e3c4b308a25b31b9a5c1f23c5461) were updating. Figured it was time to turn it into a full GitHub project where we can collect all the scripts and add additional resources.

## Installing Ubuntu with WSL2 on Windows 11

Microsoft has a [full article](https://docs.microsoft.com/en-us/windows/wsl/install) with all the details. This is a summary for quick reference. 

On Windows you need to do this from an elevated (administrator) command prompt or PowerShell window. Easiest way is **Win+X,A**.
```
wsl --install -d Ubuntu
```

Once your machine has finished rebooting, installation will continue and you will be asked to enter a username and password. This will be your Linux credential for the Ubuntu distribution.

Start Ubuntu from the start menu, or from the terminal by typing `ubuntu`

### Then run the following script (Delphi 12.3)

```
curl -L https://tinyurl.com/SetupLinux4Delphi | sudo bash
```

If you don't have curl installed then run `sudo apt install curl -y` first

