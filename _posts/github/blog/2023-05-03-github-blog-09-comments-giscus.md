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

## 2. utterances 마이그레이션

> utterances를 사용하던 댓글들을 giscus로 마이그레이션 해보자.<br>

- utterances를 사용하던 댓글들은 github issue에 저장되어 있기 때문에 이를 giscus로 옮겨야 한다.
- utterances를 사용하던 댓글들을 giscus로 옮기기 위해서는 모른다... 나는 노가다만 알고 있다 ㅠㅠ
- `혹여라도 방법을 아시는 분은 댓글로 알려주시면 감사하겠습니다.`

### 2.1 utterances 댓글 확인

- repository의 issues에 들어가면 utterances를 사용하던 댓글들이 저장되어 있다.
- 댓글을 클릭해보면
- 우측 하단에 `Convert to discussion` 버튼이 있다.
- 카테고리를 선택하고(아까 선택한 Announcements) `I understand, convert this issue.` 버튼을 클릭한다.
- 그리고 포스트를 확인해보면 댓글이 옮겨진 것을 확인할 수 있다!!!

## CLOSING

> 다음 게시글은 구글 에드센스 등록을 위한 구글 검색 엔진 등록 및 구글 검색 노출에 대해 알아보자! <br>
> 기왕이면 네이버 검색 엔진 등록 및 네이버 검색 노출도 알아보자!

## RECOMMEND NEXT POSTS

- [[예정입니다.][Github Blog, 깃허브 블로그] - 10. 구글(네이버) 검색 엔진 등록, 구글(네이버) 검색 노출, google search console, naver search advisor][github-blog-10]

[github-blog-08]: https://feelincoding.github.io/github-blog/github-blog-08-search-comments/
[github-blog-10]: https://feelincoding.github.io/github-blog/github-blog-09-comments-giscus/

### REFERENCE
