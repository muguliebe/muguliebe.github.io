---
layout: post
title: "Spring Boot 개발 시 자동 리로드 Reload"
date: 2017-12-10
categories: Spring-Boot
comments: true
tags:
- spring boot
- spring boot devtools
---

## Introduction
스프링 부트 개발 중 코드 변경 시, 자동 리로드 되게 하는 방법

<!-- more -->

## 의존성(dependency) 추가
- maven
  ```xml
  <dependencies>
      <dependency>
          <groupId>org.springframework.boot</groupId>
          <artifactId>spring-boot-devtools</artifactId>
          <optional>true</optional>
      </dependency>
  </dependencies>
  ```
- gradle
  ```gradle
  dependencies {
      compile("org.springframework.boot:spring-boot-devtools")
  }
  ```

## application property
```shell
spring.devtools.livereload.enabled=true
```

## IntelliJ 에서 개발하는 경우
- Preferences > Build,Execution,Deployment > Compiler
  - Build project Automatically: Check 

{% if page.comments %}
{% endif %}
