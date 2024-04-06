# Delphi-on-Linux-Setup
 Scripts and resources to simplify the setup and development with Delphi on Linux

 This was originally a series of [GISTs](https://gist.github.com/jimmckeeth/1cb657694d1ea18335782213097c8a33) that myself and [Ian Barker](https://gist.github.com/checkdigits/f910e3c4b308a25b31b9a5c1f23c5461) were updating. Figured it was time to turn it into a full GitHub project where we can collect all the scripts and add additional resources.

The Bash scripts works with CentOS (Redhat, Fedora) or Ubuntu and related Linux distros. I've used them both under WSL2, VM, and hardware installs.

Ubuntu support:  20.04 LTS and 22.04 LTS
Redhat support: CentOS 9

## Installing WSL2 on Windows 11

Microsoft has a [full article](https://docs.microsoft.com/en-us/windows/wsl/install) with all the details. This is a summary for quick reference. 

On Windows you need to do this from an elevated (administrator) command prompt or PowerShell window. Easiest way is **Win+X,A**.
```
wsl --install -d Ubuntu
```

Once your machine has finished rebooting, installation will continue and you will be asked to enter a username and password. This will be your Linux credential for the Ubuntu distribution.

Start Ubuntu from the start menu, or from the terminal by typing `ubuntu`

Then run the following script

```curl -L https://embt.co/SetupUbuntu4Delphi22 | bash```

If you don't have curl installed then run `sudo apt install curl -y` first