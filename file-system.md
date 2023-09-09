### Print current working directory
`echo $(pwd)`

### List all files and folders in current directory
`ls`

### List all files and folders in current directory, with information such as access rights and date last modified
`ls -l`
+ Option '-l' stands for long listing format

### List only files in current directory, ie do not list folders
`find . -maxdepth 1 -type f`
+ '.' refers to current directory

### Go to a directory / folder
`cd ./path/to/folder`

### Make a new directory / folder in current directory
`mkdir <new folder name>`
+ Note that if new folder already exists, an error will be thrown

### Make a new directory / folder only if it does not exist yet
`mkdir -p <new folder name>`

### Move or rename files
`mv /current/path/to/file /dest/path/of/file`
+ Can use either relative or absolute path
+ If dest path provided is a directory, file will be moved into that directory with current file name
+ If source and dest paths are in same directory, the file will be renamed

### Copy files
`cp /current/path/to/file /dest/path/of/file`
+ Unlike 'mv' command, 'cp' command will keep the old file

### Get content of file
`cat /path/to/file`

### Copy file content to clipboard
`cat /path/to/file | pbcopy`

### Copy command output to clipboard
`<run your command> | pbcopy`
+ E.g. sh script-file.sh | pbcopy

### Edit access rights of file
`chmod 777 /path/to/file`

### Given a file path, get file name only
`basename $FILE_NAME`
+ E.g. basename ./my-awesome-app/website/page1.html -> page1.html

### Given a file name, get file name without file extension
`${file_name%.*}`
+ Useful link: https://stackoverflow.com/questions/965053/extract-filename-and-extension-in-bash

### Given a file path, get file directory only
`dirname $FILE_NAME`
+ E.g. dirname ./my-awesome-app/website/page1.html -> ./my-awesome-app/website

### Find and list all files in current directory
`find . -type f`
+  Files will be listed as (full) relative path from current directory
+  Also list files in sub-directories

### Find and list all files, by file names only, in current directory
`find . -type f | xargs basename` \n

`find . -type f | sed 's:.*/::'`

`find . type f -execdir printf "%s\n" {} +`

### Find and list files starting with a string in file name, in current directory
`find . -name "start-string-to-match*"`

### Find and list files ending with a string in file name, in current directory
`find . -name "*end-string-to-match"`
+ E.g. find . -name "*.yaml" returns files with file extension: '.yaml'

### Find and list files containing a string in file name, in current directory
`find . -name "*some-string-to-match*"`

### Find and list files starting, containing and ending with diff string in file name, in current directory
`find . -name "start-string-to-match*some-string-to-match*end-string-to-match"`

