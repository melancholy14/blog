---
layout: post
title: "Caused by: javax.servlet.ServletException: no 파일명 in java.library.path"
date: 2018-10-24 22:24:47
image: ''
description: 리눅스에서 자바 라이브러리를 참조하지 못한다면?
category: 'linux'
tags:
- Java Native Interface
- javax.servlet.ServletException
- jeus
- JNI
- linux
- tomcat
twitter_text:
introduction: 리눅스(혹은 제우스)에서 java.library.path를 찾지 못할 때의 대처법
---
<strong>javax.servlet.ServletException: no 파일명 in java.library.path</strong> 가 발생했을 때는 <strong><font color="#ff0a16">"JNI 즉, Java Native Interface를 찾을 수 없다."</font></strong>는 의미입니다.  


그래서 자바 라이브러리 경로를 설정하는 방법을 구글링을 해보면 다음과 같은 2가지 방법이 주로 나오죠.

1. LD_LIBRARY_PATH에 해당 라이브러리 경로를 추가한다.
    <em>export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/파일이 있는 경로</em>

2. 자바 프로그램을 실행할 때 -D 옵션으로 지정한다.
    <em>java -Djava.library.path = 파일이 있는 경로</em>

​
그런데, **Jeus 는 ​서버를 올릴 때 java.library.path 로 제우스 시스템 라이브러리를 참조합니다.
<font color="blue"><em>JEUS_HOME/lib/system</em>에 해당하는 파일을 복사</font>해 주고 에러가 해결되는지 확인해 보시길 !!