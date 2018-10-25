---
layout: post
title: "Caused by: java.lang.NoClassDefFoundError"
date: 2018-10-24 22:13:37
image: ''
description: 자바를 빌드하던 중 클래스를 찾지 못한다는 에러가 나온다면?
category: 'java'
tags:
- eclipse
- java
- java.lang.NoClassDefFoundError, NoClassDefFoundError
twitter_text:
introduction: 이클립스에서 자바를 빌드할 때 "java.lang.NoClassDefFoundError"가 나올 경우의 대처법
---
> Caused by: java.lang.NoClassDefFoundError는 가장 직설적이고 단순한 원인이면서 여기저기 살펴봐야하는 에러입니다.

1. 말그대로 클래스를 발견하지 못한 경우
  * 해당 메소드가 사용된 곳을 가서 확인해보고 없으면 클래스 추가


2. 빌드 패스에서 클래스가 포함된 해당 프로젝트 혹은 jar가 빠진 경우
  * <font color="#ff0a16">왼쪽 마우스 > Build path > Configure build path</font>에서 추가


3. 컴파일 다 잘 되고 .class파일도 존재하는데 톰캣으로 올렸더니 안 되는 경우
  * 서버에 올리려는 프로젝트에 모듈이 존재하는 지 체크.
  * 없으면 <font color="#ff0a16">왼쪽 마우스 > properties > Deployment Assembly</font>에서 모듈을 추가시켜줍니다.


이외에도 많을 것 같지만...일단 저는 이렇게 하면 웬만하면 해결되더라고요.

**다른 원인도 더 알고 계신 분은 답글 달아주시길 바랍니다 :)