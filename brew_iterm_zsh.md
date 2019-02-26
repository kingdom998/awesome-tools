## 安装brew（需要vpn----下载ShadowsocksX-NG.app.1.8.2.zip，解压进行配置）
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/instal
（安装日志输出类似brew-install.log）
```

## 卸载 brew
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall)"

sudo rm -rf /usr/local/
```

## 使用阿里云源：

* 替换brew.git:
    ```
    cd "$(brew --repo)" && git remote set-url origin https://mirrors.aliyun.com/homebrew/brew.git

* 替换homebrew-core.git:
    ```
    cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core" && git remote set-url origin https://mirrors.aliyun.com/homebrew/homebrew-core.git
    ```

* 应用生效
    ```
    brew update
    ```

* 替换homebrew-bottles:
    ```
    echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.aliyun.com/homebrew/homebrew-bottles' >> ~/.bash_profile && source ~/.bash_profile
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
    curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | ZSH=~/.dotfiles/zsh sh

    * 更改默认shell
    chsh -s /bin/zsh

    * 进入插件目录
    cd ~/.oh-my-zsh/custom/plugins

    * 声明高亮
    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git

    * 自动建议填充
    git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions

    * vi ~/.zshrc打开配置文件，进行配置        
        plugins=(git autojump zsh-autosuggestions zsh-syntax-highlighting)   # 更新插件， autojump为plugins目录下已有插件
        ZSH_THEME="ys"  # 设置主题
```

## 参考：
    - [Mac下更换Homebrew镜像源](https://blog.csdn.net/lwplwf/article/details/79097565)
    - [替换 homebrew 的源为阿里云](https://blog.csdn.net/xs18952904/article/details/87261603)