---
layout: single
title:  "Debugging - Split-Half Search"

categories:
    - General
tags:
    - [General, Basic, Tips]

toc: true
toc_sticky: true

date: 2022-05-16
last_modified_at: 2020-05-16
---
# Split-Half Search Method
- A split-half search is a technique for systemtically isolating the source of an issue.
(https://www.peachpit.com/articles/article.aspx?p=420908&seqNum=3)

- Remove half of issue and try > If no issue? > Check other half

- Issue debugging order
    1. Check "User Error"
    2. Check "Software Related Issue"
    3. Check "Software Virus"
    4. Check "Hardware"
        - Inspect the components first
        - Always check larger components to smaller components
        - Always check one components at a time
