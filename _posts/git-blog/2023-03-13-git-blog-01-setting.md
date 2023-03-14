---
layout: single
title: "[Git Blog] - 01. 개발 환경 세팅 및 실행"
date: "2023-03-13 00:00:00 +0900"
last_modified_at: "2023-03-13 00:00:00 +0900"
categories:
  - git-blog
tags:
  - Git Blog
  - Setting
# toc_label: "목차"
# toc: true
# toc_sticky: true
---

<br/>

## 0. 들어가면서

> 이 문서는 ruby, jekyll, bundler 설치 및 실행 방법에 대한 내용을 다룹니다. Mac과 Window 환경에서 각각의 설치 방법을 설명하며, 로컬 환경에서 실행하는 방법도 제공합니다.

## 1. ruby, jekyll, bundler 설치

> 요거는 알아서 해도 된다.
> 설치하는 이유는 로컬에서 개발하기 편할라고 하는거니까.
> 아래의 로컬 환경에서 실행만 잘되면 된다.

### 1.1 Window

- ruby 설치
  - [https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/) 에서 추천하는 버전 설치
  - 난 이거 설치함 → **Ruby+Devkit 3.1.3-1 (x64)**
  - Which componets shall be installed? If unsure press Enter [1,3] 뜨면 → 3
  - ruby -v, gem -v 명령어 입력으로 설치확인
- jeykll, bundler 설치
  - gem install jekyll bundler

### 1.2 Mac

- ruby 설치:
  - brew install ruby
- jeykll, bundler 설치
  - gem install jekyll bundler

## 2. 로컬 환경에서 실행

- bundle install
- bundle exec jekyll serve
- localhost:4000 접속

## RECOMMEND NEXT POSTS

- [[Git Blog] - 02. github.io 만들기 및 theme 적용(minimal mistakes)][git-blog-02]

[git-blog-02]: https://feelincoding.github.io/git-blog/git-blog-02-create-github-io/
