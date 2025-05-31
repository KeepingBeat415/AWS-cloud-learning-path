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
