---
icon: lucide/binary
---

# Linux & Windows Subsystem for Linux (WSL)

Using a Linux Kernel requires **(a)** activating WSL, and **(b)** installing a Linux distribution.  The auto-script approach sometimes fails.  This section outlines the semi-manual approach.  For reference purposes:

<ul>
<li><a href="https://learn.microsoft.com/en-us/windows/wsl/install" target="_blank">Auto</a></li>
<li><a href="https://learn.microsoft.com/en-us/windows/wsl/install-manual#step-2---check-requirements-for-running-wsl-2" target="_blank">Manual</a></li>
</ul>

<br>

## Activate Windows Subsystem for Linux

The activation steps are

!!! note ""
    
    Control Panel $\rightarrow$ Uninstall a program $\rightarrow$ Turn Windows features on or off $\rightarrow$ Windows Subsystem for Linux.

Subsequently, re-start the machine.

<br>

## Enable the virtual machine feature via PowerShell; administrator mode.

For details visit [enable virtual machine feature](https://learn.microsoft.com/en-us/windows/wsl/install-manual#step-3---enable-virtual-machine-feature).

```powershell
  dism.exe /online /enable-feature 
    /featurename:VirtualMachinePlatform /all /norestart
```

<br>

## Linux Kernel Update Package

[Download and install](https://learn.microsoft.com/en-us/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package) the package.

<br>

## Download & Install a Linux Distribution

Steps:

<ul>
<li><a href="https://learn.microsoft.com/en-us/windows/wsl/install-manual#downloading-distributions" target="_blank">Download</a></li>
<li>To install, run `Add-AppxPackage .\app_name.appx`</li>
<li>Double-click on the installed app, which will exists within the applications' menu, to activate it.  You will be asked to set up credentials.</li>
</ul>

<br>

## Commands

<a href="https://learn.microsoft.com/en-us/windows/wsl/basic-commands" target="_blank">Basic Commands</a>

<br>
<br>

<br>
<br>

<br>
<br>

<br>
<br>
