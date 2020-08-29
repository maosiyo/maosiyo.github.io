---
title: Spring拓展点：BeanFactoryPostProcessor接口及其子接口
date: 2020-08-10 16:23:55
tags:
- Spring
- 后端
categories: 后端
---

### 作用示例：

ConfigurationClassPostProcessor#postProcessBeanDefinitionRegistry：动态注册Bean到Spring容器中

ConfigurationClassPostProcessor#postProcessBeanFactory：增强修改Bean定义

### 消费者与消费组概念

消费组（包含多个消费者）订阅主题（分区）

<img class="lazyload inited loaded" data-width="1156" data-height="854" src="../images/消费组订阅主题.jpg">

消费者与消费组这种模型可以让整体的消费能力具备横向伸缩性，我们可以增加（或减少）消费者的个数来提高（或降低）整体的消费能力。