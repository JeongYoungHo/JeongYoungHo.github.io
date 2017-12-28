---
layout: post
title: "Ionic으로 앱개발 할 때 SQLite Database 디버깅 하기"
date: 2017-12-28 19:26:00 +0900
comments: true
---
Saturday10am에서 Angular를 공부하고 Ionic을 접하게 되었다.
개인적으로 만들어보고 싶은 앱(간단한..)이 있어서 Ionic으로 개발중에 있다.
서버와의 통신은 필요하지 않을 것 같아 SQLite를 사용하기로 하였다.
그런데 데이터베이스에 입력한 데이터들이 저장은 잘 되었는지 확인하기가 어려웠다.
구글링을 하여 아래와 같은 방법을 찾았다.

`adb -d shell "run-as your.package.name cat databases/database.name" > target.sqlite`
터미널에서 위 명령어를 입력하면 단말기에서의 데이터베이스 결과를 가져올 수 있다.
`your.package.name`와 `database.name`만 본인에 맞게 변경하면 된다.
target.sqlite를 시각적으로 보기 위한 툴은 [sqlitebrowser][sqlitebrowser]를 사용하면 된다.
`adb -d` 옵션 이외에도 에뮬레이터나 시리얼 넘버를 사용할 수 있는 옵션이 있다.
아래의 주소에서 확인하면 된다.

출처 : https://stackoverflow.com/a/32741481

[sqlitebrowser]: http://sqlitebrowser.org/
