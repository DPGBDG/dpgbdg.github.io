---
layout: single
title:  "Basic System Usage Tips (03) - VIM Commands"

categories:
    - General
tags:
    - [General, Basic, Tips, VIM]

toc: true
toc_sticky: true

date: 2022-04-18
last_modified_at: 2020-04-18
---
# VIM Editor Basic Commands

### Move Cursor (Command Mode (Esc))
- Move (1 Character)
    ```
    h = Left
    j = Down
    k = Up
    l = Right
    ```
- Move (1 Page)
    ```
    H = Start of Page
    L = End of Page
    ```
- Move (1 Word)
    ```
    w = Move (Forward) Forward
    e = Move (End) End of word
    b = Move (Backward) Backward
    ```

### Insert (Command Mode (Esc))
- Text Writing  
    ```
    a = Inserting end of cursor
    A = Inserting end of sentence
    i = Insert where cursor is
    I = Insert start of sentence
    o = Insert start of next sentence
    O = Insert before next sentence
    s = Delete 1 character and insert where cursor is
    cc = Delete 1 sentence and insert
    ```

### Copy & Cut & Paste (Command Mode (Esc))
- Copy
    ```
    yy = Copy (yank) current line
    3yy = Copy (yank) 3 lines (Number can be changed) and press "Enter"
    y$ = Copy (yank) cursor to end of line
    y^ = Copy (yank) cursor to start of line
    yw = Copy (yank) cursor to next word
    yiw = Copy (yank) current word
    y% = Copy (yank) to matching character (example: Start from "{" to end of "}" )
    ```

- Cut
    ```
    dd = Cut (Delete) current line
    3dd = Cut (Delete) 3 lines (Number can be changed) and press "Enter"
    d% = Cut (Delete) cursor to end of line
    ```

- Paste
    ```
    p = Paste
    ```

### Save & Quit (Command Mode (Esc))
- Save
    ```
    :w = Save (Write)
    :w temp.txt = Save (Write) as "temp.txt" 
    :wq = Save (Write) and Quit
    ZZ = Save and Quit
    ```

- Quit
    ```
    :q = Quit
    :q! = Force Quit (Quit without save)
    :wq! = Force Save and Quit
    ```

### Search (Command Mode (Esc))
- Search word from the page
    ```
    ? = Search word from the top
    / = Search word from the bottom
    :7 = Go to 7th Line
    ```

### Block Select (Command Mode (Esc))
- Selecting Block
    ```
    v + move = Block Selecting
    Ctrl + v = Column Block
    Shift + v = Line Block
    ```

### Undo & Redo (Command Mode (Esc))
- Undo & Redo
    ```
    u = Undo
    Ctrl + r = Redo
    ```
