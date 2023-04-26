---
layout: single
title: "[Github Blog, 깃허브 블로그] - 02. github.io 만들기 및 theme 적용(minimal mistakes)"
date: "2023-03-13 00:01:00 +0900"
last_modified_at: "2023-03-13 00:01:00 +0900"
categories:
  - github-blog
tags:
  - Github Blog
# toc_label: "목차"
# toc: true
# toc_sticky: true
---

<br/>

## RECOMMEND BEFORE POSTS

- [[Github Blog, 깃허브 블로그] - 01. 개발 환경 세팅 및 실행][github-blog-01]

## 0. 들어가면서

> 다양한 jekyll의 theme이 존재하지만 개인적으로 minimal mistakes가 가장 좋아 보인다. ([minimal-mistakes][minimal-mistakes-url])
> 제일 자료가 많고 구글링 하기 편한 듯 하여 선택했다.

## 1. git repo 생성

### 1.1 [minimal-mistakes][minimal-mistakes-url] clone 하기

- fork를 하면 잔디가 안심어진다!!
- Repository name: username.github.io 로 repo를 만든다.
  - e.g) feelincoding.github.io
- [minimal-mistakes][minimal-mistakes-url] clone 해서, 미리 만든 repo에 clone한 프로젝트 내용물을 붙여 넣는다.

### 1.2 [minimal-mistakes][minimal-mistakes-url] fork 하기

- fork 하게 되면 Owner: 본인 아이디, Repository name: minimal-mistakes 로 fork 된다.
- Repository name: username.github.io 로 수정한다.
  - e.g) feelincoding.github.io

## 2. [minimal-mistakes][minimal-mistakes-url] 초기 세팅 하기

### 2.1 파일 정리

- 본인의 repo를 clone 한 후 아래의 파일을 삭제한다.
  - `.editorconfig`
  - `.gitattributes`
  - `.github`
  - `/docs`
  - `/test`
  - `CHANGELOG.md`
  - `minimal-mistakes-jekyll.gemspec`
  - `README.md`
  - `screenshot-layouts.png`
  - `screenshot.png`

### 2.2 Gemfile 수정

- Gemfile 수정: 아래와 같은 내용으로 수정한다.

  ```ruby
  source "https://rubygems.org"

  # Hello! This is where you manage which Jekyll version is used to run.
  # When you want to use a different version, change it below, save the
  # file and run `bundle install`. Run Jekyll with `bundle exec`, like so:
  #
  #     bundle exec jekyll serve
  #
  # This will help ensure the proper Jekyll version is running.
  # Happy Jekylling!

  # gem "github-pages", group: :jekyll_plugins

  # To upgrade, run `bundle update`.

  gem "jekyll"
  gem "minimal-mistakes-jekyll"

  # The following plugins are automatically loaded by the theme-gem:
  #   gem "jekyll-paginate"
  #   gem "jekyll-sitemap"
  #   gem "jekyll-gist"
  #   gem "jekyll-feed"
  #   gem "jekyll-include-cache"
  #
  # If you have any other plugins, put them here!
  # Cf. https://jekyllrb.com/docs/plugins/installation/
  group :jekyll_plugins do
  end
  ```

## 3. [minimal-mistakes][minimal-mistakes-url] 적용 확인 하기

### 3.1 로컬에서 확인하기

- bundle install
- bundle exec jekyll serve
- localhost:4000 접속

### 3.2 github.io에서 확인하기

- 여기까지 완료한 commit & push 하고 본인의 username.github.io 를 들어가보면 블로그가 만들어진 것을 확인할 수 있다.

- 다만, username.github.io 에서 계속 확인하면 적용이 느리니 bundle install, bundle exec jekyll serve 를 통해 로컬에서 빠르게 확인하면서 블로그를 만들도록 하자.

## CLOSING

## RECOMMEND NEXT POSTS

- [[Github Blog, 깃허브 블로그] - 03. minimal mistakes 기초][github-blog-03]

[minimal-mistakes-url]: https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/
[github-blog-01]: https://feelincoding.github.io/github-blog/github-blog-01-setting/
[github-blog-03]: https://feelincoding.github.io/github-blog/github-blog-03-minimal-mistakes-basic/
