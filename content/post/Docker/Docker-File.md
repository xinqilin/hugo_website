---
title: "Dockerfile"
author: Bill.Lin
date: 2021-07-25T02:21:13+08:00
draft: false
tags: []
Description: ""
Categories: []
DisableComments: false
---


### build image

mvn / gradle 後 clean package (或直接install) build 出 jar

```dockerfile

FROM openjdk:11
COPY ./target/*.jar C:/ideaProjects/docker-workspace/xxx.jar
WORKDIR C:/ideaProjects/docker-workspace
RUN sh -c 'touch xxx.jar'
ENTRYPOINT ["java","-jar","xxx.jar"]

```


### build image


cd 到 Dockerfile 目錄

``docker build -t <自訂 image 名字> . ``

.代表docker build時使用當下目錄的Dockerfile。

### 打開 docker 完成
