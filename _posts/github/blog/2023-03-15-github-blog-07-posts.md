---
layout: single
title: "[Github Blog, 깃허브 블로그] - 07. 상단바(nav), 사이드바(sidebar)에 맞추어 게시글 작성하기"
date: "2023-03-15 00:02:00 +0900"
last_modified_at: "2023-03-15 00:02:00 +0900"
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

- [[Github Blog, 깃허브 블로그] - 06. 사이드바(sidebar) 만들기][github-blog-06]

## 0. 들어가면서

> 사이드바와 상단바를 다 만들었다면 이제 \_posts에 폴더링을 통해 깔끔하게 게시글만 작성하면 된다. 후에 검색, 댓글, 구글 검색 노출, 구글 애드센스 등을 추가해 보자.

## 1. \_posts 폴더링

> 폴더링을 할 때는 navigation.yml을 생각하며 폴더링을 해보자. <br> 나는 navigation.yml에 있는 sidebar-category의 url을 기준으로 폴더링을 했다. <br> 내가 만든 구조는 아래와 같으며 참고해서 폴더링을 해보자.

### 1.1 \_posts structure

> yyyy-mm-dd-github-blog-title.md에서 yyyy-mm-dd는 날짜이다. <br> yyyy-mm-dd를 제외한 나머지가 title이다. <br> 즉, github-blog-title이 title이다.

```yml
feelincoding.github.io
├── _posts                     # posts
|  ├── github                  # github
|  |  ├── blog                 # github/blog
|  |  |  |── yyyy-mm-dd-github-blog-title.md
|  ├── algorithm               # algorithm
|  |  ├── baekjoon             # algorithm/baekjoon
|  |  |  |── yyyy-mm-dd-algorithm-baekjoon-title.md
|  ├──├── programmers          # algorithm/programmers
|  |  |  |── yyyy-mm-dd-algorithm-programmers-title.md
|  ├── project                 # project
|  |  ├── openmat              # project/openmat
|  |  |  └── yyyy-mm-dd-project-openmat-title.md
└── ...
```

## 2. \_posts에 게시글 작성하기

> **"블로그 만들기"** 기준으로 진행한다.

### 2.1 post 동작

- 사이드바를 클릭하면 feelincoding.github.io//github/blog로 이동하여 게시글 목록을 볼 수 있다.
- 게시글을 클릭하면 게시글의 카테고리를 기준으로 주소가 잡힌다.
  - username.github.io/categories/title/
  - e.g) feelincoding.github.io/github-blog/github-blog-07-posts/

### 2.2 post 작성

> 폴더링도 했고, 어떻게 만들어지는지 알았으니 이제 게시글을 작성해보자.

```yml
# _posts\github\blog\2023-03-15-github-blog-07-posts.md
---
layout: single
title: "[Github Blog, 깃허브 블로그] - 07. 상단바(nav), 사이드바(sidebar)에 맞추어 게시글 작성하기"
date: "2023-03-15 00:02:00 +0900"
last_modified_at: "2023-03-15 00:02:00 +0900"
categories:
  - github-blog
tags:
  - Github Blog
# toc_label: "목차"
# toc: true
# toc_sticky: true
---
# 마크다운 기반 본문 내용
```

- 이렇게 작성하고 나면 지금 보이는 화면처럼 만들어진다!

## CLOSING

> 다음 게시글에서는 블로그 내에서 검색과 댓글 기능까지 다루어 보겠다.

## RECOMMEND NEXT POSTS

- [[Github Blog, 깃허브 블로그] - 08. 블로그 내의 검색, 댓글 기능(utterances) 추가해보기][github-blog-08]

[github-blog-06]: https://feelincoding.github.io/github-blog/github-blog-06-sidebar/
[github-blog-08]: https://feelincoding.github.io/github-blog/github-blog-06-sidebar/

### REFERENCE

```

```
