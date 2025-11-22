---
icon: lucide/grid-2x2
---

# Fundamental Software: Windows

## CORE

### Basic Tools

Foremost, install

<ul class="disc">
  <li class="disc"><a href="https://notepad-plus-plus.org" target="_blank">Notepad++</a> / <a href="https://github.com/notepad-plus-plus/notepad-plus-plus/releases" target="_blank">Notepad++</a></li>
  <li class="disc"><a href="https://adoptium.net/en-GB/temurin" target="_blank">Java: [JDK & JRE]</a></li>
</ul>


### Open Office

Unload the core executable & language pack of [OpenOffice](https://www.openoffice.org/download/index.html).


### Git

Unload the executable at [git-scm](https://git-scm.com), subsequently install.


??? note "Install GIT"
    
    !!! Quote "Select Destination Location"
    
        This installation directory.
    
    !!! Quote "Select Components"
    
        Deselect
        
        <ul class="deselect">
          <li class="deselect">Additional icons On the Desktop</li>
          <li class="deselect">Git LFS (Large File Support)</li>
          <li class="deselect">Add a Git Bash Profile to Windows Terminal</li>
        </ul>
    
    !!! Quote "Select Start Menu Folder"
    
        Deselect
        
        <ul class="deselect">
          <li class="deselect">Don't create a Start Menu folder</li>
        </ul>
    
    !!! Quote "Choosing the default editor used by Git"
    
        Select
        
        <ul class="select">
          <li class="select">Use Notepad++ as Git's default editor</li>
        </ul>


    !!! Quote "Adjusting the name of the initial branch in new repositories"
    
        Select
        
        <ul class="point">
          <li class="point">Override the default branch name for new repositories [master]</li>
        </ul>
    
    !!! Quote "Adjusting your PATH environment"
        
        Select
        
        <ul class="point">
          <li class="point">Git from the command line and also from 3rd-party software</li>
        </ul>
    
    !!! Quote "Choosing the SSH executable"
        
        Select
        
        <ul class="point">
          <li class="point">Use bundled OpenSSH</li>
        </ul>
    
    !!! Quote "Choosing HTTPS Transport Backend"
        
        Select
        
        <ul class="point">
          <li class="point">Use the OpenSSL library</li>
        </ul>
    
    !!! Quote "Configuring the line ending conversions"
        
        Select
        
        <ul class="point">
          <li class="point">Checkout Windows-style, commit Unix-style line endings</li>
        </ul>
    
    !!! Quote "Configuring the terminal emulator to use with Git Bash"
        
        Select
        
        <ul class="point">
          <li class="point">Use MinTTY (the default terminal of MSYS2)</li>
        </ul>
    
    !!! Quote "Choose the default behaviour of `git pull`"
        
        Select
        
        <ul class="point">
          <li class="point">Fast-forward or merge</li>
        </ul>
    
    !!! Quote "Choose a credential helper"
        
        Select
        
        <ul class="point">
         <li class="point">None</li>
        </ul>
    
    !!! Quote "Configuring extra option"
    
        Select
        
        <ul style="list-style-type: '\2611'; margin-left: 35px;">
          <li style="list-style-type: '\2611'; padding-left: 5px;">Enable file system caching</li>
        </ul>
    
    !!! Quote "Configuring experimental options"
        
        <ul class="deselect">
          <li class="deselect"><b>Deselect all</b></li>
        </ul>


<br>

## INSTALLATIONS THAT PROPAGATE TO WSL KERNELS

### Docker Desktop

Unload [Docker Desktop](https://www.docker.com/products/docker-desktop/), subsequently install.  During installation

- [x] Use WSL-2 instead of Hyper-V  [**Select**]
- [ ] Add shortcut to desktop [**Deselect**]


<br>


### IntelliJ IDEA Ultimate

Unload [IntelliJ IDEA Ultimate](https://www.jetbrains.com/idea/download/?section=windows), subsequently install.  During the product's initial launch, a licence screen appears.  Activate your licence via one of the presented methods, e.g., via an **Activation Code**.

<br>

### VS Code

Study the [Visual Studio CODE](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode) installation [notes](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode#install-vs-code-and-the-wsl-extension).  Whilst installing VS Code

<ul class="disc">
  <li class="disc">Select Destination Location (This is about the installation directory)</li>
  <li class="disc">Select Start Menu Folder (Leave default text)</li>
  <li class="disc">Select Additional Tasks (Ensure `Add to PATH (requires <i>shell</i> restart)` is selected.  Deselect everything else.)</li>
</ul>

Subsequently, and after launching VS Code, install the [Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) extension pack via the extension button.

<br>
<br>

<br>
<br>

<br>
<br>

<br>
<br>
