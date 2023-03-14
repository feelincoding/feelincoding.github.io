---
layout: single
title: "[Git Blog] - 03. minimal mistakes 기초"
date: "2023-03-14 00:00:00 +0900"
last_modified_at: "2023-03-14 00:00:00 +0900"
categories:
  - git-blog
tags:
  - Git Blog
# toc_label: "목차"
# toc: true
# toc_sticky: true
---

<br/>

## RECOMMEND POSTS BEFORE THIS

- [[Git Blog] - 02. github.io 만들기 및 theme 적용(minimal mistakes)][git-blog-02]

## 0. 들어가면서

> **\_config.yml 파일만 수정하면 된다.** <br> \_config.yml 파일 수정 만으로 기본적인 블로그의 모습을 바꿀 수 있다. 따라서, \_config.yml 파일을 수정하면서 기본적인 블로그의 모습을 바꿔보자.

## 1. Theme Settings

### 1.1 minimal_mistakes_skin

> 블로그의 외형을 바꿔 색상을 바꿀 수 있다. <br>[minimal mistakes docs 참조](https://mmistakes.github.io/minimal-mistakes/docs/configuration/#skin)

```yml
minimal_mistakes_skin: "dark" # "default", "air", "aqua", "contrast", "dark", "dirt", "neon", "mint", "plum", "sunrise"
```

## 2. Site Settings

### 2.1 locale

> 블로그의 기본 언어 세팅을 바꿀 수 있다. <br>[minimal mistakes docs 참조](https://mmistakes.github.io/minimal-mistakes/docs/configuration/#site-locale)

```yml
locale: "en-US" # "en-US", "ko"
```

### 2.2 블로그 제목 및 설명

> 블로그의 제목, 설명 등 기본적인 요소를 바꿀 수 있다. <br>[minimal mistakes docs 참조](https://mmistakes.github.io/minimal-mistakes/docs/configuration/#site-title)

```yml
title: "Feelincoding Tech Blog"
title_separator: "-"
subtitle: "기록을 위한 테크 블로그" # site tagline that appears below site title in masthead
name: "feelincoding"
description: "기록을 위한 테크 블로그"
url: "https://feelincoding.github.io" # the base hostname & protocol for your site e.g. "https://mmistakes.github.io"
baseurl: # the subpath of your site, e.g. "/blog"
repository: "feelincoding/feelincoding.github.io" # GitHub username/repo-name e.g. "mmistakes/minimal-mistakes"
```

### 2.2 Site Author

> 자기소개, 링크 추가 등을 할 수 있다. <br>[minimal mistakes docs 참조](https://mmistakes.github.io/minimal-mistakes/docs/configuration/#site-author)

```yml
author:
  name: "feelincoding" # "Your Name"
  avatar: # path of avatar image, e.g. "/assets/images/bio-photo.jpg"
  bio: "feelincoding@gmail.com" # "I am an **amazing** person."
  location: "Republic of Korea" # "Somewhere"
  email:
  links:
    - label: "YouTube"
      icon: "fab fa-fw fa-youtube"
      url: "https://www.youtube.com/@feelincoding8853"
    - label: "GitHub"
      icon: "fab fa-fw fa-github"
      url: "https://github.com/feelincoding"
    - label: "stackoverflow"
      icon: "fab fa-fw fa-stack-overflow"
      url: "https://stackoverflow.com/users/21084338/feelincoding"
```

### 2.2 Site Author

> 앞으로 올릴 게시글에 대한 기본 설정이다. <br>[minimal mistakes docs 참조](https://mmistakes.github.io/minimal-mistakes/docs/configuration/#front-matter-defaults)

```yml
# Defaults
defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: true
      comments: true
      share: true
      related: true
      toc_label: "목차" # 게시글에 목차가 있을 경우, 목차의 제목을 바꿀 수 있다.
      toc: true # 현재 페이지의 목차 보기 활성화
      toc_sticky: true # 현재 페이지의 목차를 스크롤 시에도 고정
```

## CLOSING

> 다음 게시글에서는 게시글을 작성하는 방법에 대해 알아보자.

## RECOMMEND NEXT POSTS

- [[Git Blog] - 04. 첫 게시글 작성하기][git-blog-04]

[git-blog-02]: https://feelincoding.github.io/git-blog/git-blog-02-create-github-io/
[git-blog-04]: https://feelincoding.github.io/git-blog/git-blog-04-first-posts/

### REFERENCE
