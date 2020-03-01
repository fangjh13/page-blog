---
layout: post
title: Mac终端(Terminal)配置
description: mac上终端配置
modified: 2020-02-29
tags: [mac,iTerm]
readtimes: 
published: true
---


平时工作中命令行用的比图形界面多，所以有必要配置一个赏心悦目的终端界面来提高工作效率(^_^)。

![](https://img.fythonfang.com/MacScreenShot%202018-07-20-5-35-35.png)

### iTerm
第一步就是替换原来的自带终端(Terminal)，换成[iTerm](https://www.iterm2.com/)。iTerm是一个深受广大开发者欢迎的终端App，代码托管在[Github](https://github.com/gnachman/iTerm2)，可以直接在官网下载安装。

打开*iTerm2 > Preferences > General*，在`Selection`下勾上`Applications in terminal may access clipboard`使在`tmux`中鼠标选中就能复制到系统剪切板使用`command+v`粘贴

打开*iTerm2 > Preferences > Keys Tab*，把左右 option键设为`Esc+`，启用 Unix 的`Alt + B`和`Alt + F`前进和后退一个单词。

![](https://img.fythonfang.com/ScreenShot-2018-07-20-%209-34-18.png)

### Zsh & Oh My Zsh

打开 iTerm安装[Homebrew](https://brew.sh/)

```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

使用 Homebrew 安装 zsh

```shell
brew install zsh
```

[oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)是 zsh 的配置文件，使用下面命令安装

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

打开 iTerm 会耐看很多，应该长成这个样子了

![](https://img.fythonfang.com/MacScreenShot-2018-07-20-8-13.png)

配置`.zshrc`文件可以更改主题或者增加插件，默认启用robbyrussell 主题和开启了 git插件，可以根据需要更改[主题](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes)和[插件](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins)。

```shell
SH_THEME="robbyrussell"
...
plugins=(
  git
)
```

然后加第三方插件

- [*zsh-autosuggestions*](https://github.com/zsh-users/zsh-autosuggestions) 自动提示插件，根据你输入的历史命令给出提示

```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

- [*zsh-completions*](https://github.com/zsh-users/zsh-completions) 原生zsh功能补充，可以认为某些功能的尝鲜版稳定了会被加入的官方版本中

```shell
git clone https://github.com/zsh-users/zsh-completions ${ZSH_CUSTOM:=~/.oh-my-zsh/custom}/plugins/zsh-completions
```

- [*zsh-syntax-highlighting*](https://github.com/zsh-users/zsh-syntax-highlighting) 高亮不同的命令插件

```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

最后加入到`.zshrc`启用

```shell
plugins=(
  git
  zsh-autosuggestions
  zsh-syntax-highlighting
)
```
效果图

![](https://img.fythonfang.com/ScreenShot%202018-07-20-8-47.png)

### Pure

[Pure](https://github.com/sindresorhus/pure)是一个zsh提示，使用`npm`安装。

```shell
npm install --global pure-prompt
```

在`.zshrc`后添加

```shell
autoload -U promptinit; promptinit
prompt pure
```

### iterm2-snazzy & Menlo-for-Powerline fonts
- [iterm2-snazzy](https://github.com/sindresorhus/iterm2-snazzy)是一个 iTerm配色方案

下载[Github](https://github.com/sindresorhus/iterm2-snazzy)页上的`Snazzy.itermcolors`到本地，*iTerm2 > Profiles > Colors Tab*页右下角在`Color Presets...`导入`Snazzy`并选择启用。

- [Menlo-for-Powerline](https://github.com/abertsch/Menlo-for-Powerline) 是Menlo 的 Powerline的字体。

下载到本地并双击安装字体。*iTerm2 > Profiles > Text Tab*修改字体为`menlo for powerline`，字体大小选`13`。

最终效果

![](https://img.fythonfang.com/ScreenShot-2018-07-20-9-25-43.png)

PS: 上面第一张图是[Hyper](https://hyper.is/)加[hyper-snazzy](https://github.com/sindresorhus/hyper-snazzy)插件的效果
