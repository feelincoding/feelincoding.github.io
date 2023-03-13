---
title: "Git Blog"
layout: archive
permalink: /git-blog
author_profile: true
sidebar:
    nav: "sidebar-category"
---

{% assign posts = site.categories.git-blog %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
