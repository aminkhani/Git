# Git Installation
Before you start using Git, you have to make it available on your computer. Even if it’s already installed, it’s probably a good idea to update to the latest version. You can either install it as a package or via another installer, or download the source code and compile it yourself.

## Installing on Linux
If you want to install the basic Git tools on Linux via a binary installer, you can generally do so through the package management tool that comes with your distribution. If you’re on **Fedora (or any closely-related RPM-based distribution, such as RHEL or CentOS)**, you can use ```dnf```:
```bash 
sudo dnf install git-all
```
If you’re on a **Debian-based distribution**, such as **Ubuntu**, try ```apt```:
```bash 
sudo apt install git-all
```
For more options, there are instructions for installing on several **different Unix distributions** on the Git website, at https://git-scm.com/download/linux.


## Installing on macOS
There are several ways to install Git on a Mac. The easiest is probably to install the **Xcode Command Line Tools**. On Mavericks (10.9) or above you can do this simply by trying to run ```git``` from the Terminal the very first time.
```bash 
git --version
```
If you don’t have it installed already, it will prompt you to install it.<br>
If you want a more up to date version, you can also install it via a binary installer. A macOS Git installer is maintained and available for download at the Git website, at https://git-scm.com/download/mac.
<img src="../../images/git-osx-installer.png">


## Installing on Windows
There are also a few ways to install Git on Windows. The most official build is available for download on the Git website. Just go to https://git-scm.com/download/win and the download will start automatically. Note that this is a project called Git for Windows, which is separate from Git itself; for more information on it, go to https://gitforwindows.org.


##### for more information, go to https://git-scm.com/book/en/v2/Getting-Started-Installing-Git