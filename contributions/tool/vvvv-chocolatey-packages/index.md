---
uid: "contribution/vvvv-chocolatey-packages"
uid-meta: "contribution/vvvv-chocolatey-packages-meta"
title: "VVVV Chocolatey Packages"
image: "chocolateyicon.gif"
contribution: "true"
---

vvvv and addonpack packages for Chocolatey.
*(Chocolatey is a package manager, apt-get for Windows)*

##  How to use it :
If you don't have Chocolatey installed, just go to http://chocolatey.org for instructions. It will take about 2 minutes to install.

When Chocolatey is installed, type **cinst vvvv** and **cinst vvvv-addonpack** in command prompt to install vvvv and addons. I recommend run all commands as administrator.

By default, all stuff is installing to **C:\vvvv\version** folder. For me it's ok, but i think some people want to specify default installation dirrectory. I will add this functionality in future packages or maybe someone can help me with this and fork my [repo](https://github.com/smakhtin/VVVV-Chocolatey-Packages).

Update: now we support both x86 and x64 versions. You can type **vvvv.x86** or **vvvv.x64** to install 32 or 64 bit version. Also, thx to Claudius, package now automatically installing C++ dependencies, and if you installing addonpack, it's installs VVVV automatically. We still missing .Net4 and DirectX dependecies.