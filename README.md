# dev-env-setup
## Install Python and Setup a Virtual Environment -> [Python 3.8.12](https://www.python.org/downloads/release/python-3812/) 
### Install virtualenv  
This one is needed to isolate the requirements of a project from the entire Python installation and packages.
```console
pip install virtualenv
virtualenv --version
```
Go to your project folder and create virtualenv:
```console
python -m venv ./.venv
```
Before activating the venv, you need to give permission to PowerShell scripts. Run PowerShell as administrator and execute the following command.
```console
set-executionpolicy remotesigned
```
Activate the venv:
```console
.\.venv\Scripts\Activate.ps1
```
Deactivate the venv:
```console
deactivate
```
The required packages for RL development is listed below:
```console
pip install torch==1.10.1+cu113 torchvision==0.11.2+cu113 torchaudio===0.10.1+cu113 -f https://download.pytorch.org/whl/cu113/torch_stable.html
pip install gym
pip install stable-baselines3[extra]
pip install fmpy
pip install mysql-connector-python
```

## Install Visual Studio Code and Visual Studio Community Edition
- VSCode -> [Download the setup file from official page.](https://code.visualstudio.com/) After VSCode installation, add Python extension from marketplace.
- Install Visual Studio Community edition. This one is needed for C/C++ libraries required by FMU simulations. -> [Download](https://visualstudio.microsoft.com/vs/community/)

## Git and GitHub
Install Git for Windows. After installation, there are some steps to go through in order to complete the setup.
```console
git config --global user.name "serhat-akbas"
git config --global user.email serhatakbas89@gmail.com
git config --global core.editor "code --wait"
git config --global color.ui auto
git config --list
git config --list --global
```
You also need to configure SSH in order to communicate with GitHub (pull, push etc. commands directly from terminal). Open git bash and type the following:
```console
ssh-keygen -t ed25519 -C "serhatakbas89@gmail.com"
ssh-add ~/.ssh/id_ed25519
clip < ~/.ssh/id_ed25519.pub
```
Go to GitHub ([link](https://github.com/settings/keys)) and click on "New SSH Key" in settings (SSH and GPG keys). Paste the copied key into the field.
For more information, refer to [GitHub docs on SSH.](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

# Optional
## Windows Subsystem for Linux (WSL)
Install WSL (Ubuntu). This is needed for Docker on Windows.
```console
wsl --install
```
This command installs the latest WSL Linux kernel version onto your machine. Ubuntu is the default distribution of Linux. For the complete documentation, [visit official page.](https://docs.microsoft.com/en-us/windows/wsl/)

## Docker
Install Docker Desktop on Windows. [Official page.](https://docs.docker.com/desktop/windows/install/)  
Build and run the image:
```console
docker build -t project-ai-docker-image -f ./Dockerfile .
```
Run the image:
```console
docker run -it --rm --gpus all project-ai-docker-image bash
```
## Install Hyper terminal. Download from their [site.](https://hyper.is/)

[Change default terminal to PowerShell.](https://dev.to/vanwildemeerschbrent/use-powershell-within-hyper-terminal-windows-51k3)

