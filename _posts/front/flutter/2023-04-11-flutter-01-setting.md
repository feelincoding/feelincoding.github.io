---
layout: single
title: "[Flutter] - 01. Mac M1 환경에서 Flutter 설치하기, vscode 세팅하기"
date: "2023-04-11 00:00:00 +0900"
last_modified_at: "2023-04-11 00:00:00 +0900"
categories:
  - front-flutter
tags:
  - Flutter
# toc_label: "목차"
# toc: true
# toc_sticky: true
---

<br/>

## RECOMMEND BEFORE POSTS

> 없음

## 0. 들어가면서

> Mac M1 환경에서 Flutter를 세팅하고 VSCode를 이용해 보자.

## 1. Flutter 세팅

### 1.1 Flutter SDK 설치

- 중요: Apple Silicon Mac 에 설치하는 경우 일부 보조 도구 에 사용할 수 있는 Rosetta 번역 환경이 있어야 합니다 . 다음을 실행하여 수동으로 설치할 수 있습니다.

  ```bash
  $ sudo softwareupdate --install-rosetta --agree-to-license
  ```

- [Flutter SDK 다운로드](https://flutter.dev/docs/get-started/install/macos#install-the-flutter-sdk)에서 SDK를 다운로드 받는다.
- 다운로드 받은 SDK를 압축 해제한다.(자신이 원하는 위치에)
  ```bash
  $ cd ~/development
  $ unzip ~/Downloads/flutter_macos_2.2.3-stable.zip
  ```
- 환경변수를 설정한다.
  ```bash
  $ vim ~/.zshrc
  ```
  ```bash
  export PATH="$PATH:`pwd`/flutter/bin"
  # pwd에 본인이 압축을 푼 위치를 넣는다.(ex. export PATH="$PATH:/Users/username/development/flutter/bin")
  ```
  ```bash
  $ source ~/.zshrc
  ```
- 설치가 잘 되었는지 확인한다.
  ```bash
  $ flutter doctor
  ```
- 만약 dart은 신뢰할 수 없다는 식의 화면이 뜨면 시스템 설정의 보안 설정에서 허용해준다.

## 2. iOS 세팅

### 2.1 xcode 설치

- [xcode 설치](https://apps.apple.com/kr/app/xcode/id497799835?mt=12)에서 설치한다.
- 설치가 완료되면 다음 명령어를 실행한다.
  ```bash
  $ sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
  $ sudo xcodebuild -runFirstLaunch
  ```
- license agreement를 동의한다.

### 2.2 CocoaPods 설치

- 다음 명령어를 실행한다.
  ```bash
  $ sudo gem install cocoapods
  ```
- 다음 명령어를 통해 설치가 잘 되었는지 확인한다.
  ```bash
  $ pod --version
  ```
- 설치가 완료되면 다음 명령어를 실행한다.
  ```bash
  $ pod setup
  ```
- 만약 환경 변수를 못 찾는다면 기존에 설치한 것을 지우고
  ```bash
  $ sudo gem uninstall cocoapods
  ```
- brew를 이용해 설치한다.
  ```bash
  $ brew install cocoapods
  ```
- 다음 명령어를 통해 설치가 잘 되었는지 확인한다.
  ```bash
  $ pod --version
  ```
- 설치가 완료되면 다음 명령어를 실행한다.
  ```bash
  $ pod setup
  ```

## 3. Android 세팅

### 3.1 Android Studio 설치

- [Android Studio 설치](https://developer.android.com/studio)에서 설치한다.
  - Mac with Apple chip을 다운 받는다.
- 설치한 파일을 더블 클릭 후 안드로이드 스튜디오를 application 폴더로 드래그 앤 드랍한다.

### 3.2 Android SDK 설치

- 안드로이드 스튜디오를 실행한다.
- 모두 next를 눌러주면서 마지막에 accept를 누르고 finish를 누른다.
- 설치중...
- finish 클릭
- more actions 클릭
- SDK Manager 클릭
- SDK Tools 탭 클릭
- Android SDK Command-line Tools 항목 체크
- apply 클릭, ok 클릭
- 설치중...
- finish 클릭
- ok 클릭

### 3.3 Android license 설정

- 다음 명령어를 실행한다.
  ```bash
  $ flutter doctor --android-licenses
  ```
- 모든 질문에는 y를 입력한다.

### 3.4 etc

- 안드로이드 스튜디오에서 개발을 할 것이라면 안드로이드 스튜디오에서 flutter를 사용할 수 있도록 설정해준다.
  - flutter plugin 설치
- 하지만 우리는 vscode를 사용할 것이기 때문에 vscode에서 flutter를 사용할 수 있도록 설정할 것이다!

## 4. flutter doctor

> flutter doctor 입력해서 잘 설치 했는지 확인하자!<br>

- 다음과 같이 나오면 성공!

```bash
$ flutter doctor
-> no issues found!
```

## CLOSING

> 없음

## RECOMMEND NEXT POSTS

> 없음

### REFERENCE

> 없음
