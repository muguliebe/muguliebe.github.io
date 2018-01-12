---
layout: post
title: "Lombok 사용 시 IntelliJ 셋팅"
date: 2018-01-12
categories: java
comments: true
tags:
- java
- intellij
- lombok
---

# Introduction
Lombok 사용 시 IntelliJ 셋팅 ( lombok 사용법이 아님 )

<!-- more -->

# IntelliJ 셋팅
## plugin 추가
> Preference > Plugins > Browse Repositories > lombok 검색

![](http://muguliebe.github.io/assets/images/blog/180102/intellij-lombok.png)

## 프로젝트 설정 2 개
- Build Automatically 활성화
![](http://muguliebe.github.io/assets/images/blog/180102/intellij-javacompiler.png)

- Annotation Processing 활성화
![](http://muguliebe.github.io/assets/images/blog/180102/intellij-annotation.png)

## Application 수행 시에도 컴파일 되도록 설정 변경
> Find Action > Registry 검색 > compiler.automake.allow.when.app.running 활성화   

![](http://muguliebe.github.io/assets/images/blog/180102/intellij-registry-findaction.png)
![](/assets/images/blog/180102/intellij-registry-compile.png)

# Gradle Dependency 추가
- gradle
  ```groovy
  compile group: 'org.projectlombok', name: 'lombok', version: '1.16.20'
  ```

 
{% if page.comments %}
{% endif %}
