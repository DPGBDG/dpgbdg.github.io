---
title: "Blog"
layout: archive
permalink: categories/blog
author_profile: true
sidebar_main: true
---


{% assign posts = site.categories.Blog %}
{% for post in posts reversed %} 
    {% include archive-single_simple.html type=page.entries_layout %} 
{% endfor %}
