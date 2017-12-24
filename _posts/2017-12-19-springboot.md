---
layout: post
title: "Spring Boot"
date: 2017-12-10
categories: Spring-Boot
comments: true
tags:
- spring boot
---

# Introduction
스프링 부트 스터디

<!-- more -->

---

# 개발환경
JDK 설치하고, IDE 하나 깔고, Maven 이나 Gradle 둘 중 하나 설치하면 됨

## IDE
- Eclipse 와 IntelliJ 가 대표
- IntelliJ 의 경우 무료(Community), 유료(Pro) 버젼이 나뉘지만 무료버젼으로 부족한 부분 없음

## 빌드 및 의존성 관리
- maven 과 gradle 이 대표
- (소스에서 사용하는 외부 라이브러리에 대한) 의존성 선언하면 Maven Repository 에서 jar 파일을 다운로드
- 빌드 외에도 Task Manager 로서 활용 가능
- gradle 도 jar 파일은 Maven Central Repository 에서 다운로드 됨

### maven < gradle
  - Maven: XML 로 관리, 의존성 선언 시 최소 세줄이여서 파일이 길어짐
           빌드 관련해서 커스터마이징이 힘듬
  - gradle 이 나중에 나왔고,
    의존성 선언이 한줄이여서 보기에도 이쁜기도 하고
    groovy 로 이루어져 script 기술하여 build task 를 자유롭게 수행할 수도 있고
    각종 가이드에도 gradle 로 예제를 들어주는 등
  > 추세는 gradle 이며, NPM 과 같은 다른 언어 패키지 매니져에 비하면 둘 다 불편

### 의존성 관리 파일 예
  - Gradle
    ```groovy
    compile group: 'ch.qos.logback', name: 'logback-classic', version: '1.1.8'
    compile group: 'org.json', name: 'json', version: '20160810'
    compile group: 'io.reactivex', name: 'rxjava', version: '1.3.3'
    compile group: 'junit', name: 'junit', version: '4.12'
    ```

  - Maven

    ```xml
    <dependency>
        <groupId>com.google.code.gson</groupId>
        <artifactId>gson</artifactId>
    </dependency>
    <dependency>
        <groupId>org.jasypt</groupId>
        <artifactId>jasypt</artifactId>
        <version>1.9.2</version>
    </dependency>
    <dependency>
        <groupId>org.apache.httpcomponents</groupId>
        <artifactId>httpclient</artifactId>
    </dependency>
    ```

## 프로젝트 와꾸 잡는 네 가지 방법
1. gradle, maven 명령어로 초기화하고 알아서 소스 구조 잡는 방법
1. IDE 에서 제공하는 스프링 프로젝트 생성
1. Spring Initizlir (스프링 부트 프로젝트 소스 와꾸를 잡아주는 tool) 로 셋팅
   1. https://start.spring.io/ 에서 필요한 환경을 선택하여 다운로드 하면 zip 파일로 다운로드, 압축해제 하는 방법
      ![](https://muguliebe.github.io/assets/images/blog/spring/springInitializr.jpg)
   1. Spring CLI 를 설치하여 아래와 같이 스크립트 수행하여 generation 하는 방법
   ```bash
   spring init -d=web,thymeleaf,data-jpa,h2 --groupId=com.test --artifactId=st-spring --name="AppMain" --package-name=com.test --description="Spring Boot Study" --build gradle st-spring
   ```
   - [스프링가이드](https://docs.spring.io/spring-boot/docs/current/reference/html/getting-started-installing-spring-boot.html) 에서 Spring CLI 다운로드 파일 제공
   - [spring-boot-cli-1.5.9.RELEASE-bin.zip](https://repo.spring.io/release/org/springframework/boot/spring-boot-cli/1.5.9.RELEASE/spring-boot-cli-1.5.9.RELEASE-bin.zip)

---

# 포스트에서의 개발환경 기준 
  - JDK: 1.8
  - IDE: IntelliJ
  - Dependency Management: Gradle

---

# 스프링 부트 시작
- 부트스트랩 클래스
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

---

# Spring Boot 에 로드 된 모든 Bean 확인
  ```java
  ConfigurableApplicationContext ctx = SpringApplication.run(AppMain.class, args);

  for(String bean : ctx.getBeanDefinitionNames()){
      System.out.println("bean = " + bean);
  }
  ```

# 기본 어노테이션
RestController, Service
- @RestController
  - 클래스 및 메소드에 특정 URL 에 해당하는 서비스 진입점을 지정
  - @Controller 라는 어노테이션이 쓰였으나 Restful API 가 등장하면서 @RestController 가 생김
    - @Controller 와 다른점은, Return Type 을 자바 어느 객체로든 지정할 수 있으며, JSON 으로 변환하여 줌

- @Service
  - @Component 에서 파생 된 어노테이션으로( @Controller 도 마찬가지임 ), 단지 서비스 레이어 라는 것을 나타내 줌 

## Controller

## Service


{% if page.comments %}
{% endif %}
