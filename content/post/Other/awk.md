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


＝＝＝＝＝ advanced ＝＝＝＝＝

awk 'BEGIN{statement} {main statement} END{statement}'  
BEGIN, END 執行一次 main 可多次

String ~ /regex/[actions] => String match regex, then execute actions
String !~ /regex/[actions]  => String not match regex, then execute actions
/regex/[actions] file => file match regex, then execute actions
!/regex/[actions] file => file not match regex, then execute actions

"NF"  => Number of Fields 
"NR"  => Number of Records
"ARGC" => number of arguments
  ``awk 'BEGIN {print "Arguments =", ARGC}' One Two Three Four`` => Arguments = 5

"ARGV" => input arguments in vector

```zsh
    awk 'BEGIN { 
    for (i = 0; i < ARGC - 1; ++i) { 
        printf "ARGV[%d] = %s\n", i, ARGV[i] 
    } 
    }' one two three four
```

"FNR" => record number in current file
"IGNORECASE" => ignore case
"OFMT" => output format for numbers
"RSTART" => index of first character matched by match
"RLENGTH" => match length of string matched by match




reference: 
    <a href="https://www.hy-star.com.tw/tech/linux/awk/awk.html#awk_basic" alt="awk basic" target="_blank">awk basic</a>
    <a href="https://www.tutorialspoint.com/awk/awk_built_in_variables.htm" alt="awk tutorial" target="_blank">awk tutorial</a>


