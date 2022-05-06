---
title: "Awk"
author: Bill.Lin
date: 2019-04-06T23:18:56+08:00
draft: false
tags: []
Description: ""
Categories: ["script", "awk"]
DisableComments: false
---

### Awk

'$0','$1'~'$N' (N 為欄位數)
$0: 一整行

example:

```zsh 
    ls -l | awk '{print $3,$9}'

    # linxinqi Applications
    # linxinqi Desktop
    # linxinqi Documents
    # linxinqi Downloads
```

, => 空格

```zsh 
    ls -l | awk '{print $3 $9}'

    # linxinqiApplications
    # linxinqiDesktop
    # linxinqiDocuments
    # linxinqiDownloads
    # linxinqiLibrary
```
自訂格式化輸出, 也可做數學運算

```zsh
    ll | awk '{print "userName: ", $3, "fileName: ", $9}'

    # userName:  linxinqi fileName:  Applications
    # userName:  linxinqi fileName:  Desktop
    # userName:  linxinqi fileName:  Documents
    # userName:  linxinqi fileName:  Downloads

    awk '{print $1 + $2}' -    #  '-' 叫鍵盤出來
    # 1 2
    # 3
```

使用外部 script

```zsh
    ls -l | awk -f {sciptFileName}

```


