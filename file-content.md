### Check if file contains a string
`cat /path/to/file | grep <string-to-check>`
+ E.g. cat ./my-awesome-app/website/page1.html | grep "html"
+ grep returns the \<string-to-check\> if found, else returns an empty string

### Get line number of a string or text section in a file
`cat /path/to/file | awk '/<string-to-find>/{ print NR; exit }'`
+ Returns line number if \<string-to-find\> is found, else returns an empty string
+ Line number starts counting from 1

### Get last line number, aka EOF line number
`LAST_LINE_NUM=$(wc -l < /path/to/file)`
+ Line number starts counting from 0, so actual LAST_LINE_NUM=$(( LAST_LINE_NUM+1 ))

### Replace text in a file
`sed -i '' "s/<text-you-want-to-replace>/<new-text>/" /path/to/file`
+ -i '' -> replace text and output new file content to overwrite current file
+ s -> substitute command
+ By default, sed replaces only first occurence of \<text-you-want-to-replace\>, to replace all occurrences, add the global flag, aka "g": `sed -i '' "s/<text-you-want-to-replace>/<new-text>/g"`

### Add text after a particular string in a file
`sed -i '' "s/<text-you-want-to-append-to>/& <new-text>/" /path/to/file`
+ Similar to previous command
+ Using symbol "&", sed will add \<new-text\> after \<text-you-want-to-append-to\>

### Add text to end of line of text containing a particular string in a file
```
# Scenario: You want to append semi-colon to end of every line in your codebase that contains <match-string>
NEW_TEXT=";"
sed -i '' "/<match-string>/ s/$/$NEW_TEXT/" /path/to/file
```
+ Similar to previous command
+ Symbol "$" refers to end of line
+ sed will first find string(s) containing \<match-string\>, then append $NEW_TEXT to end of respective lines

### Delete text, between 2 lines, from a file
`sed -i '' "<start-line-number>,<end-line-number>d" /path/to/file`
+ -i '' -> delete text and output new file content to overwrite current file
+ d -> delete command
