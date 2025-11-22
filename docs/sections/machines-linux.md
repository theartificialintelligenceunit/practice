---
icon: fontawesome/brands/linux
---


# Fundamental Software: Linux

Apriori

```shell
sudo apt update
sudo apt upgrade
```

Additionally, inspect the GNU Privacy Guard (<abbr title="GNU Privacy Guard">GPG</abbr>) keys via:

```shell
gpg --list-keys
gpg --list-secret-keys
```

<br>

## WGET

Check if the <a href="https://www.gnu.org/software/wget/manual/wget.html" target="_blank">wget</a> utility exists:

```shell
wget --version
```

If `wget` does not exist, install it; additionally, install `ca-certificates`:

```shell
sudo apt install wget ca-certificates
```

`ca-certificates` allows applications that are secure sockets layer (SSL) dependent to verify the authenticity of <abbr title="secure sockets layer">SSL</abbr> connections; <abbr title="secure sockets layer">SSL</abbr> is a deprecated tool.

<br>

## JAVA

### Installing Java

For more details study [this tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-java-with-apt-on-ubuntu-22-04) by [DigitalOcean](https://www.digitalocean.com/about).  Example, **pre Ubuntu 24.04 era**:

```shell
# jdk & jre
sudo apt install openjdk-19-jdk-headless
java --version
javac --version
```

For <a href="https://linuxiac.com/how-to-install-java-on-ubuntu-24-04-lts/" target='_blank'>Ubuntu 24.04 LTS (Long Term Supported)</a>

```shell
# jdk & jre
sudo apt install default-jdk
java --version
javac --version
```


### Java Environment Variables

The environment variable of interest is the `JAVA_HOME` variable, which depends on the installation directory string, i.e.,

```shell
sudo update-alternatives --config java
```
or

```shell
readlink -f `which java`
```

The `JAVA_HOME` environment variable is defined as

```shell
readlink -f `which java` | sed "s:/bin/java::"
```

i.e., the `/bin/java` suffix of the penultimate command's output is excluded/removed. If the resulting string is `/usr/lib/jvm/java-19-openjdk-amd64`, then

```shell
export JAVA_HOME=/usr/lib/jvm/java-19-openjdk-amd64
```

Or rather, edit `/etc/environment` by appending the definition of `JAVA_HOME` at the end of the file.  An edit mode option is

```shell
sudo vi /etc/environment
```

Subsequently, append

```shell
JAVA_HOME=/usr/lib/jvm/java-19-openjdk-amd64
```

<details class="example">
  <summary>`vi` Help Notes</summary>
  The directive

  <ul>
    <li>`i` starts the edit mode</li>
    <li>`ESC` exits the mode</li>
    <li>`:wq` saves</li>
  </ul>
  
  More `vi` directives <a href="https://www.cs.colostate.edu/helpdocs/vi.html" target="_blank">herein</a>.
</details>

<br>

## GIT

Update `git` via the `git-core/ppa`[^1].  **Pre Ubuntu 24.04 era**:

```shell
sudo add-apt-repository ppa:git-core/ppa
sudo apt update
sudo apt install git-all
```

Case <a href="https://ubuntu.com/blog/canonical-releases-ubuntu-24-04-noble-numbat">Ubuntu 24.04 LTS (Long Term Supported)</a>

```shell
sudo add-apt-repository ppa:git-core/ppa
sudo apt update
sudo apt upgrade
```

Subsequently, [set up & configure](https://git-scm.com/book/en/v2/Appendix-C%3A-Git-Commands-Setup-and-Config) `git` ...

```shell
git config --global user.name ""

# Navigate to Settings -> Emails ... within the *Primary email address* section 
# you will find a ...@users.noreply.github.com address that can be used 
# for Git operations.  Additionally, consider enabling - Keep my 
# email addresses private 
git config --global user.email "...@users.noreply.github.com"

git config --global core.editor "vim --nofork"
git config --global init.defaultBranch master
```

<br>

Next, SSH key

```shell
ssh-keygen -t ed25519 -C "...@users.noreply.github.com"
$ Enter file in which to save the key ... [Default ↦ ENTER.]
```

Beware, a key [re-write might be requested](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#:~:text=When%20you%27re%20prompted) if a key file already exists.  The command

```shell
cat ~/.ssh/id_ed25519.pub
```

prints the text for setting-up SSH key pair within a version control service.  For instances whereby multiple accounts have to be managed per git client study [GitHub Multiple Accounts](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-your-personal-account/managing-multiple-accounts).

<br>

## CONDA [Optional]

This is for readers that sometimes need to develop outwith a container, i.e., within a virtual environment of the host machine instead.  Installation is via `miniconda`.  Foremost, check the python version

```shell
python --version
```

### The Installer

Subsequently, `get` the [installer](https://docs.conda.io/en/latest/miniconda.html#linux-installers) relative to the system's python version, e.g.,

```shell
# if python 3.10.*
sudo wget -P Downloads 
  https://repo.anaconda.com/miniconda/Miniconda3-py310_24.4.0-0-Linux-x86_64.sh
cd Downloads
sudo chmod +x Miniconda3-py310_24.4.0-0-Linux-x86_64.sh
```

<br>

### Install

Install in the specified directory

```shell
# Include <-b> for automatic acceptance of the terms & conditions
sudo bash Miniconda3-py310_24.4.0-0-Linux-x86_64.sh -p /opt/miniconda3

$ Do you wish the installer to initialize Miniconda3 by running conda init?
>>> no
```

<br>

### Set the Path Variable

Open `/etc/profile`, i.e.,

```shell
sudo vi profile
```

and append

```shell
if ! [[ $PATH =~ "/opt/miniconda3/bin" ]]; then
	PATH="/opt/miniconda3/bin:$PATH"
fi
```

The command `i` starts the edit mode, `ESC` exits the mode, and `:wq` saves; [`vi` commands](https://www.cs.colostate.edu/helpdocs/vi.html).  **Exit** the terminal.

<br>

### Set-up

Next, within a new terminal

```shell
conda init bash
conda config --set auto_activate_base false
sudo chown -R $USER:$USER /opt/miniconda3
```

<br>

### Upkeep

Update [conda](https://docs.conda.io/projects/conda/en/4.14.x/index.html) via

```shell
conda update -n base -c anaconda conda
```

<br>
<br>

<br>
<br>

<br>
<br>

<br>
<br>

[^1]: <a href="https://documentation.ubuntu.com/launchpad/user/reference/packaging/ppas/ppa" target="_blank">Personal Package Archive</a>

<br>
<br>
