---
layout: single
title:  "Linux (02) - Basic Linux Commands"
categories:
    - Linux
tags:
    - [Linux, Command, Syntax]

toc: true
toc_sticky: true

date: 2022-03-29
last_modified_at: 2020-03-29
---

# Basic of Command Line 

## Files and Directories

- File - Document that stores information such as text, images, video.  
- Directory - File that stores the names of other files or directories in a hierarchical st.


## Command Line Basic Syntax
Format = Command Option File/Name  
(ex: mkdir -p temp)  

- Command line alphabet case rule - Command line is Case-Insensitive.
    ```
    echo "Lower case" > a.txt       file created
    echo "Upper case" > A.TXT       New file created, above file deleted
    echo "Mixed case" > A.txt       New file created, above file deleted
    ```

- mkdir - make folder
    ``` 
    mkdir MyFolder
    mkdir /tmp/tutorial     Creating folder with location 
                            (Error occurs if /tmp does not exist
    mkdir dir1 dir2 dir3    Create Multiple Folder
    mkdir -p dir4/dir5/dir6 Create folder inside folder
                            Dir4 > Dir5 > Dir6
                            mkdir -p = Create the parent directories
    ```
    ```
    Same Command / Different Method
    (Verbose = Provide additional detail about what command doing)
    mkdir --parents --verbose dir4/dir5
    mkdir -p --verbose dir4/dir5
    mkdir -p -v dir4/dir5
    mkdir -pv dir4/dir5
    ```
    ```
    Same Command / Different Method
    Insert "Space" as folder name
    mkdir "folder 1"
    mkdir 'folder 2'
    mkdir folder\ 3
    mkdir "folder 4" "folder 5"
    mkdir -p "folder 6"/"folder 7"
    ```

- whoami - Print User Name
    ```
    whoami
    ```

- pwd - Print Working Directory
    ```
    pwd
    ```

- cd - Change Directory ("/" = Directory seperator | root folder)
    ```
    cd          Go to root folder
    cd /        Go to home folder
    cd ../..    Go to previous folder x 2
    cd ~/       Starting from home directory
    cd ..       Go to previous folder  
                ( . = current folder,  .. = Parent of current folder)
    ```

- ls - List Files
    ```
    ls
    Creating file using ls
    ls > output.txt
    ```

- rm - Delete Files
    ```
    rm temp.txt     Delete file
    rm -r temp      Delete file & directories
    ```

- touch - Create file without any content
    ```
    touch README.txt
    ```

- echo - Outputs the strings that are passed to it as arguments
    ```
    echo "this is test"
    echo "This is a test" > test_1.txt
    echo "This is a second test" > test_2.txt
    echo "This is a third test" > test_3.txt
    ```

- cat - Create/Read single or multiple files (Concatenate)
    ```
    cat output.txt                          Read output.txt
    cat test_1.txt test_2.txt test_3.txt    Read all 3 files together
    ```
    ```
    Using Wildcard
    cat test_?.txt      ? = any character (? = 1 character)    
    cat test_*          * = any character, text, letter // Include all
    ```
    ```
    Combining context
    cat t* > combined.txt       Combine text in all files start with t  
                                and make "combined.txt"
                                all text in test_1.txt ~ test_3.txt will combine
    ```
    ```
    Editing (Adding text to the file)
    cat t* >> combined.txt
    echo "I've appended a line!" >> combined.txt    >> = Adding
    ```
    ```
    Result
    $ cat combined.txt
    this is a test
    this is a second test
    this is a third test
    I'v appended a line!    
    ```

- less - View the contents of a text file one screen at a time
    ```
    less combined.txt
    ```

- mv - Move one or more files or directories from one place to another ina file system
    ```
    mv README.txt Documents/
    ```