
# Formatting File

When using DRU, it looks in the current directory for a file
`.dru`. If this file is found, then DRU will read this as
its formatting file, using it to produce the desired output.
For example, if we are in a directory `myproject` and we
the create a file `myproject/.dru` such as:

**myproject/.dru**
```
Code (Haskell): -c -s -tl -d
    *.hs

Code (C): -c -s -tl -d
    *.c
    *.h

Images: -c -ts
    *.png
```

This file creates three categories of output: Code (Haskell),
Code (C), and Images. For the first category, we have spec-
ified that we want DRU to count (`-c`) the number of files, 
enumerate the size (`-s`) of each file, display the total num-
ber of lines (`-tl`), and to sort everything by directory (`-d`).
After this, we specified the type of file we want to catch
in this category, namely, haskell source files. For the Code
(C) category, the arguments are the same but the files to be
discovered are C source and header files. The final category
merely counts the number of files and totals the size (`-tl`),
specifically of the PNG image files. Now, upon the command

```
dru
```

DRU will search your current directory for the .dru file. 
Then, it will load in the information and produce a formatted
output, prescribed by the .dru file.


# Command Line Args

In the event that you do not want to use a formatting file,
you can always run DRU manually. If DRU is run with no arg-
uments, i.e.

```
dru
```

and there is no .dru file in your current directory, then it
will open up a prompt to get the information specified in a
.dru file from the user. Otherwise, we can give DRU a list
of command line arguments to achieve the same result.
