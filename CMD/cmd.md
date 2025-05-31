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
10. - -- (wildcards) take the place of characters or words,
11. Dir /a -- displays every file, including those that are hidden
12. Doskey /History -- displays previous commands
13. Ctrl+C -- stops the execution of a command
14. Tab Key -- automatically completes a command

### Re-directors & Applications

1. re-director
   - create empyt file
     `echo. > File.txt`
   - content into new file
     `echo Hello World > File.txt`
   - append content into exist file
     `echo Goodbye World >> File.txt`
2. type -- displays the contents of a text file

3. Combining Commands - use a redirector, to redirect from one command to another
   && only runs the second command if the first runs successfully
   & runs the second command regardless if the first command returns an error or not
   || only runs the second command if the first one fails
   | redirects the output of the first command to the second

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

1. Pause - pauses the execution of a script
2. @Echo Off - hides the directory from which a command is executed
3. Set - creates or modifies variables,
   ```bat
           Set var = 1
           Echo %var%
   ```
4. if statement
   ```bat
       if %var% == 1
           (echo var equals 1)
       else if
           %var% == 2 (echo var equals 2)
       else
           (echo var not 1 or 2)
   ```
5. functions && GoTo

   ```bat
        if %var% == 1 (Goto function1) else (Goto function2)

        :function1
        echo var equals 1
        Goto End

        :function2
        echo Not 1

        :end
        echo done!
   ```

6. Loops
   syntax: `FOR %%var IN (*) DO (something %%var)`
   ```bat
        @Echo off
        Cd C:\Users\Desktop
        FOR %%A IN (*) DO (Echo %%A)
   ```
7. move file into folder
   Parameter Extensions

   1. File Name: %%~n
   2. File Extension: %%~x
   3. File Attributes: %%~a
   4. File Size: %%~z
   5. Last-Modified Date: %%~t
   6. Drive and Path: %%~dp
   7. Drive: %%~d

   ```bat
       cd C:\User\Desktop
       mkdir "All Files"
       FOR %%A IN (*) DO (move "%%A" "All Files")

       FOR /r %%A IN (*) DO (if "%%~nA"=="My Awesome File" (del "%%A") else (echo No Match))
   ```

### File Management

1. Tree - displays the structure of a directory
2. Find - searches for a specified string within multiple documents
   1. /v - displays every string except the specified one
   2. /n - displays at which line every string is located at
   3. /c - displays the count of lines that contains the specified

```bat
    Find "Awesome" Text_Documents.txt
    Find /i "Awesome" Text_Documents.txt :: ignore the case of the characters
```

3. Findstr - supports the use of regular expressions
4. FC - finds any differences between files

```bat
    FC File1.txt File2.txt
```

5. Cipher - encrypts/decrypts files and directories
   1. \e - encrypts
   2. \d - decrypts

```bat
    cipher \e file.txt
    cipher \d file.txt
```

6. file attributes - file attributes define the way a user or the system can interact with a file or folder

   1. read-only (R): allows a file only to be read and not modified
   2. archive (A): enables windows backups
   3. system (S): denotes the files as one that's part of the operating system
   4. hidden (H): hides the file in windows explorer

   a. attrib - displays or modifies the attributes of a file/folder
   b. /s, /d - modifies files/folders the attributes in the current folder/sub-folder

```bat
    Attrib +R file.txt :: add attribute
    Attrib -R file.txt :: remove attribute
```

7. file association
   1. extension associations - windows associates every extension with a certain file type so that it knows the type of data contained within that file, and thus how to execute or open it
   2. one file type can be associated with many extensions, on the other hand, an extension can only be associated with one file type
   3. assoc - displays or modifies extension associations
   ```bat
    :: modified files association, then system will trade .txt file as .docx file
       Assoc .docx
       .docx = Word.Document.12
       Assoc .txt=Word.Document.12
   ```

### System Administration & Management

1. manage tasks
   1. tasklist - displays every running process in the computer
      1. -v - more info about task
      2. -svc - related services
   2. taskkill - terminates a running process
      1. ```bat
              taskill -im Chrome.exe
              taskill -f -pid 1234
         ```
2. scheduler tasks
   1. schtasks - schedules and automatically executes tasks
      1.
      ```bat
         SchTasks /Create /SC <DAILY/WEEKLY/MONTHLY> /TN "Task Name" /TR "<Executable Location>" /ST <Time (24 Hour Format)>
      ```
      2. `/Create /Change /Delete`
3. System configuration & Maintenance
   1. shut down system
      1. shutdown - schedules shutdowns or restarts
         1. ```bat
               ::shutdown computer in 2 hours
               shutdown -s -t 7200
            ```
   2. Power Config
      1. PowerCfg - modifies computers power configuration
         1. ```bat
            ::list power plan
            powercfg /l
            ```

### Networking Tools

1. ping - send packets, and awaits a response
2. tracerts - traces each hop a packet takes to reach your destination
3. pathping - combination ping and trace
4. netstat - displays various network statistics and information
5. ipconfig - displays information about IP configuration
6. ipconfig /flusdns - flushed the DBS resolver cache
