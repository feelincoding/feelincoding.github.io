---
layout: single
title: "[Github Blog, 깃허브 블로그] - 06. 사이드바(sidebar) 만들기"
date: "2023-03-15 00:01:00 +0900"
last_modified_at: "2023-03-15 00:01:00 +0900"
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

- [[Github Blog, 깃허브 블로그] - 05. 상단바(nav) 만들기][github-blog-05]

## 0. 들어가면서

> 사이드바(sidebar)를 만들고 <br> 사이드바에 들어가는 카테고리들에 대해 페이지를 만들어 보자. <br> 상단바 만드는 것과 꽤나 유사하다!!

## 1. 사이드바(sidebar) 설정

### 1.1 navigation.yaml

> \_data/navigation.yml 안에 main과 같은 depth로 아래에 추가할 부분이 사이드바에 보여지는 항목들이다.

```yml
# _data/navigation.yml
sidebar-category: # 이 이름을 _config.yml에 추가할 것이다.
  - title: ":octocat: Github Blog"
    # url: "/github-blog"
    # category: "github-blog"
    children:
      - title: "- 블로그 만들기"
        url: "/github/blog" # _pages에 연결시키고 싶은 page의 permalink가 같아야한다!
        category: "github-blog" # 나중에 게시글의 개수를 세서 사이드 바 옆에 띄워 줄건데, 이 때 숫자 세기 위해 필요!
  - title: "💡 Algorithm"
    # url: "/algorithm"
    category: "algorithm"
    children:
      - title: "- 백준"
        url: "/algorithm/baekjoon"
        category: "algorithm-baekjoon"
      - title: "- 프로그래머스"
        url: "/algorithm/programmers"
        category: "algorithm-programmers"
  - title: "🗂️ Project"
    # url: "/algorithm"
    category: "project"
    children:
      - title: "- 오픈매트"
        url: "/project/openmat"
        category: "project-openmat"
```

- url과 \_pages에 연결시키고 싶은 page의 permalink는 같아야한다!
- category: 나중에 게시글의 개수를 세서 사이드 바 옆에 띄워 줄건데, 이 때 숫자 세기 위해 필요!
  - \_posts/post의 category와 같아야 셀 수 있다.

### 1.2 \_config.yml

> \_config.yml안에 최하단으로 내려가 보자.

```yml
# _config.yml
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
      toc_label: "목차"
      toc: true # 현재 페이지의 목차 보기 활성화
      toc_sticky: true
      sidebar:
        nav: "sidebar-category" # /_data/navigation.yml에 sidebar-category의 내용을 정의
```

- 이렇게 작성하고 로컬 환경에서 실행한다면, 사이드바에 카테고리들이 보일 것이다.
- 클릭한다면 흰바탕의 이상한 화면이 뜰 것이다.
  - \_pages 폴더에 해당 화면을 생성해 주어야 하기 때문에 정상적인 동작이다.

## 2. Page 구현

> 사이드바(sidebar)의 page를 구현해보자. <br> 상단바와 유사하지만 다른 점은 기본제공 layout인 archive.html을 사용함에도 코드를 좀 더 추가해야한다.

### 2.1 \_pages 폴더

> \_pages 폴더 안에는 구현할 page들을 넣어줄건데 그냥 카테고리들 넣어준다 생각하면된다.

### 2.2 카테고리에 따라 구현

> 어차피 하나만 구현하면 나머지는 다 똑같기에 <br> **"Github Blog"**의 **"블로그 만들기"**를 구현해보았다.

#### 2.2.1 **"Github Blog"**의 **"블로그 만들기"** 클릭 시 화면

```yml
# _pages/category-github-blog.md
---
title: "Github Blog"
layout: archive
permalink: /github/blog
author_profile: true
sidebar:
  nav: "sidebar-category"
---
# 아래 부분은 해당 카테고리의 포스트 목차를 띄우기 위한 코드이다.
{% raw %}
{% assign posts = site.categories.github-blog %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
{% endraw %}
```

- 이렇게 파일을 작성하고 실행 후 해당 카테고리를 클릭 해보면 아래와 같은 화면을 얻을 수 있다.

![](/images/github-blog/2023-03-14-github-blog-06-sidebar-img-01.png)

---

## 3. 사이드바(sidebar)에 게시글 숫자 넣기 구현

> 사이드바(sidebar)의 게시글 숫자와 총 게시글 숫자를 구현해보자.

## 3.1 \_includes/nav_list 수정하기

```yml
# _includes/nav_list

{% raw %}
{% assign navigation = site.data.navigation[include.nav] %}
{% assign sum = site.posts | size %}

<nav class="nav__list">
  {% if page.sidebar.title %}<h3 class="nav__title" style="padding-left: 0;">{{ page.sidebar.title }}</h3>{% endif %}
  <input id="ac-toc" name="accordion-toc" type="checkbox" />
  <label for="ac-toc">{{ site.data.ui-text[site.locale].menu_label | default: "Toggle Menu" }}</label>
  <li class="nav__sub-title"> Total Posts : {{sum}}</li>
  <ul class="nav__items">
    {% for nav in navigation %}
      <li>
        {% if nav.url %}
          <a href="{{ nav.url | relative_url }}"><span class="nav__sub-title-sidebar">{{ nav.title }}</span></a>
        {% else %}
          <span class="nav__sub-title-sidebar">{{ nav.title }}</span>
        {% endif %}
        <!-- {% if nav.url %}
          <a href="{{ nav.url | relative_url }}"><span class="nav__sub-title">{{ nav.title }}</span></a>
        {% else %}
          <span class="nav__sub-title">{{ nav.title }}</span>
        {% endif %} -->

        {% if nav.children != null %}
        <ul>
          {% for child in nav.children %}
          {% assign post_cnt = 0 %}
          {% for category in site.categories %}
            {% if category[0] == child.category  %}
                {% assign post_cnt = category[1].size %}
            {% endif %}
          {% endfor %}
            <li><a href="{{ child.url | relative_url }}"{% if child.url == page.url %} class="active"{% endif %}>{{ child.title }}({{ post_cnt }})</a></li>
            <!-- <li><a href="{{ child.url | relative_url }}"{% if child.url == page.url %} class="active"{% endif %}>{{ child.title }}</a></li> -->
          {% endfor %}
        </ul>
        {% endif %}
      </li>
    {% endfor %}
  </ul>
</nav>

{% endraw %}
```

- 이렇게 파일을 작성하고 사이드바를 확인 해보면 아래와 같은 화면을 얻을 수 있다.

<center>
<img src="/images/github-blog/2023-03-14-github-blog-06-sidebar-img-02.png">
</center>
---

## CLOSING

> 다음 게시글에서는 상단바, 사이드바에 맞게 게시글 만들어보자.

## RECOMMEND NEXT POSTS

- [[Github Blog, 깃허브 블로그] - 07. 상단바(nav), 사이드바(sidebar)에 맞추어 게시글 작성하기][github-blog-07]

[github-blog-05]: https://feelincoding.github.io/github-blog/github-blog-05-nav/
[github-blog-07]: https://feelincoding.github.io/github-blog/github-blog-07-posts/

### REFERENCE
