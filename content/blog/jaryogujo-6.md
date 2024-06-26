---
title: '[자료구조] 6. 여러가지 데이터의 표현'
status: 'published'
slug: 'jaryogujo-6'
description: ''
coverImage: ''
tags: ["test"]
publishedAt: '2024-03-23T14:49:48.856Z'
---

자료 구조 3/25까지 25\~31p까지 정리(각 정리마다 100자 이상), 36p 전까지 있는 실습 문제 풀기

## 문자 데이터의 표현

### 유니코드

전 세계 모든 문자를 통일된 체계로 표현하도록 지원하는 국제 표준 코드

UTF-8, UTF-16 등 여러가지 종류가 있지만, UTF-8이 가장 흔히 쓰인다.

사용중인 운영체제와 프로그램과 관계없이 문자마다 고유한 코드 값을 제공한다.

모든 글자를 표현할 수 있지만, 프로그램의 용량이 커질 수 있다.

### ASCII

한 문자를 표현하는데 7비트로 구성된다(나머지는 존 비트). 128개의 문자를 표현할 수 있다.

![](/images/image-EzNT.png)

### 한글 코드

크게 완성형과 조합형 코드로 나눠진다.

완성형 코드는 하나의 음절에 코드를 부여해 2바이트에 표현한다.

## 이미지 데이터의 표현

### 비트맵 이미지 (래스터 이미지)

픽셀들의 집합

### 벡터 이미지

수학적 표현을 통해 그림 정보를 명령어의 집합으로 표현함

## 소리 데이터의 표현

- MP3 - 손실 압축 포맷을 이용

- WAV

- AU - 선 마이크로시스템즈가 개발한 오디오 파일 포맷

- WMA

- RA

- AAC

  등

## 동영상 데이터의 표현

자연스러운 움직임을 보여주기 위해 초당 25\~30프레임이 필요함

### 동영상 파일의 종류

- AVI - 압축률이 높지 않다
- MP4
- MOV
- ASF - 인텔이 개발한 데이터 포맷
- RM