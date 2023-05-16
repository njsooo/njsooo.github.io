---
title: "Git 깃 초기 설정"
categories: Git
---

## 명령어를 이용해 필수 설정하기
이름, 이메일, CRLF 설정을 합니다.  
윈도우 유저라면 autocrlf를 true로 아니라면 input으로 설정합니다.
```
git config --global user.name "your_name"
git config --global user.email "your_email"
git config --global core.autocrlf true 또는 input
```

## 에디터를 이용해 필수 설정하기
Visual Studio Code를 기본 에디터로 설정합니다.
```
git config --global core.editor "code --wait"
```

아래 명령어를 입력하면 Visual Studio Code가 열립니다.
```
git config --global -e
```

Visual Studio Code에 아래의 내용을 입력하시면 됩니다.  
윈도우 유저라면 autocrlf를 true로 아니라면 input으로 설정합니다.
```
[core]
	editor = code --wait
	autocrlf = true 또는 input
[user]
	name = your_name
	email = your_email
```

## 모든 설정 확인
```
git config --list
```

## 특정 설정 확인하기
```
git config user.name
git config user.email
```

## 별명 설정하고 확인하기
매번 git status를 입력하기 번거롭다면 별명을 설정해 git st만 입력할 수 있습니다.
```
git config --global alias.st status // 설정하기
git config --global alias.st // 설정 확인
```
