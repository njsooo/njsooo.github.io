---
title: PowerShell(파워셸) 명렁어 정리
categories: terminal
---

## 사전 준비

```powershell
$host
```

위 명령어로 파워셸의 버전을 확인하고 [파워셸 깃허브](https://github.com/PowerShell/PowerShell)에서 최신 버전으로 설치합니다.  
[windows terminal](https://github.com/microsoft/terminal), [ohmyposh](https://ohmyposh.dev/) 등을 이용해 편의성을 위한 추가적인 환경설정을 할 수 있습니다.

## 1. 생성

### 1.1 파일 생성

[New-Item](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/new-item?view=powershell-7.3) 대신 ni를 사용해 파일을 생성 할 수 있다.

### 1.1.1 빈 파일 1개 생성

```powershell
ni a.txt
```

### 1.1.2 빈 파일 명시적으로 여러 개 생성

```powershell
ni a.txt, b.txt
```

### 1.1.3 빈 파일 반복문으로 여러 개 생성

```powershell
(1..10) | foreach {ni "tmp-$_.txt"}
```

### 1.1.4 내용을 가진 파일 생성

```powershell
ni a.txt -value "Hello!"
```

### 1.2 폴더 생성

[md](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/md) 또는 [mkdir](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/mkdir)를 사용해 폴더를 생성할 수 있다.

### 1.2.1 빈 폴더 생성

```powershell
md a
```

### 1.2.2 빈 폴더 명시적으로 여러 개 생성

```powershell
md a, b
```

### 1.2.3 빈 폴더 반복문으로 여러 개 생성

```powershell
(1..10) | foreach {md "tmp-$_"}
```

### 1.2.4 파일을 가진 폴더 생성

## 2. 삭제

## 4. 읽기

## 3. 수정

## 5. 기타

### 5.1. 폴더 GUI 열기

```powershell
start path
```

### 5.2. Alias를 이용해 명령어 이름 찾기 또는 그 반대

```powershell
gal ls
gal -d Get-ChildItem
```
