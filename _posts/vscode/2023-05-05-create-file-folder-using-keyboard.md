---
title: "VSCode 키보드로 파일, 폴더 생성"
categories: vscode
---

## 소개
윈도우 VSCode 환경에서 마우스 사용없이 키보드만으로 파일, 폴더를 생성하는 방법에 대한 글입니다.  

## Ctrl + Shift + E

기본 설정되어 있는 키입니다.  
위 커맨드를 사용해 포커스가 왼쪽의 Explorer와 오른쪽의 코드 입력창을 오갈 수 있습니다.  
Explorer에 포커스가 되었을때 위, 아래 방향키로 움직일 수 있고 좌우 방향키로 폴더를 펼치거나 접을 수 있습니다.

## 키 바인딩

1. Keyboard Shortcuts 페이지를 두 가지 방법으로 열 수 있습니다.
- 왼쪽 맨 아래 톱니바퀴 클릭 후 Keyboard Shortcuts 클릭
- `Ctrl + K` 누른 후 `Ctrl + S`  
2. Keyboard Shortcuts 페이지에서 오른쪽 위 버튼을 눌러 keybindings.json 파일을 엽니다.
3. 아래 내용을 입력합니다.
```json
[
  {
    "key": "ctrl+n",
    "command": "explorer.newFile",
    "when": "explorerViewletFocus"
  },
  {
    "key": "ctrl+shift+n",
    "command": "explorer.newFolder",
    "when": "explorerViewletFocus"
  }
]
```

## 사용법

1. `Ctrl + Shift + E` 키로 Explorer에 포커스 
2. 방향키로 원하는 위치 이동
3. 파일 생성을 원하면 `Ctrl + N`
4. 폴더 생성을 원하면 `Ctrl + Shift + N`