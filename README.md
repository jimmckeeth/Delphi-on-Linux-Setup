# Delphi-on-Linux-Setup
 Scripts and resources to simplify the setup and development with Delphi on Linux

 This was originally a series of [GISTs](https://gist.github.com/jimmckeeth/1cb657694d1ea18335782213097c8a33) that myself and [Ian Barker](https://gist.github.com/checkdigits/f910e3c4b308a25b31b9a5c1f23c5461) were updating. Figured it was time to turn it into a full GitHub project where we can collect all the scripts and add additional resources.

The Bash scripts works with CentOS (Redhat, Fedora) or Ubuntu and related Linux distros. I've used them both under WSL2, VM, and hardware installs.

* Ubuntu support:  20.04 LTS and 22.04 LTS - `curl -L curl -L https://tinyurl.com/SetupUbuntu4Delphi23 | bash`
* Redhat support: CentOS 9, FedoraRemix (WSL), RHEL8 -  `curl -L curl -L https://tinyurl.com/SetupRedHat4Delphi23 | bash`
* [Official Platform Support list](https://docwiki.embarcadero.com/PlatformStatus/en/Main_Page)

## Installing Ubuntu with WSL2 on Windows 11

Microsoft has a [full article](https://docs.microsoft.com/en-us/windows/wsl/install) with all the details. This is a summary for quick reference. 

On Windows you need to do this from an elevated (administrator) command prompt or PowerShell window. Easiest way is **Win+X,A**.
```
wsl --install -d Ubuntu
```

Once your machine has finished rebooting, installation will continue and you will be asked to enter a username and password. This will be your Linux credential for the Ubuntu distribution.

Start Ubuntu from the start menu, or from the terminal by typing `ubuntu`

### Then run the following script (Delphi 12.1)

```curl -L curl -L https://tinyurl.com/SetupUbuntu4Delphi23 | bash```

If you don't have curl installed then run `sudo apt install curl -y` first

***************

## Installing CentOS 9 Stream in WSL2 on Windows 11

Microsoft has a [full article](https://docs.microsoft.com/en-us/windows/wsl/install) with all the details.

`wsl --install`

**Note:** *There isn't a Red Hat as part of the default WSL distributions*. This script should work with any RPM based distribution using the YUM package manager.

To manually install CentOS Stream 9 follow these steps:

1. Download the latest [CentOS Stream 9 release](https://github.com/mishamosher/CentOS-WSL) (this is not an official CentOS or WSL source)
2. Extract the content into a folder it can live on your system. I picked `C:\WSL\CentOS9`
3. Run `CentOS9-stream.exe` as Administrator to install CentOS 9
4. Start CentOS 9

CentOS is installed, but it doesn't have a user yet. The following will create a user for you. Then you need to restart the CentOS instance.

* From CentOS
```
yum update -y && yum install passwd sudo -y
myUsername=delphi
adduser -G wheel $myUsername
echo -e "[user]\ndefault=$myUsername" >> /etc/wsl.conf
passwd $myUsername
```
* From PowerShell
```
wsl --terminate CentOS9-Stream
```
* You can now launch CentOS

### Then run the following script (Delphi 12.1)

```curl -L curl -L https://tinyurl.com/SetupRedHat4Delphi23 | bash```

If you don't have curl installed then run `sudo apt install curl -y` first
