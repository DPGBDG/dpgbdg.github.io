---
title: "Basic System Usage Tips"
layout: archive
permalink: categories/general
author_profile: true
sidebar_main: true
---


{% assign posts = site.categories.General %}
{% for post in posts reversed %} 
    {% include archive-single_simple.html type=page.entries_layout %} 
{% endfor %}
