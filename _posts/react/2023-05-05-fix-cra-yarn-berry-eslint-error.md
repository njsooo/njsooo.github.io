---
title: "cra, yarn berry, eslint 에러 해결"
categories: react
---

## 서론
yarn berry로 create-react-app를 설치했을 때 마주치게 되는 eslint 에러 해결 방법에 대한 글입니다.

## [eslint] Failed to load config "react-app" to extend from.
설치하시면 위의 에러는 사라지지만 다른 에러가 발생합니다.
```
yarn add -D eslint-config-react-app
```


## ERROR in [eslint] Plugin "react" was conflicted between "package.json

최상위 경로에 .yarnrc.yml 파일을 생성 후 아래의 내용을 입력합니다.
```
packageExtensions:
  react-scripts@*:
    peerDependencies:
      eslint-config-react-app: '*'
```
아래의 명령어를 실행합니다.
```
yarn cache clean
yarn install
```

## 그 후 HMR이 작동하지 않는다면
여기까지 하면 에러는 발생하지 않습니다.  
만약 Hot Module Replacement(HMR)가 작동하지 않는다면 재부팅 또는 `yarn cache clean`과 `yarn install`을 다시 해보시기 바랍니다.