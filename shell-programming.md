### Create a new variable and reference it
```
MY_VAR=hello
echo $MY_VAR # prints out 'hello'
```
+ When declaring / initiating a new variable, there is no "$" symbol and ensure that you don't have spaces before and after the assignment symbol "="
+ When referencing a variable, use "$" followed by variable name
+ I prefer to use uppercase for variable names, but this is not required by shell

### Conditional statements, aka _if this then that_ 
```
# General syntax 1
if [[ condition  ]]; then
  ... expression ...
fi

# General syntax 2
if [ condition ]; then
  ... expression ...
fi
```
+ For both syntax, ensure that <condition> is separated by space with enclosing square brackets
    - `[condition]` or `[condition ]` or `[ condition]` are all invalid
+ Double square brackets is a newer syntax than single square brackets, with some differences:
    1. For single square brackets, you need to add a backslash "\" to escape special characters, such as "<", "-eq"
        - [[ 5 < 7 ]] is same as [ 5 \< 7 ]
