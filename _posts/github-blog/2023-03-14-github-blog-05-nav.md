---
layout: single
title: "[Github Blog, 깃허브 블로그] - 05. 상단바(nav) 만들기"
date: "2023-03-15 00:00:00 +0900"
last_modified_at: "2023-03-15 00:00:00 +0900"
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

- [[Github Blog, 깃허브 블로그] - 04. 첫 게시글 작성하기][github-blog-04]

## 0. 들어가면서

> 상단바를 만들고 <br> 상단바에 들어가는, About, Categories, Tags, Posts 페이지를 만들어 보자.

## 1. 상단 nav 설정

### 1.1 navigation.yaml

> \_data/navigation.yml 안에 main 부분이 상단에 보여지는 nav 항목들이다.

```yml
# _data/navigation.yml
main:
  - title: "About"
    url: /about/
  - title: "Posts"
    url: /year-archive/
  - title: "Categories"
    url: /categories/
  - title: "Tags"
    url: /tags/
```

- 이렇게 작성하고 로컬 환경에서 실행한다면, 화면 상단에 About, Posts, Categories, Tags 가 보일 것이다.
- 클릭한다면 Not found 화면이 뜰 것이다.
  - \_pages 폴더에 해당 화면을 생성해 주어야 하기 때문에 정상적인 동작이다.

## 2. Page 구현

> 상단바(nav)의 page를 구현해보자. <br> 후에 구현할 사이드바(sidebar)도 매우 유사한 동작을 가진다!

### 2.1 \_pages 폴더

> \_pages 폴더 안에는 구현할 page들을 넣어준다고 생각하면된다. <br> 나는 주로 사이드바, 상단바에 대한 페이지로 활용했다.

### 2.2 Posts, Categories, Tags 구현

> 이 친구들은 기본적으로 minimal mistakes에서 제공하는 \_layout 폴더의 layout을 통해 간단하게 만들 수 있다.

#### 2.2.1 Posts

> \_layout/posts.html의 형식을 따라가며 기본 제공되어 있는 layout이다. <br> \_pages 폴더 안에 posts.md 파일을 생성한다.

```yml
# _pages/posts.md
---
title: "Posts"
permalink: /year-archive/
layout: posts
author_profile: true
sidebar:
  nav: "sidebar-category"
---
```

- 이렇게 파일을 작성하고 실행 후 Posts를 클릭 해보면 아래와 같은 화면을 얻을 수 있다.

![](/images/github-blog/2023-03-14-github-blog-05-nav-img-01.png)

---

#### 2.2.2 Categories

> \_pages 폴더 안에 categories.md 파일을 생성한다.

```yml
# _pages/categories.md
---
title: "Categories"
permalink: /categories/
layout: categories
author_profile: true
sidebar:
  nav: "sidebar-category"
---
```

- 이렇게 파일을 작성하고 실행 후 Categories를 클릭 해보면 아래와 같은 화면을 얻을 수 있다.

![](/images/github-blog/2023-03-14-github-blog-05-nav-img-02.png)

---

#### 2.2.3 Tags

> \_pages 폴더 안에 tags.md 파일을 생성한다.

```yml
# _pages/tags.md
---
title: "Tags"
permalink: /tags/
layout: tags
author_profile: true
sidebar:
  nav: "sidebar-category"
---
```

- 이렇게 파일을 작성하고 실행 후 Tags 클릭 해보면 아래와 같은 화면을 얻을 수 있다.

![](/images/github-blog/2023-03-14-github-blog-05-nav-img-03.png)

---

### 2.3 About 구현

> About의 경우 기본으로 제공되는 것이 아닌 직접 만든 것이다. \_layout 폴더의 about을 직접 만들어서 새로운 layout을 만들 수도 있지만, <br> 제공되는 single.html을 통해 간단히 작성했다.

#### 2.3.1 about.md

> \_pages 폴더 안에 about.md 파일을 생성한다.

```yml
# _pages/about.md
---
title: "About"
permalink: /about/
layout: single
author_profile: true
sidebar:
  nav: "sidebar-category"
toc_label: "목차"
toc: true # 현재 페이지의 목차 보기 활성화
toc_sticky: true
---
# 이 아래 부분은 _posts 폴더 안의 파일을 만들 때 처럼 넣고 싶은 내용을 넣으면 된다.

## Hi there 👋 예시

<h1 align="center">Hi there 👋 </h1>

<h3 align="center"> My Skills...</h3>
<p align="center">
<img src="https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=C&logoColor=white"/>&nbsp;
```

- 이렇게 파일을 작성하고 실행 후 About 클릭 해보면 아래와 같은 화면을 얻을 수 있다.

![](/images/github-blog/2023-03-14-github-blog-05-nav-img-04.png)

---

## CLOSING

> 다음 게시글에서는 사이드바를 만들어보자.

## RECOMMEND NEXT POSTS

- [[Github Blog, 깃허브 블로그] - 06. 사이드바(sidebar) 만들기][github-blog-06]

[github-blog-04]: https://feelincoding.github.io/github-blog/github-blog-04-first-posts/
[github-blog-06]: https://feelincoding.github.io/github-blog/github-blog-04-first-posts/

### REFERENCE
