### Baisc

1. dir -- displays every file in a directory
2. help -- view every available parameter
3. cd -- stands for Change Directory
4. Mkdir -- create directories/folders, ex: mkdir "My Cats"
5. rmdir -- delete directories/folders, ex: rmdir /S "Folder"
    delete with path: mkdir 'path\Folder'
6. move -- move file into folder, ex: move Cat.txt Cats
7. copy -- copies or duplicates files and folders, ex: copy Cat.txt Cats
8. ren -- renames files and folders
9. del -- delete files, ex: del Cat1.txt
10. * -- (wildcards) take the place of characters or words,

### Redirectors & Applications

1. redirector 
    - create empyt file
        `echo. > File.txt`
    - content into new file
        `echo Hello World > File.txt`
    - append content into exist file
        `echo Goodbye World >> File.txt`
2. type -- displays the contents of a text file

3. Combining Commands - use a redirector, to redirect from one command to another
    && only runs the second command if the first runs successfully
    &  runs the second command regardless if the first command returns an error or not
    || only runs the second command if the first one fails
    |  redirects the output of the first command to the second

4. lunch application
    1. internal commands - launch programs that are built into the command line
    2. direct invocation - launch programs in the current directory
    3. the start command - start "" "application\path\app.exe"

5. environment variables
    - environment variables are a set of variables whose value is set through the operating system
    - path: the path environment variable contains a list of applications and executable locations  
        - set: lists a program into the path environment variable  
        ```bat
            Set Chrome="C:\Program Files (x86)\Google\Chrome\Application\chrome.exe"
            start Chrome
            ::will execute the application
        ```

### Batch Scripting
