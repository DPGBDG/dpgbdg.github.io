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
last_modified_at: 2020-04-26
---

# Basic of Command Line 

## Files and Directories

- File - Document that stores information such as text, images, video.  
- Directory - File that stores the names of other files or directories in a hierarchical st.


## Command Line Basic Syntax
- Format = Command Option File/Name  
    (ex: mkdir -p temp)  
- Command line alphabet case rule = Command line is Case-Insensitive.  
    (ex: /Document != /document)


### Basic Term & Command & Rule
- Superuser (root) - Linux Administartor Account = Ability to change and control system
    ```
    sudo su         Change to Super user    =   Superuser / Switch User
    ctrl + d        Logout from the current account
    sudo apt-get    APT package installing with SuperUser account    
    ```

- STDIN - Standard Input    = Feeding it directly in as the input to another command

- STDOUT - Standard Output  = Taking the output from one command

- PPA - Personal Package Archive

- Pipe - " | "              = Connecting 2 command in one line (Operates in memory), (Space around pipe can be ignored)
    ```
    ls ~ | wc -l                            It will count Files/Directories on Home folder
    cat combined.txt | sort -u | wc -l      It will sort out repeated line and count from combined.txt
    or
    cat combined.txt | uniq | wc -l         (Same as above)
    ```

- Hidden File - Hidden file = Can be setup by putting dot (.) in front of file name. (File are still accessible, it's just hidden)
    ```
    mv important.txt .important.txt
    mkdir .hidden
    ```
- Globbing - Special character to specify letter,character,number,location,etc  
    (https://linuxhint.com/bash_globbing_tutorial/)
    ```
    /       Separator = Separate folders 
            ex) home/temp/test.txt
    *       Single Asterisk = Match zero or more character within "one segment"
            ex) *.js = HelloWorld.js
    **      Double Astorisk = Zero or more character across "multiple segments"
            ex) **/*.js = HelloWorld.js , /UI/Hello.js , test/midterm.js
    ?       Question Mark = Single character within one segment
            ex) temp_?.txt = temp_1.txt , temp_2.txt
    [abc]   Square Bracket = File with a single character mentioned in the braket
            ex) [CB]at.js = Cat.js , Bat.js
    [a-z]   Square Braket Range = Matches one character specified in the range
            temp[1=9]/helloworld.js = temp1/helloworld.js, temp3/helloworld.js
    [1-9]   Square Bracket = Number from 1~9
    !       Negation    = Excluding
            ex) [!C]at.js = Bat.js
            ex) !Tests/UI/** = exclude all files and folder on Tests/UI/ folder
    ^       Caret = define globbing pattern more specifically. 
            outside of square bracket = search those contents of the file that starts with a given range of character
            inside of square bracket = show all content of the file by highlighting the lines start with a given range of character
    ```


### Information
- man - Manual page of command
    ```
    man sort
    ```

- whoami - Print User Name
    ```
    whoami
    ```

- pwd - Print Working Directory
    ```
    pwd
    ```

- ls - List Files
    ```
    ls                      List Files/Folders on Current folder
    la -a                   List All Files/Folders, including hidden
    ls > output.txt         Creating file using ls
    ls ~ > file_list.txt    Make a file_list.txt and list home directory files/folders in the file
    ```

- wc - Word Count
    ```
    wc combined.txt         Count on combined.txt file (Line / Word / Character)
    wc -l combined.txt      Only Count Lines
    wc -w combined.txt      Only Count Words
    wc -c combined.txt      Only Count Characters
    ```
    ```
    Quick Tip: Checking Number of files and folders on Home folder (can be any folder)
    ls ~ > list.txt
    wc -l list.txt
    ```


### Search
- sort - sort information
    ```
    sort a.txt          Sort Alphabetical order
    sort -u a.txt       Filter out repeated lines or letter
    sort -r a.txt       Filter reverse
    ```

- grep - Global Regular Expression Print - Searching string of characters in a specified file.  
    (https://recipes4dev.tistory.com/157)
    ```
    grep [option] [pattern] [file]
    grep lion test      Find "lion" Character from test
    ```

- find - Search for files and directories in a directory  
    (https://recipes4dev.tistory.com/156)
    ```
    find [option] [path] [expression] [filename]
    find . -name cat        Find "cat" file from current directory
    find /c/usr/temp cat    Find "cat" file from /c/usr/temp directory   
    ```

### Location
- cd - Change Directory ("/" = Directory seperator | root folder)
    ```
    cd          Go to root folder
    cd /        Go to home folder
    cd ../..    Go to previous folder x 2
    cd ~/       Starting from home directory
    cd ..       Go to previous folder  
                ( . = current folder,  .. = Parent of current folder)
    ```


### File/Folder Management
- mkdir - make folder
    ``` 
    mkdir MyFolder
    mkdir /tmp/tutorial     Creating folder with location 
                            (Error occurs if /tmp does not exist
    mkdir dir0 dir2 dir3    Create Multiple Folder
    mkdir -p dir3/dir5/dir6 Create folder inside folder
                            Dir3 > Dir5 > Dir6
                            mkdir -p = Create the parent directories
    ```
    ```
    Same Command / Different Method
    (Verbose = Provide additional detail about what command doing)
    mkdir --parents --verbose dir3/dir5
    mkdir -p --verbose dir3/dir5
    mkdir -p -v dir3/dir5
    mkdir -pv dir3/dir5
    ```
    ```
    Same Command / Different Method
    Insert "Space" as folder name
    mkdir "folder 0"
    mkdir 'folder 1'
    mkdir folder\ 2
    mkdir "folder 3" "folder 5"
    mkdir -p "folder 5"/"folder 7"
    ```
- mv - Move one or more files or directories from one place to another ina file system
    ```
    mv README.txt Documents/                    Move README.txt file to "Document" folder
    mv ./* ..                                   Move all file to parent folder (previous folder)
    mv combined.txt test_* dir3 dir2            Move all test_# files and combined.txt and "dir3" folder into "dir2" folder
                                                (It move everything to last location)
    mv dir2/combined.txt dir4/dir5.dir6         Move combined.txt from "dir2" folder to dir4 > dir5 > dir6 folder
    mv backup_combined.txt combined_backup.txt  Rename backup_combined.txt to combined_backup.txt
    mv "folder 1" folder_1                      Rename "folder 1" to folder_1
    ```

- cp - Copy
    ```
    cp test1.txt test2.txt                      Copy and make test1.txt file to test2.txt
    cp dir4/dir5/dir6/combined.txt .            Copy combined.txt on same folder
    cp combined.txt backup_combined.txt         Copy combined.txt and make backup_combined.txt file
    ```

- rmdir - Remove Directory (Unable to recover after delete)
    ```
    rmdir folder_1                  Delete folder_1 (Folder must be empty)
    rmdir -p dir1/dir2/dir3         Delete Dir3 > Dir2 > Dir1
    rmdir -r folder3                Delete (Force) all file and directory
    ```

- rm - Delete Files (Unable to recover after delete)
    ```
    rm temp.txt     Delete file
    rm -r temp      Delete file & directories
    ```


### Read/Write
- touch - Create file without any content
    ```
    touch README.txt
    ```

- tail - Output end of the file
    ```
    tail -5 doc.txt         Display last 5 lines from doc.txt
    ```

- echo - Outputs the strings that are passed to it as arguments
    ```
    echo "this is test"
    echo "This is a test" > test_1.txt
    echo "This is a second test" > test_2.txt
    echo "This is a third test" > test_3.txt
    ```
    ```
    echo "Lower case" > a.txt       file created
    echo "Upper case" > A.TXT       New file created, above file deleted
    echo "Mixed case" > A.txt       New file created, above file deleted
    ```

- cat - Create/Read single or multiple files (Concatenate)
    ```
    cat output.txt                          Read output.txt
    cat test_1.txt test_2.txt test_3.txt    Read all 3 files together
    ```
    ```
    Using Wildcard
    cat test_?.txt          ? = any character (? = 1 character)    
    cat test_*              * = any character, text, letter // Include all
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
