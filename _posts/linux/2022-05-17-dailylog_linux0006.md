---
layout: single
title:  "Linux (06) - Linux Special Character Symbol"
categories:
    - Linux
tags:
    - [Linux, Command, Syntax, Symbol]

toc: true
toc_sticky: true

date: 2022-05-17
last_modified_at: 2020-05-18
---

# Linux Special Character Symbol Meaning In Command Line

## Directory Symbol Command
-   ~   =   Home Directory
    ```
    cd ~        Move to Home Directory
    ```

-   \-   =   Previous Directory
    ```
    cd -        Move to Previous Directory
    ```

-   .   =   Current Directory
    ```
    mv temp.txt ./cat.txt       Change "temp.txt" name to "cat.txt" from current folder
    ```

-   ..  =   Parent Directory (Previous/Above Folder)
    ```
    mv ../temp.txt ./temp.txt   Move "Temp.txt" from previous folder to current folder
    ```


## History Symbol Command
-   !   =   Launch command with ID   (Each Symbol has ID number)
    ```
    ! + (Symbol ID)
    ```

-   !!  =   Launch previous command
    ```
    !!
    ```

-   !-number    =   Recall the "number-th" command backward from the history(마지막 명령어로부터 뒤로 번호만큼째 명령어 재호출)
    ```
    history     command history will display
    1   su
    2   sudo passwd root
    3   su
    4   !
    5   su
    6   ls
    !-2         su will recalled
    ```

-   !^  =   1st argument from previous command
    ```
    ls -la company      Command example (3 arguments exist)
    ls !^               Same as ls -la
    ```

-   !$  =   Last argument from previous command
    ```
    ls -la company      Command example (3 arguments exist)
    ls !$               Same as ls company
    ```

-   !*  =   All from previous command
    ```
    ls -la company      Command example (3 arguments exist)
    ls !*               Same as ls -la company
    ```


## Multiple Command
-   |   =   Connect left and right side of command (Pass output of left command to right side command)
    ```
    cat /etc/passwd | grep bash | sort      Organize only bash files from passwd folder
    ```

-   ;   =   Connects 2 commands (Execute commands from left to right)
    ```
    data; cal; who      show date > show calender > show my info
    ```

-   &&  =   Execute from left to right but if left command fail, do not start right (AND)
    ```
    echo 1 && eecho 2 && echo 3       Due to syntax error on "eecho2", echo 3 will not execute
    ```

-   ||  =   Execute from left to right but if left succeed, right command will ignored (OR)
    ```
    echo 1 || echo 2 || echo 3      Only "echo 1" will execute
    ```


## Wild Card
-   \* =   Any characters
    ```
    ls test*        Any file starts with test (Ex)test1, test222, test312312)
    ```

-   [] =   Any range of character
    ```
    [a-z]       a ~ z 
    [A-Z]       A ~ Z
    [0-9]       0 ~ 9
    ```

-   ?   =   Any character, each "?" represent 1 character
    ```
    ls ?at      Cat,Bat,Mat
    ```

-   { } =   Specific Character, It must match with range
    ```
    mkdir test{1,2,3}       Create test1, test2, test3
    ```

-   \- =   Range
    ```
    [a-z]       a to z
    [a-e]       a to e
    ```

-   [! ] or [^ ]    =   Exclude
    ```
    ls -l [!a-c]*       Show any files without a,b,c
    ```


## Quoting
-   ' '  =   Display anything inside ' '. Include any special characters
    ```
    echo '\'        It will display \
    ```

-   " " =   Display anything inside " ". Exclude $(), '', $, \
    ```
    echo "\\"       It will display \
    ```

-   \  =    Use in front of special character (It ignore special character command)
    ```
    echo \\         It will display \
    ```

-   \` ` (Symbol beside 1)  =   Execute command inside and display output
    ```
    echo the working directory is `pwd`
    ```
    ```
    output
    echo the working directory is /home/etc/temp
    ```

## Braket
-   ( )     =      
    1.  Function Start to End
    2.  Sub shell create
    3.  Arrangement reset

-   (())    =   Use on mathematical  equation

-   { }     =   
    1.  Command block start to end
    2.  variable range
    3.  variable expend
    4.  repeat characters list

-   \[ ]      =
    1. Arrangement Index
    2. Test Condition

-   [[ ]]   =   Upgrade version of [ ] (Bash)
  
-   :   =   Start of argument

-   ;   =   End of argument

-   ,   =   separates functions, arguments


## Input & Output Redirection
-   <   =   Input re-insert
    ```
    cat < aaa.txt       same as "cat aaa.txt"
    ```

-   \>   =   Output re-insert
    ```
    cat < file > file_copied        Redirect input, "cat" data in "file" and redirect output and save it on "file_copied"
    ```

-   \>> =   Output re-insert (Edit, Do not delete previous data)
    ```
    who >> output.txt       Add who data on output.txt
    ```

---
###### ( Source: https://inpa.tistory.com/category )