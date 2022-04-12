---
title: "Computer"
layout: archive
permalink: categories/computer
author_profile: true
sidebar_main: true
---


{% assign posts = site.categories.Computer %}
{% for post in posts reversed %} 
    {% include archive-single_simple.html type=page.entries_layout %} 
{% endfor %}
