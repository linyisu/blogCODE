---
title: md 文件快捷上传指令
tags: 
  - HEXO
categories: 
  - 网站
---

```bash
call @echo off

%1 mshta vbscript:CreateObject("Shell.Application").ShellExecute("cmd.exe","/c %~s0 ::","","runas",1)(window.close)&&exit

call cd /d "%~dp0"

call cd /d "你的本地文件路径"
call echo 正在清理旧文件...
call hexo clean

call echo 正在生成静态文件...
call hexo g

call echo 正在部署到服务器...
call hexo d

call echo 所有操作已完成！
call @cmd.exe
```

可将上面的代码复制到记事本，并更改后缀名为`.bat`, 即可快捷上传。

**记得将第 $7$ 行行代码更改为本地文件的路径！**