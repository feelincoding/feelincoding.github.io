---
layout: single # 페이지에 single 레이아웃을 적용
title: "[Git Blog] - 02. github.io 만들기 및 theme 적용(minimal mistakes)" # 페이지 타이틀
# post-order: 8                                  # (내 커스텀 변수) 같은 카테고리 내 정렬 순서
date: "2023-03-13 00:01:00 +0900" # 최초 포스팅 날짜. 별도 정렬 순서가 없으면 이 값으로 정렬됨. 파일명에 기록되어있다면 생략 가능.
last_modified_at: "2023-03-13 00:01:00 +0900" # 마지막 수정 날짜.
categories:
  - git-blog
tags:
  - Git Blog
# toc_label: "목차"
# toc: true
# toc_sticky: true
---

# 02. github.io 만들기 및 theme 적용(minimal mistakes)

> 다양한 theme이 존재하지만 개인적으로 minimal mistakes가 가장 좋아 보인다. ([https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/))

## git repo 생성

- https://github.com/mmistakes/minimal-mistakes fork 하기
  - fork 하게 되면 Owner: 본인 아이디, Repository name: minimal-mistakes 로 fork 된다.
  - Repository name: username.github.io 로 수정한다.
    - ex) feelincoding.github.io

## minimal mistakes 적용하기

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

- 아래 명령어 입력 후 실행 확인
  - bundle install
  - bundle exec jekyll serve
  - localhost:4000 접속

---

여기까지 완료한 commit & push 하고 본인의 username.github.io 를 들어가보면 블로그가 만들어진 것을 확인할 수 있다.

다만, username.github.io 에서 계속 확인하면 적용이 느리니 bundle install, bundle exec jekyll serve 를 통해 로컬에서 빠르게 확인하면서 블로그를 만들도록 하자.
