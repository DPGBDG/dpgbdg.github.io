---
layout: single
title:  "Programming Language (01) - Markdown Commend"

categories:
    - Language
tags:
    - [Markdown, Language, Syntax, Blog]

toc: true
toc_sticky: true

date: 2022-03-26
last_modified_at: 2020-03-26
---

# Basic of Markdown

## Why Markdown?
- Markdown = Markdown is a lightweight markup language that you can use to add formatting elements to plaintext text documents (.md file)
- Markdown text editor 
    1. Stack Edit (Free/Online)
    2. Typora (Pay/Local)
    3. VS Code (Free/Local)
        - Install plugins (markdownlint & markdown all in one)
        - Preview Ctrl + Shift + v

## Markdown Syntax
- Markdown Basic Syntax  
  Detail on <https://ansohxxn.github.io/blog/markdown/>
    - Change Line
    ```
    <br>
    or
    space x 2 + enter
    ```

    - Bullet
    ```
    -
    ```

    - Commenting
    ```
    \
    ```
    
    - Header  
    ```
    #       h1      Largest
    ##      h2
    ###     h3
    ####    h4
    #####   h5
    ######  h6      Smallest
    ```

    - Bold
    ```
    **text**
    ```

    - Italic
    ```
    *text*
    ```

    - Strike out
    ```
    ~~text~~
    ```
    
    - Under Line
    ```
    <u>text<u>
    ```

    - Text Colour
    ```
    <span style="color:yellow">text</span>>
    ```

    - Code Block  
    \`\`\`  
    code  
    \`\`\`

    - Commenting "Liquid Language" without executing  
    \`\`\`  
    {퍼센트 raw 퍼센트}  
    Liquid Syntax  
    {퍼센트 endraw 퍼센트}  
    \`\`\`

    
    - Insert Image
    ```
    ![image](url)
    ```

    - Line
    ```
    ---
    ```