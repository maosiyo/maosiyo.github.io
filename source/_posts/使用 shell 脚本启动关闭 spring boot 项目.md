---
title: 使用 shell 脚本启动|关闭 spring boot 项目
date: 2019-09-03 15:43:21
tags:
---

## 启动脚本

使用 ps 命令显示瞬间行程 (process) 的动态，grep 来获取应用的进程信息，最后获取到应用的 pid。获取到 pid 的同时还检测了应用是否存在运行进程，存在则提示应用已经运行，否则就启动应用。

``nohup`` 命令与  ``&`` 组合使用能使命令在后台挂起运行。

``> ./run.log 2>&1``  将日志输出到指定的文件。

```sh
#!/bin/bash
#应用名
APP_NAME=srm-interface-front.jar

#检查程序是否在运行
is_exist(){
  pid=`ps -ef|grep $APP_NAME|grep -v grep|awk '{print $2}' `
  #如果不存在返回1，存在返回0
  if [ -z "${pid}" ]; then
   return 1
  else
    return 0
  fi
}

#启动
is_exist
if [ $? -eq "0" ]; then
  echo "${APP_NAME} is already running. pid=${pid} ."
else
  nohup java -Xms256m -Xmx512m -Dfile.encoding=utf-8 -jar $APP_NAME > ./run.log 2>&1 &
fi
```

## 关闭脚本

使用 ps 命令显示瞬间行程 (process) 的动态，grep 来获取应用的进程信息，最后获取到应用的 pid。获取到 pid 的同时还检测了应用是否存在运行进程，存在则杀掉进程，否则提示应用未运行。

``kill -9`` 命令是强杀应用，不会走释放资源的步骤。不建议使用，但是在无法关闭进程时，可以使用。此处为了避免进程杀不掉，采用了 ``kill -9`` 。


```sh
#!/bin/bash
#应用名
APP_NAME=srm-interface-front.jar

#检查程序是否在运行
is_exist(){
  pid=`ps -ef|grep $APP_NAME|grep -v grep|awk '{print $2}' `
  #如果不存在返回1，存在返回0
  if [ -z "${pid}" ]; then
   return 1
  else
    return 0
  fi
}

#停止
is_exist
if [ $? -eq "0" ]; then
  kill -9 $pid
else
  echo "${APP_NAME} is not running"
fi
```
