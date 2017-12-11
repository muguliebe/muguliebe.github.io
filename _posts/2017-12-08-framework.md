---
layout: post
title: "웹 서비스를 위한, 서버 Framework 가 가져야할 기능들"
date: 2017-12-08
categories: Spring-Boot
comments: true
tags:
- Framework
- server
---

# Introduce
- 웹 서비스를 위한 서버단 소스가 가져야할 기능 명세

<!-- more -->

# Architecture
## Presentation, Application, Persistence 구분하여 정책이 필요
### Presentation: Client 와의 연계 명세
    - Restful 때문에, JSON 리턴만으로 설계할 것이 아니라,
      Legacy와의 연계 고려하여 XML, JSON 선택하여 리턴할 수 있는 구조로 설계
    - 단순 클라이언트와의 통신 이외에도, MCI,EAI,별도 배치 스케쥴러와의 연계도 고려

### Application: Business 레이어
    - 온라인, 배치로 나누어 각각의 아키텍쳐 명세가 필요
    - Application 은 Process(프로세스 진입), Service(비즈니스 로직), DAO(DB접근) 로 구분
    - Service Context 레벨에서의 공통변수 영역과 업무별 전/후처리 관리
    - System 레벨에서의 트랜잭션 관리, 캐쉬, 거래내역, 로그, 전/후처리 관리

### Persistence: DB 와의 연계 명세
    - JPA, myBatis 를 선택하는 것만이 아닌, 디퍼드 서비스 지원도 고려

# Service Layer
- Controller, Service, DAO Layer 로 구분
- Controller와 Service가 상속받을 클래스 기술
- Controller 의 입출력은 DTO로 선언

# AOP(aspect oriented programming)
- 업무별 전/후처리가 가능하도록 필터
- 모든 Request에 대한 전/후처리 필터

## Request 에 대한 전, 후처리 기능
### 전처리
- 공통영역 변수 조립: 사용자정보, IP,URL 등

### 후처리
- 거래내역 저장
- 에러처리: 에러구분에 따른 HTTP 응답 코드 셋팅

# Logging
# Monitoring

{% if page.comments %}
{% endif %}
