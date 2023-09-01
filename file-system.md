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
