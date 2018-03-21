---
layout: post
title:  "npm eaccess problem"
date:   2018-03-21 00:00:00 +0900
comments : true
categories: npm eaccess problem
---
macOS 기반으로 작성되었습니다.

npm을 설치하고 나서 패키지 설치 중 EACCESS 오류가 나며 진행이 안될 경우가 있다.

이런 경우에 nvm을 이용한 오류 해결 방법을 알아보겠다.
[npm 공식 문서](https://docs.npmjs.com/getting-started/fixing-npm-permissions)에도 있는 내용이다.

우선 npm을 이미 설치한 상태라면 node의 완전한 제거를 필요로 한다.
제거 방법은 [여기](https://gomugom.github.io/how-to-remove-node-from-macos/)서 확인할 수 있다.

완전히 삭제를 진행했다면 본격적으로 nvm을 설치해보자.

아래의 내용은 [여기](https://github.com/creationix/nvm/blob/master/README.md#installation)서 확인할 수 있다. 

nvm을 설치하기 위해 터미널에 아래의 명령어를 입력하자.
```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash
```

그 다음으로 `~/.bash_profile`에 아래의 내용을 추가하자.
```
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
```

내용을 추가했으면 실행하고 있는 터미널을 종료하자.

nvm의 설치가 잘 되었는지 확인하기 위해서 아래의 명령어를 입력하자.
```
command -v nvm
```
그 결과로 'nvm'이 출력된다면 nvm이 정상적으로 설치된 것이다.

이제 nvm 설치가 완료되었다.
```
nvm install node
```
위 명령어를 이용하여 node를 설치하고 나면 npm 패키지 설치가 정상적으로 되는것을 확인할 수 있다.
