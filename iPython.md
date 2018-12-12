## General
Some general commands
```
%run -n <file_name>   # option -n: do not run the main portion of the program.
%paste
%cpaste 
print(_)     # print output of the current lin
print(__)    # print output of second-to-last
print(___)   # print the third-to-last output

_<line_number>  # retrieve value of output at line_number
%history?
%history -n 1-4 # get history from line 1 to 4

%rerun          # re-execute a portion of command history
%save           # save history command to a file
```
## Use Python command
In order to run Python command on IPython shell, use `!` before the command.
```
    In [1]: !pwd
    In [2]: !cd
``` 

Example of how to pass an output of shell command to variable on IPython
``` 
    In [5]: myfile = !ls 
    In [6]: print(myfile)
    ['project.txt'] 
``` 
   
## Debugging
 Use ```%xmode``` magic function for debugging
 ``` 
     In [1]: %mode?     
     In [2]: %mode [option]    # there are 3 options - Plain, Context and Verbose.
``` 