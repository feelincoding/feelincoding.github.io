---
layout: single
title: "[Github Blog, 깃허브 블로그] - 09. 댓글 기능(giscus)로 변경 및 utterances에서 마이그레이션 하기"
date: "2023-05-03 00:02:00 +0900"
last_modified_at: "2023-05-03 00:02:00 +0900"
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

- [[Github Blog, 깃허브 블로그] - 08. 블로그 내의 검색, 댓글 기능(utterances) 추가해보기][github-blog-08]

## 0. 들어가면서

> 댓글기능을 구현해보았지만 더 이쁜걸 찾았다! <br> utterances를 giscus로 변경하고 기존 것을 마이그레이션 해보자!!

## 1. giscus로 변경하기

> giscus는 utterances와 비슷한 기능을 제공한다. <br> utterances는 github issue를 이용하여 댓글을 관리하는 반면, giscus는 github discussion을 이용하여 댓글을 관리한다. <br> 댓글을 관리하는 방식이 다르기 때문에 기존 utterances를 사용하던 것을 마이그레이션 해야한다.

### 1.1 giscus 설치

- [giscus install](https://github.com/apps/giscus) 에 접속하여 giscus를 install한다.
- only select repositories를 선택하고, 기존 utterances를 사용하던 repository(깃허브 블로그)를 선택하고 install한다.

### 1.2 giscus 설정

- 깃허브 블로그 repository의 settings에 들어간다.
- 및으로 내려 Discussions를 클릭한다.
- [gistus settings](https://giscus.app/ko) 에 들어간다.
- 저장소에 깃허브 블로그 repository 입력 한다. (ex) feelincoding/feelincoding.github.io)
- 페이지와 Discussion을 연결할 방법을 선택하세요.
  - `"Discussion 제목이 페이지 경로를 포함"`을 선택한다.
- 새 Discussion이 만들어질 카테고리를 선택하세요.
  - `"Announcements"`를 선택한다.
- 특정 기능의 사용 여부를 선택하세요.
  - `"메인 포스트에 반응 남기기"`를 선택한다.
- 테마
  - `"Github Dark Dimmed"`를 선택한다.
- giscus 사용 부분을 확인하면 아래와 같은 사진이 나온다.

  ***

  ![](/images/github-blog/2023-05-03-github-blog-09-comments-giscus-img-01.png)

  ***

  - 이 화면을 바탕으로 \_config.yml을 수정한다.

### 1.3 \_config.yml 수정

```yml
giscus:
  repo_id: "R_kgDOJJpaZw"
  category_name: "Announcements"
  category_id: "DIC_kwDOJJpaZ84CWObE"
  discussion_term: "pathname"
  reactions_enabled: "1"
  theme: "dark_dimmed"
```

## CLOSING

> ~~다음 게시글에서는 google search console, naver search advisor를 이용하여 내 블로그 글들을 검색엔진에 등록해보자.~~<br> > <br> 추가: 원래는 검색 엔진 등록과 구글 애드센스(google adsense) 등록에 관한 글을 올릴려고 했지만 아직 승인이 나지 않았다. <br> 그래서 다음 게시글은 **"giscus"**를 이용한 댓글 기능 추가에 관한 글을 올릴 예정이다.

## RECOMMEND NEXT POSTS

- [[예정입니다.][Github Blog, 깃허브 블로그] - 10. 구글(네이버) 검색 엔진 등록, 구글(네이버) 검색 노출, google search console, naver search advisor][github-blog-10]
<!-- - [[Github Blog, 깃허브 블로그] - 09. 구글(네이버) 검색 엔진 등록, 구글(네이버) 검색 노출, google search console, naver search advisor][github-blog-09] -->

[github-blog-08]: https://feelincoding.github.io/github-blog/github-blog-08-search-comments/
[github-blog-10]: https://feelincoding.github.io/github-blog/github-blog-09-comments-giscus/

### REFERENCE
