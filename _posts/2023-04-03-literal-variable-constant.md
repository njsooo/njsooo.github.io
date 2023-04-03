---
title: "리터럴, 변수, 상수"
categories: programming_basic
---

## 리터럴(Literal)
"문자 그대로"라는 뜻으로 고정된 값을 나타내는 표기법이다.
```c
int n = 10; // 10은 literal이고 언제나 10을 뜻합니다.
char str[] = "Hello" // "Hello"는 literal이고 언제나 "Hello"를 뜻합니다.
```

## 변수(Variable)
값을 저장할 수 있는 메모리 공간이다.
메모리 주소를 사용하는 것은 불편하기 때문에 변수명을 붙여 사용한다.
```c
int n = 10
n = 20
```

## 상수(Constant)
주로 리터럴의 뜻과 혼용되어 사용되고 있다.  
변할 수 없는 수를 뜻하기도 하고 값이 확정된 후 변경할 수 없는 변수를 뜻하기도 한다.  
맥락에 따라서 판단해야 한다.
```c
const int n = 10 // 10을 상수라고도 부른다.
n = 20 // 값을 변경할 수 없다. error: expression must be a modifiable lvalue
```

## 변수명 대신 메모리 주소로 접근해 사용하기
변수명, 상수명은 메모리 공간에 붙은 이름인데 이름말고도 메모리 주소를 통해 접근해 사용하는 게 가능하다.  
심지어 재할당이 불가능한 상수에 값을 재할당시켜버릴 수 있다.

Vs Studio에서 ASLR(Address Space Layout Randomization) 기능을 끈 후 변수, 상수의 주소를 알아낸 후 접근해보자.
```c
*(int*)0x0019FED8 = 10;
printf("%d\n", *(int*)0x0019FED8); // 10
```
```c
const int n = 10;
*(int*)0x0019FED8 = 20; // 또는 *(int*)&n = 20;
printf("%d\n", *(int*)0x0019FED8); // 20
```