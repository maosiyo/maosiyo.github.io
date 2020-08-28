---
title: 使用 bat 脚本启动|关闭 spring boot 项目
date: 2019-09-03 15:43:21
tags:
---

## 启动脚本

spring boot 项目打包出来的 jar 包要和 bat 脚本文件在同一目录下，启动前会检测端口是否被占用。端口被占用将提示占用端口的进程 PID，可以使用关闭脚本关闭或手动关闭。

```bat
@echo off
rem 应用名
set APP_NAME=hzero-generator
set port=8090
for /f "tokens=1-5" %%a in ('netstat -ano ^| find ":%port%"') do (
    if "%%e" == "" (
        set pid=%%d
    ) else (
        set pid=%%e
    )
)
if NOT "%pid%" == "" (
   echo "port %port% is already occupied by PID %pid%!"
   pause
) else (
    rem 项目启动命令（后台运行）
    start java -Xms256m -Xmx512m -Dfile.encoding=utf-8 -jar .\%APP_NAME%.jar
)
```

## 关闭脚本

关闭脚本通过检测占用应用端口的进程 PID，然后杀掉该进程及相关的进程来实现关闭应用。端口未被占用将提示该端口未被占用，不会做任何操作。

```bat
@echo off
SETLOCAL ENABLEDELAYEDEXPANSION
rem 停止指定端口的命令脚本 端口号
set port=8090
for /f "tokens=1-5" %%a in ('netstat -ano ^| find ":%port%"') do (
    if NOT "%%e" == "0" (
        set pid= %%e
        taskkill /f /pid !pid!
    )
)

if "%pid%" == "" (
  echo "port %port% is not running anything!"
  pause
)
```
