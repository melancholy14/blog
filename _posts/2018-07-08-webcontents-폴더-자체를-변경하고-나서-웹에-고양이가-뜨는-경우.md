---
layout: post
title: "WebContents 폴더 자체를 변경하고 나서 웹에 고양이가 뜨는 경우"
date: 2018-07-08 19:19:31
image: 'http://tomcat.apache.org/res/images/tomcat.png'
description: Tomcat을 restart했는데 난데없이 Apache Tomcat의 고양이가 나타난다면?
category: 'linux'
tags:
- ROOT.xml
- tomcat
- WebContents
twitter_text:
introduction: Root.xml이 사라질 경우 웹이 제대로 뜨지 않는 현상 소개
---
웹 개발을 하던 중 WebContents를 부득이하게 수정했거나 실수로 수정한 경우,

tomcat을 재시작하고 나서 웹에 들어갔을 때 갑자기 어딘가에서 보았던 익숙한 고양이가 보일 때가 있습니다.

> 왜 아파치 고양이가 여기서 나타나는 거지??!!


이럴 때는 당황하지 말고...<strong><font color="#ff0a16">ROOT.xml 파일이 사라졌는 지 확인해 주세요.</font><strong>

(Root.xml 파일은 /tomcat/conf/Catalina/localhost에 있습니다.)


**tomcat이 떠 있는 상태에서 WebContents가 변경될 경우 ROOT.xml은 삭제될 가능성이 매우 높습니다.**

ROOT.xml에는 docBase, mysql 등 설정이 저장되어 있습니다. 이 중 docBase의 경로가 WebContents인데요. WebContents 자체를 변경해버리면 톰캣 입장에서는 무엇을 봐야할 지 포인터를 잃어버린 격입니다. 아무리 이름이 같아도 말이지요. 이럴 때는 ROOT.xml을 다시 만들고 재시작하시면 됩니다. 포인터를 다시 만들어주는 거죠.
P.S. WebContents 폴더가 이름도 변경되었다 하면 이 부분의 경로를 완전히 변경해 주셔야 합니다.

## 혹여, WebContents를 변경할 일이 있다면 tomcat을 내리고 변경하시길 바랍니다 :)