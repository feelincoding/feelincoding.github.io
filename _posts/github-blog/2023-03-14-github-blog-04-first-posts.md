---
layout: single
title: "[Github Blog, 깃허브 블로그] - 04. 첫 게시글 작성하기"
date: "2023-03-14 00:01:00 +0900"
last_modified_at: "2023-03-14 00:01:00 +0900"
categories:
  - github-blog
tags:
  - Github Blog
# toc_label: "목차"
# toc: true
# toc_sticky: true
---

<br/>

## RECOMMEND POSTS BEFORE THIS

- [[Github Blog, 깃허브 블로그] - 03. minimal mistakes 기초][github-blog-03]

## 0. 들어가면서

> 이번에 기본적인 게시글 작성법에 대해서 알아보자. <br> 하지만 추후에 사이드바, 상단바를 만들고 이에 맞게 게시글을 작성할 것이기에 **이 게시글을 건너뛰어도 무방하다.**

## 1. \_posts

### 1.1 폴더 생성

> 폴더가 없으면 생성해준다.

```yml
feelincoding.github.io
├── _posts                     # posts
|  ├── 2023-03-13-test.md      # post, 파일명은 YYYY-MM-DD-제목.md
```

### 1.1 게시글 작성

> 2023-03-13-test.md 에 대한 작성법이다.

```yml
---
# ---로 둘러싸인 부분은 front matter라고 한다. front matter는 jekyll에서 사용되는 부분이다.
layout: single # 기본적으로 post는 single로 설정한다.
title: "test" # 게시글 제목
date: "2023-03-13 00:00:00 +0900" # 게시글 작성일
last_modified_at: "2023-03-13 00:00:00 +0900" # 게시글 수정일
categories: # 카테고리
  - test
tags: # 태그
  - test
# 이 아래부터는 마크다운으로 작성한다.(실제 게시글 내용)
---
# 1. 첫번째 게시글

- 첫번째 게시글입니다.
```

- 파일명은 YYYY-MM-DD-제목.md 형식으로 작성한다.

- 게시글 작성시에는 **마크다운**을 사용한다.
- 게시글 작성시 #, ##, ###, #### 등의 헤더에 따라 목차가 생성된다.
- categories, tags는 필수가 아니다. 다만, 추후에 상단바, 사이드바 구현시 사용된다.

## 2. 게시글 확인

> 사진을 보면 사이드바, 상단바 등이 존재하지만 이는 추후에 구현할 것이다.

### 2.1 게시글 목록 확인

![](/images/github-blog/2023-03-14-github-blog-04-first-posts-img-02.png)

### 2.2 게시글 내용 확인

![](/images/github-blog/2023-03-14-github-blog-04-first-posts-img-01.png)

## CLOSING

> 다음 게시글에서는 상단바와 사이드바를 만들어보자.

## RECOMMEND NEXT POSTS

- [[Github Blog, 깃허브 블로그] - 05. 상단바(nav) 만들기][github-blog-05]

[github-blog-03]: https://feelincoding.github.io/github-blog/github-blog-03-minimal-mistake-basic/
[github-blog-05]: https://feelincoding.github.io/github-blog/github-blog-05-nav/

### REFERENCE
