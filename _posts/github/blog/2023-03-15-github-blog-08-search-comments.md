---
layout: single
title: "[Github Blog, 깃허브 블로그] - 08. 블로그 내의 검색, 댓글 기능(utterances) 추가해보기"
date: "2023-03-15 00:03:00 +0900"
last_modified_at: "2023-03-15 00:03:00 +0900"
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

- [[Github Blog, 깃허브 블로그] - 07. 상단바(nav), 사이드바(sidebar)에 맞추어 게시글 작성하기][github-blog-07]

## 0. 들어가면서

> 이제 게시글 까지는 문제 없다! <br> 게시글이 쌓일수록 블로그 내에서의 검색과 소통을 위한 댓글이 필요하지 않을까 싶다. <br> 이번 포스팅에서는 블로그 내에서의 검색과 댓글 기능을 추가해보자.

## 1. 검색 기능

> minimal mistakes에서는 기본적으로 검색 기능을 제공한다. <br> 제공 기능을 활용해보자.

### 1.1 \_config.yml 수정

> \_config.yml 파일을 열어서 아래와 같이 수정한다.

```yml
search: true # true, false (default)
search_full_content: true # true, false (default)
search_provider: lunr # lunr (default), algolia, google
lunr:
  search_within_pages: # true, false (default)
```

### 1.2 검색 결과 확인

> 이것으로 검색 기능이 추가 되었다. 결과는 아래와 같다.

- 상단바에 검색 아이콘이 생겼다.

  ***

  ![](/images/github-blog/2023-03-15-github-blog-08-search-comments-img-01.png)

  ***

- 검색 아이콘을 누르고 검색을 해보자.

  ***

  ![](/images/github-blog/2023-03-15-github-blog-08-search-comments-img-02.png)

  ***

## 2. 댓글 기능

> utterances를 이용하여 댓글 기능을 추가해보자.

### 2.1 utterances Install

- https://github.com/apps/utterances 에 접속하여 utterances를 install한다.
- only select repositories를 선택하고, 깃허브 블로그 저장소를 선택한다.

  ***

  ![](/images/github-blog/2023-03-15-github-blog-08-search-comments-img-03.png)

  ***

- Install을 완료한 후 나타나는 페이지의 repo에 feelincoding/feelincoding.github.io를 적는다
- Issue title contains page pathname를 체크한다.
- label은 따로 설정하지 않는다.
- Theme은 원하는 테마를 선택한다.
- Enable Utterances를 복사 해놓는다.
  - \_config.yml을 이용해 댓글 기능을 활성화할 것이다.
  - 하지만 안들어가는 부분이 있어서 따로 넣기 위해 복사한다.
    - e.g) about.md 파일에 댓글 기능을 넣고 싶다면, about.md 파일의 맨 위에 복사한 코드를 붙여넣는다.

### 2.2 \_config.yml 수정

> \_config.yml 파일을 열어서 아래와 같이 수정한다.

```yml
provider: "utterances" # false (default), "disqus", "discourse", "facebook", "staticman", "staticman_v2", "utterances", "giscus", "custom"
utterances:
  theme: "github-dark" # "github-light" (default), "github-dark"
  issue_term: "pathname" # "pathname" (default)
```

- 이제 확인해보자!!

### 2.3 댓글 기능 확인

#### 2.3.1 posts에 댓글 기능 확인

---

![](/images/github-blog/2023-03-15-github-blog-08-search-comments-img-04.png)

---

#### 2.3.2 about.md에 댓글 기능 확인

> 최 하단에 코드를 붙여 넣었다면, 댓글 기능이 추가된 것을 확인할 수 있다.

## CLOSING

> 다음 게시글에서는 google search console, naver search advisor를 이용하여 내 블로그 글들을 검색엔진에 등록해보자.

## RECOMMEND NEXT POSTS

- [[Github Blog, 깃허브 블로그] - 09. 구글(네이버) 검색 엔진 등록, 구글(네이버) 검색 노출, google search console, naver search advisor][github-blog-09]

[github-blog-07]: https://feelincoding.github.io/github-blog/github-blog-07-posts/
[github-blog-09]: https://feelincoding.github.io/github-blog/github-blog-07-posts/

### REFERENCE
