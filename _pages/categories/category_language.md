---
title: "Language"
layout: archive
permalink: categories/language
author_profile: true
sidebar_main: true
---


{% assign posts = site.categories.Language %}
{% for post in posts reversed %} 
    {% include archive-single_simple.html type=page.entries_layout %} 
{% endfor %}
