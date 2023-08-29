# 字体
```shell-session
$ wget https://download.jetbrains.com/fonts/JetBrainsMono-1.0.0.zip
$ unzip JetBrainsMono-1.0.0.zip
```

```shell-session
$ sudo mv JetBrainsMono-*.ttf /usr/share/fonts/
```

# 终端

```shell-session
curl -fsSL https://raw.githubusercontent.com/zimfw/install/master/install.zsh | zsh
vim ~/.zimrc
zmodule romkatv/powerlevel10k
zimfw install

chsh -s /bin/zsh (重启shell)
```


# zim

