---
layout: post
title: "스프링 프로젝트에서 Profile 설정하여 환경별 사용하기"
parent: Spring
nav_order: 4
date: 2025-03-16
tags: [Spring, MultiModule]
permalink: /spring/spring-애플리케이션에서-profile-사용하기/
---

## 목차
{: .no_toc .text-delta }

1. TOC
{:toc}

---

[Externalized Configuration](https://docs.spring.io/spring-boot/reference/features/external-config.html#features.external-config.files.profile-specific)<br/>
[Profiles](https://docs.spring.io/spring-boot/reference/features/profiles.html#page-title)

# 환경별 프로퍼티 값 사용
## 환경별 application.yml 파일명 수정/추가
- application-local.yml
- application-dev.yml
- application-prod.yml

## 각 application.yml에 profile명 설정 추가
application-dev.yml
```yml
profile-name: dev
...
```


## 인텔리제이에서 profile 값 사용
![](/assets/images/20250316/1.png)
![](/assets/images/20250316/2.png)
![](/assets/images/20250316/3.png)

dev로 바꾸면
![](/assets/images/20250316/4.png)

## Jar 실행 시 JVM 옵션 적용
jar파일이 있는 위치로 이동, 애플리케이션 기동 시 profile 옵션 추가
```bash
java -jar -Dspring.profile.active=prod api-0.0.1.SNAPSHOT.jar
```
