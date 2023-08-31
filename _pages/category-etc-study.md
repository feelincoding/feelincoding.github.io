---
title: "Study"
layout: archive
permalink: /etc/study
author_profile: true
sidebar:
  nav: "sidebar-category"
---

🏷️ **<u>개인적인 공부</u>** 를 진행하며 간단한 스케치를 공유 :D, 간단한 스케치가 끝나면 정리해서 올려보자!
{: .notice--info}

{% assign posts = site.categories.etc-study %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
