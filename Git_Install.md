Note. Needed 2 separate installations.
# Git - Install - Windows 11 Arm

Go to URL: https://git-scm.com/ download and run as **Admin** Git for Arm

C:\Program Files\Git

Settings:
- Use Git and optional Unix tools from the Command Line.
- Use external OpenSSH - New!
- Use the native Windows Secure Channel library
- Checkout as-is, commit Unix-style line endings
- Use Windows' default console window
- Fast-forward or merge
- Git Credential Manager
- Choose first option

# Git -Install - WSL Ubuntu 
Run each command separately:
```bash
sudo add-apt-repository ppa:git-core/ppa

sudo apt update

sudo apt install git

git --version
```
Optional: Clean up old Git version
```bash
sudo apt remove git
sudo apt purge git
sudo apt autoremove
```




