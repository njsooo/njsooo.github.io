---
title: "KeyboardEvent 속성 charCode, keyCode, key, code 비교"
categories: JS event
---

## 사전 지식
[qwerty 레이아웃](https://en.wikipedia.org/wiki/QWERTY)  
[colemak 레이아웃](https://colemak.com/)

## [charCode](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/charCode), [keyCode](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/keyCode)
Deprecated 되었습니다.

## [key](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key)

소프트웨어 레이아웃을 따라갑니다.

### 물리적 키보드가 qwerty이고 소프트웨어 레이아웃이 qwerty 일 때

s를 누르면 값은 s가 됩니다.  
2를 누르면 값은 2가 됩니다.  
왼쪽 Shift를 누르면 값은 Shift가 됩니다.  
왼쪽 Shift키와 2를 누르면 이벤트가 2번 발생하며 
Shift가 한 번 @가 한 번 발생합니다.

### 물리적 키보드가 qwerty이고 소프트웨어 레이아웃이 colemak 일 때

s를 누르면 값은 r가 됩니다.  
알파벳 제외 레이아웃이 같으니 나머지는 위와 같습니다.

## [code](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/code)

물리적 키보드를 따라갑니다.

### 물리적 키보드가 qwerty이고 소프트웨어 레이아웃이 qwerty 일 때

s를 누르면 값은 keyS가 됩니다.  
2를 누르면 값은 Digit2가 됩니다.  
왼쪽 Shift를 누르면 값은 ShiftLeft가 됩니다.  
왼쪽 Shift키와 2를 누르면 이벤트가 2번 발생하며 
ShiftLeft가 한 번 Digit2가 한 번 발생합니다.

### 물리적 키보드가 qwerty이고 소프트웨어 레이아웃이 colemak 일 때

위와 같습니다.