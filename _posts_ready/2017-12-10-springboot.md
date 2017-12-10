---
layout: post
title: "Spring Boot"
date: 2017-12-10
categories: Spring-Boot
comments: true
tags:
- spring boot
---

## Introduction
스프링 부트 스터디를 하며 정리

<!-- more -->

## Spring Initilizr
- Spring Initialize Command example
  ```bash
  spring init -d=web,thymeleaf,data-jpa,h2 --groupId=com.egstep --artifactId=st-spring --name="Spring Boot Study" --package-name=st-spring --description="Spring Boot Study" --build gradle st-spring
  ```

## 부트스트랩 클래스
- 스프링 부트 시작 소스 
  ```java
  @SpringBootApplication
  public class AppMain {
  
  	public static void main(String[] args) {
  		SpringApplication.run(AppMain.class, args);
  	}
  }
  ```

- @SpringBootApplication 어노테이션이 포함하는 세 가지 어노테이션
  - @Configuration, @ComponentScan, @EnableAutoConfiguration

{% if page.comments %}
{% endif %}
