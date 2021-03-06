# Windows

## Windows 10 快捷键

- (截屏)将选择区域图像复制到剪贴板: `Win + Shift + S`
- 桌面切换: `Win + Ctrl + Left/Right`
- 显示日期: `Win + Alt + D`

## 开启休眠

1. powercfg.exe /hibernate on
2. 在电源设置里面勾选 hibernate ：Start -> System -> Power & sleep -> Additional power settings. -> Choose what the power button does -> Change settings that are currently unavailable -> 勾选Hibernate

## CMD 命令

```bash
# 查看端口占用进程
netstat -ano | findstr "8081"

# 杀进程
taskkill /pid XXXXXX

# SSH: Windows 10 可用
ssh username@IP
```

## WSL 命令

```bash
# 打开当前目录
explorer.exe .

# 打开文件(默认程序): cmd.exe /C start main.pdf
cmd.exe /C start <file>

# Ubuntu 升级
sudo do-release-upgrade
```

## Windows10 + Cmder + zsh

在 Cmder 中集成 zsh。

1. <https://zhuanlan.zhihu.com/p/34152045>
2. <https://blog.csdn.net/sko121/article/details/78091083>

步骤

1. 启用系统的 Ubuntu Bash
2. 进入 Ubuntu Bash
3. 安装 zsh

    ```bash
    # zsh 安装
    sudo apt-get install zsh
    # oh-my-zsh 安装
    sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

    # 主题修改
    vim ~/.zshrc
    # ZSH_THEME="ys"

    # 默认启动 zsh
    vim ~/.bash_profile
    # 末尾添加
    # exec zsh
    source ~/.bash_profile
    ```

4. Cmder 设置, 添加 Tasks。`bash:ubuntu`, 图标路径 `/icon "%USERPROFILE%\icons\ubuntu.ico"`, 命令路径`%windir%\system32\bash.exe ~ -cur_console:p`

zsh 启动时如果需要添加 ssh-add，需要在 `~/.zshrc` 末尾添加，同时 `.ssh` 权限需要作改为 `chmod -R 700 .ssh`。

```bash
vim ~/.zshrc
# if [ -z "$SSH_AUTH_SOCK" ] ; then
#   eval `ssh-agent -s`
#   ssh-add -D
#   ssh-add ~/.ssh/id_rsa_gitlab
#   ssh-add ~/.ssh/id_rsa_github
#   ssh-add ~/.ssh/id_rsa_inter_gitlab
#   ssh-add ~/.ssh/id_rsa_gitee
#   ssh-add -l
# fi
```

## 资源

1. git bash 添加更多的 Linux 命令: [How to add more to Git Bash on Windows](https://gist.github.com/evanwill/0207876c3243bbb6863e65ec5dc3f058)
