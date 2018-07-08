---
layout: post
title: "StandardServer.await"
date: 2018-07-08 20:02:23
image: ''
description: StandardServer.await Invalid command 'GET / HTTP/1.1' received
category: 'eclipse'
tags:
- HTTP/1.1
twitter_text:
introduction: StandardServer.await Invalid command 'GET / HTTP/1.1' received
---
이클립스에 Tomcat을 이용하여 로컬 서버를 동작할 때 아래와 같은 에러가 발생하면

### StandardServer.await: Invalid command 'GET / HTTP/1.1' received

일단 *HTTP/1.1 Port*를 살펴봐야 합니다.


[Server] 탭에서 해당 서버를 더블클릭 > [Port] 탭에서 <font color="#ff0a16">Tomcat admin port 와 HTTP/1.1 Port가 같은 지 확인</font>하고 같으면 2개의 값이 다르게 변경해 주세요.


**StandardServer.await 관련 에러는 HTTP Port 관련 에러 일 확률이 높기 때문에**

[Server] 탭에서 해당 서버를 더블클릭하면 나오는 "Overview"에서 대부분 해결 가능합니다.