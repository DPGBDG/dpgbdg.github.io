---
title: "Test 페이지 차후 삭제"
layout: archive
permalink: categories/test
author_profile: true
sidebar_main: true
---
<!-- 공백이 포함되어 있는 카테고리 이름의 경우 site.categories.['a b c'] 이런식으로! -->

{% assign posts = site.categories.Test %}
{% for post in posts reversed %} 
    {% include archive-single_simple.html type=page.entries_layout %} 
{% endfor %}