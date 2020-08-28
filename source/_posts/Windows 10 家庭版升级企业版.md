---
title: Windows 10 家庭版升级企业版
date: 2019-09-03 15:43:21
tags:
---

## 一、升级方法

### 1、方法一：直接升级

使用以下密钥直接更改，输入产品密钥后等待系统验证。

```
    win10家庭版升级专业版密钥：
        VK7JG-NPHTM-C97JM-9MPGT-3V66T
        4N7JM-CV98F-WY9XX-9D8CF-369TT （有效）
        FMPND-XFTD4-67FJC-HDR8C-3YH26
```

### 2、方法二：使用原版镜像安装专业版 windows 10

> 1、 从 msdn 下载最新的原版镜像 <br/>
> 2、 将镜像使用 Rufus 刻录到 U 盘上 <br/>
> 3、 重启后引导从 U 盘启动，系统程序启动

## 二、激活方法

1、 使用管理员权限打开 CMD

2、 输入 slmgr.vbs /upk ，卸载原来的密钥

3、 安装密钥、设置可用的 kms 服务器、激活当前系统

```
// 安装密钥
slmgr /ipk TX9XD-98N7V-6WMQ6-BX7FG-H8Q99
// 设置可用的 kms 服务器
slmgr /skms zh.us.to
// 激活当前系统
slmgr /ato
```

4、 完成后执行 slmgr.vbs /xpr 查看激活状态

## 三、可用的 key

```
1、专业版：

    W269N-WFGWX-YVC9B-4J6C9-T83GX
    MH37W-N47XK-V7XM9-C7227-GCQG9
    2X7P3-NGJTH-Q9TJF-8XDP9-T83GT
    J2WWN-Q4338-3GFW9-BWQVK-MG9TT
    NBQWQ-W9PTV-B4YWP-4K773-T6PKG
    236TW-X778T-8MV9F-937GT-QVKBB
    87VT2-FY2XW-F7K39-W3T8R-XMFGF
    KH2J9-PC326-T44D4-39H6V-TVPBY
    TFP9Y-VCY3P-VVH3T-8XXCC-MF4YK
    J783Y-JKQWR-677Q8-KCXTF-BHWGC
    C4M9W-WPRDG-QBB3F-VM9K8-KDQ9Y
    2VCGQ-BRVJ4-2HGJ2-K36X9-J66JG
    MGX79-TPQB9-KQ248-KXR2V-DHRTD
    FJHWT-KDGHY-K2384-93CT7-323RC

2、神Key(适用各版本)：

    KH2J9-PC326-T44D4-39H6V-TVPBY
    TFP9Y-VCY3P-VVH3T-8XXCC-MF4YK
    236TW-X778T-8MV9F-937GT-QVKBB
    87VT2-FY2XW-F7K39-W3T8R-XMFGF
    6K2KY-BFH24-PJW6W-9GK29-TMPWP
    RHTBY-VWY6D-QJRJ9-JGQ3X-Q2289


3、常用笔记本激活码：

    戴尔 DELL 序列号： 342DG-6YJR8-X92GV-V7DCV-P4K27
    联想 LENOVO 序列号： 22TKD-F8XX6-YG69F-9M66D-PMJBM
    三星 SAMSUNG 序列号：49PB6-6BJ6Y-KHGCQ-7DDY6-TF7CD
    宏基 ACER 序列号： YKHFT-KW986-GK4PY-FDWYH-7TP9F或    FJGCP-4DFJD-GJY49-VJBQ7-HYRR2
```
