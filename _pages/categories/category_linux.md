---
title: "Linux"
layout: archive
permalink: categories/linux
author_profile: true
sidebar_main: true
---


{% assign posts = site.categories.Linux %}
{% for post in posts reversed %} 
    {% include archive-single_simple.html type=page.entries_layout %} 
{% endfor %}
