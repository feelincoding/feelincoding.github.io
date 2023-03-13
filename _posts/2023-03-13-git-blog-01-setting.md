---
layout: single                                 # 페이지에 single 레이아웃을 적용
title: "[Git Blog 만들기] - [01] 개발 환경 세팅 및 실행"  # 페이지 타이틀
# post-order: 8                                  # (내 커스텀 변수) 같은 카테고리 내 정렬 순서
date: "2023-03-13 00:00:00 +0900"              # 최초 포스팅 날짜. 별도 정렬 순서가 없으면 이 값으로 정렬됨. 파일명에 기록되어있다면 생략 가능.
last_modified_at: "2023-03-13 00:00:00 +0900"  # 마지막 수정 날짜.
categories:
    - Git Blog
tags:
    - Git Blog
    - 개발환경 세팅
---
# 01. 개발 환경 세팅 및 실행

이 문서는 ruby, jekyll, bundler 설치 및 실행 방법에 대한 내용을 다룹니다. Mac과 Window 환경에서 각각의 설치 방법을 설명하며, 로컬 환경에서 실행하는 방법도 제공합니다.

## ruby, jekyll, bundler 설치

> 요거는 알아서 해도 된다.
설치하는 이유는 로컬에서 개발하기 편할라고 하는거니까.
아래의 로컬 환경에서 실행만 잘되면 된다.

- Mac
    1. homebrew install: terminal 에 입력하여 homebrew 를 설치한다.
    (사이트 참조: [https://brew.sh/index_ko](https://brew.sh/index_ko))
    **/bin/bash -c "$(curl -fsSL [https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh](https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh))"**
    2. **brew install rbenv**: mac 은 기본적으로 ruby 가 설치되어 있다. 이에 따라 알맞은 버전의 ruby 를 설치하고 경우에 따라 원하는 버전의 ruby 를 사용해야할 일이 있을 수 있는데 rbenv 를 이용해 ruby 설치 및 버전관리를 진행한다. 터미널에 brew install rbenv 입력하여 다운.
    3. 알맞은 ruby 설치: [https://www.ruby-lang.org/en/downloads/](https://www.ruby-lang.org/en/downloads/) 를 참고하여 알맞은 version을 설치하자. 나는 2.6.8이 설치 가능한 버전이며 EOL 이어서 설치했다. rbenv install 2.6.8
        1. 설치전 체크할 것!
        2. rbenv versions:
        * system (set by /Users/"내컴퓨터이름"/.rbenv/version) 이렇게 나오면서 현재 ruby는 기존 설치되어 있던 ruby를 쓰고 있음을 알 수 있다.
        3. rbenv install -l: 설치 가능한 ruby의 버전을 확인 할 수 있다.
    4. 설치한 ruby 로 변경
        1. rbenv versions: 다시 한번 확인하면 다음과 같이 나온다.
        * system (set by /Users/"내컴퓨터이름"/.rbenv/version)
           2.6.8
        2. rbenv global 2.6.8: ruby 사용 버전을 설치한 2.6.8 로 바꿔준다.
        rbenv versions 를 입력하면 다음과 같이 바뀐 것을 알 수 있다.
           system
        * 2.6.8 (set by /Users/"내컴퓨터이름"/.rbenv/version)
        3. 터미널을 종료하고 재실행 한 뒤 ruby -v 를 입력하면 버전이 올바르게 반영 된 것을 볼 수 있다.
    5. ~~gem install --user-install bundler jekyll: jekyll, bundler 설치 하는 명령어
    만약 다음과 같은 오류가 뜬다면
    WARNING:  You don't have /Users/"내컴퓨터이름"/.gem/ruby/2.6.0/bin in your PATH, gem executables will not run.
    2.6.8 을 2.6.0 으로 인지해야 하기 때문이다. 즉 path 설정을 해주면 되는데
    echo 'export PATH="$HOME/.gem/ruby/2.6.0/bin:$PATH"' >> ~/.zshrc~~
    6. gem install bundler jekyll: 이거 일때는 괜찮?
    export PATH="$HOME/.rbenv/bin:$PATH"
    eval "$(rbenv init -)"
    를 ~/.zshrc 에 추가해준다.
    7. jekyll -v: jekyll 4.2.0, bundler -v: Bundler version 2.2.24임을 확인할 수 있다.
    8. gem 으로 install 한 것들을 다 날리고 싶다면 gem uninstall -aIx 또는 gem uninstall —aIl
- Window
    1. ruby 설치
        1. [https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/) 에서 추천하는 버전 설치
            1. 난 이거 설치함 → **Ruby+Devkit 3.1.3-1 (x64)**
            2. Which componets shall be installed? If unsure press Enter [1,3] 뜨면 → 3
        2. ruby -v, gem -v 명령어 입력으로 설치확인
    2. jeykll, bundler 설치
        1. gem install jekyll bundler


---

## 로컬 환경에서 실행

- bundle install
- bundle exec jekyll serve
- localhost:4000 접속
