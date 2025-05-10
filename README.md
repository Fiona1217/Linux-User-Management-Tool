# 🔧 Linux User Management Tool  
*A Bash script to manage users on GNU/Linux systems with ease.*  

![Bash](https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white)  ![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)  

## 🚀 Skills Demonstrated
### Technical Expertise
- **Bash Scripting Mastery**: Advanced parameter handling, conditional logic, and process control
- **Linux System Administration**: Practical use of `useradd`, `usermod`, and `userdel`
- **Permission Management**: Proper implementation of `sudo` and `umask`
- **Error Handling**: Comprehensive exit code checking and `stderr` redirection

### Professional Skills
- **User Experience Design**: Intuitive menu-driven interface
- **Problem Solving**: Efficient automation of complex sysadmin tasks

## ✨ Features  
- ✅ **Add users** (with custom home dir & login shell)  
- 🔄 **Modify groups** (primary & supplementary)  
- 🐚 **Change login shell** (e.g., `/bin/bash` → `/bin/zsh`)  
- ⏳ **Set account expiration dates**  
- ❌ **Delete users** (with home directory cleanup)  

## 🚀 Quick Start  
```sh
git clone https://github.com/yourusername/repo-name.git  
cd repo-name  
chmod +x manage_users  
sudo ./manage_users
```

## 📜 Interactive Menu Option
| Key | Action |  
|-----|--------|  
| `A` | Add User |  
| `I` | Change Initial Group |  
| `S` | Change Supplementary Group |  
| `L` | Change Login Shell |  
| `E` | Set Expiration Date |  
| `D` | Delete User |  
| `Q` | Quit |  

*(Run with `sudo` for full functionality.)*  
