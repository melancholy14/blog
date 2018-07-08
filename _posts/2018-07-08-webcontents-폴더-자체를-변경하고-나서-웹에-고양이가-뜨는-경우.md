---
layout: post
title: "WebContents 폴더 자체를 변경하고 나서 웹에 고양이가 뜨는 경우"
date: 2018-07-08 19:19:31
image: 'http://tomcat.apache.org/res/images/tomcat.png'
description:
category: 'linux'
tags:
- ROOT.xml
- tomcat
- WebContents
twitter_text:
introduction: Tomcat을 restart했는데 난데없이 고양이가 나타난다면?
---
웹 개발을 하던 중 서버나 로컬에서 WebContents를 부득이하게 수정해야 하거나 실수로 수정한 경우,

tomcat을 재시작하고 나서 웹에 딱 들어갔을 때 익숙한 고양이가 보일 때가 있습니다. 바로 이 고양이가요.

![placeholder](http://tomcat.apache.org/res/images/tomcat.png "Apache Tomcat")


이럴 때는 ![#ff0a16](ROOT.xml 파일이 사라졌는 지 확인해 주세요.) ( /tomcat/conf/Catalina/localhost에 있습니다.)

**tomcat이 떠 있는 상태에서 WebContents가 변경될 경우 ROOT.xml은 삭제됩니다.**

(ROOT.xml : docBase, mysql 등 설정이 저장되어 있습니다. 이 중 docBase의 경로가 WebContents인데요. WebContents 폴더가 이름도 변경되었다 하면 이 부분의 경로를 완전히 변경해 주셔야 합니다.)

혹여, WebContents를 변경할 일이 있다면 tomcat을 내리고 변경하시길 바랍니다 :)