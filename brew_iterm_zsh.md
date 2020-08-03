## 安装brew（需要vpn----下载ShadowsocksX-NG.app.1.8.2.zip，解压进行配置）
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
（安装日志输出类似brew-install.log）
```

## 卸载 brew
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall)"

sudo rm -rf /usr/local/
```

## 使用清华源：

* 替换brew.git:
    ```
    cd "$(brew --repo)" && git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git

* 替换homebrew-core.git:
    ```
    cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core" && git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git
    ```

* 应用生效
    ```
    brew update
    ```

* 替换homebrew-bottles:
    ```
    echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles' >> ~/.zshrc && source ~/.zshrc
    ```
## iterm2 安装
```
brew cask install iterm2
```

## git 安装
```
brew install git
```

## 安装和配置oh-my-zsh
```
    * 下载安装
    curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh

    * 更改默认shell
    chsh -s /bin/zsh

    * 进入插件目录
    cd ~/.oh-my-zsh/custom/plugins

    * 声明高亮
    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git

    * 自动建议填充
    git clone https://github.com/zsh-users/zsh-autosuggestions.git

    * vi ~/.zshrc打开配置文件，进行配置        
        plugins=(git autojump zsh-autosuggestions zsh-syntax-highlighting)   # 更新插件， autojump为plugins目录下已有插件
        ZSH_THEME="ys"  # 设置主题
```

## 问题列表
1. autojump not found. Please install it first
```
brew install autojump
```

2. plugin 'zsh-autosuggestions' not found
```
git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

3.  Insecure completion-dependent directories detected:
drwxrwxrwx  3 kd  admin   96  8  3 10:28 /usr/local/share/zsh
drwxrwxrwx  4 kd  admin  128  8  3 13:41 /usr/local/share/zsh/site-functions
```
chmod 755 /usr/local/share/
chmod 755 /usr/local/share/zsh/site-functions
```

## 参考：
    * [Mac下更换Homebrew镜像源](https://blog.csdn.net/lwplwf/article/details/79097565)
    * [替换 homebrew 的源为阿里云](https://blog.csdn.net/xs18952904/article/details/87261603)