# dev-env-setup
## Essentials
* Install Python3.9 <br />
[Python 3.9.9](https://www.python.org/downloads/release/python-399/)

* Install Visual Studio Code. [Download the setup file from official page.](https://code.visualstudio.com/) After VSCode installation, add Python extension from marketplace.

* Install PyTorch with the following command in shell (Stable 1.10.1 Cuda 11.3). Open PowerShell and type the following command:
```console
pip3 install torch==1.10.1+cu113 torchvision==0.11.2+cu113 torchaudio===0.10.1+cu113 -f https://download.pytorch.org/whl/cu113/torch_stable.html
```

* Install Visual Studio Community edition. This one is needed for C/C++ libraries required by FMU simulations.

* Install WSL (Ubuntu). This is needed for Docker on Windows.
```console
wsl --install
```
This command installs the latest WSL Linux kernel version onto your machine. Ubuntu is the default distribution of Linux. For the complete documentation, [visit official page.](https://docs.microsoft.com/en-us/windows/wsl/)

* Install Docker Desktop on Windows. [Official page.](https://docs.docker.com/desktop/windows/install/)

* Install Git for Windows. After installation, there are some steps to go through in order to complete the setup.
```
git config --global user.name "serhat-akbas"
git config --global user.email serhatakbas89@gmail.com
git config --global core.editor "code --wait"
git config --global color.ui auto
git config --list
git config --list --global
```
You also need to configure SSH in order to communicate with GitHub (pull, push etc. commands directly from terminal). Open git bash and type the following:
```
ssh-keygen -t ed25519 -C "serhatakbas89@gmail.com"
ssh-add ~/.ssh/id_ed25519
clip < ~/.ssh/id_ed25519.pub
```
Go to GitHub ([link](https://github.com/settings/keys)) and click on "New SSH Key" in settings (SSH and GPG keys). Paste the copied key into the field.
For more information, refer to [GitHub docs on SSH.](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

## Optional
* Install Hyper terminal. Download from their [site.](https://hyper.is/)

[Change default terminal to PowerShell.](https://dev.to/vanwildemeerschbrent/use-powershell-within-hyper-terminal-windows-51k3)

