---
title: chrome extension
tags: web
---
在chrome中安装的有道云翻译插件，我很喜欢它的指词即译模式，开启这个模式后，鼠标放在需要翻译的单词上按住Ctrl键就会自动翻译，但这样我每次Ctrl+C复制网页内容的时候就会弹出翻译弹窗，非常讨厌，而且常常会造成复制下来的只有选中的最后一个字。

因此我考虑将插件的源码修改，改为按住Alt键进行指词即译

### 获取源码即插件的.crx包
Chrome扩展文件以.crx为后缀名，在Google Chrome扩展官方网站下载扩展时，Chrome会将.crx文件下载到Chrome的Application Data文件夹的User Data\Temp下，一般是C:\Documents and Settings\User\Local Settings\Application Data\Google\Chrome\User Data\Temp，安装完成或者取消安装，该文件就会被删除。.crx实际上是一个压缩文件，使用解压文件打开这个文件就可以看到其中的文件目录。

首先，在[chrome extension](chrome://extension)中找到有道云的ID
在[这里](https://chrome-extension-downloader.com/)中下载到本地
.crx可以直接使用winrar之类的解压缩软件解压

### 了解chrome插件的结构
[read this](https://developer.chrome.com/extensions/getstarted)

### 锁定要修改的文件和位置
lookup.js

ctrlKey ---》altKey

### 测试
在chrome://extension中打开开发者模式，加载已解压的扩展程序