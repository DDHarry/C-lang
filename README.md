# The *C* Programming Style Guide for mweet.me 
The C language from ANSI-C to the C11 edition


## Conventions

• Unix shell
```c
$> pwd      /* in the Unix shell */
	>> jane_doe/workspace
```

• The ```main``` function

The standard define two environments
  1. the *freestanding environment*, when, for example, you build an OS-kernel;
  2. a *hosted environment* where libs and startup go through a ```main``` function defined as
 ```c
 
 int main(void){
 	...
}
 
 ```
 
 or
 
  
  ```c
  
  int main(int, char*[]){
		...
	}
  
  ```
  
  
  
  
## Sources

From gcc.gnu.org, the [GCC manual](https://gcc.gnu.org/onlinedocs/)




<a name="table-of-content"></a>
## Table of content

1. [A compiler short reminder](#compiler-short-reminder)

3. [Main, Comment, Indentation](#main-comment-indentation)

t



<a name="1"></a><a name="compiler-short-reminder"></a>
## [1](#compiler-short-reminder) A compiler short reminder



We get the *GCC* compiler, even it can be linked to the CLang compiler, as for example on MacOS. We go from the *ANSI-C* original edition to the latest and fourth version *C11*

### 1.1 Options controlling the kind of input

#### • The four compilation stages

Compilation is up to four stages always in that order

1. preprocessing;

2. compilation proper;

3. assembly;

4. linking.

__How GCC works?__

Steps	1+2  ::  Process and compile several input files	>>	one assembler or several assembler input files;
														      
Step	3    ::  Each assembler input file			>>	object file

Step	4    ::  Linking combines				>>	all the object files into an executable file.


#### • Filenames

Filename suffixes
```c
	file.c	:	C source code, must be preprocessed
	file.i	:	C-source code that should not be preprocessed
	file.s	:	Assembler code
	file.S
	file.sx	:	Assembler code that must be preprocessed
	other	:	An object file to be fed straight into licking.
			    Any non recognized file's suffix file is treated in this manner.
```



### 1.2 Options controlling the C dialect
```c
	$: gcc -ansi greetings.c
```
Choice of the different versions
```c
	-ansi               ::  compile respect to the ANSI-C standard ratified in 1989. Gets three different writings forms
	-std=c90            >   also C89,
	-std=iso-9899:1990  >   published in 1990 (std=90). Ratified as an ISO standard (ISO/IEC 9899:1990)
	-std=c11            ::  ISO/IEC 9899:2011, the fourth version, under two different forms
	-std=iso-9899:2011  >   second form
```

Choice of an extension - GCC provides some extensions to the C language
```c
-std=gnu11          ::  The default choice. On rare occasions, they conflict with the C standard.
                        G11 = C11 with GNU extensions, also GNU dialect of C11
```

More, see [Chapter 6 Extensions to the C language family (p 383)](https://gcc.gnu.org/onlinedocs/gcc-6.3.0/gcc/index.html#toc_C-Extensions)

```c
  -fhosted          ::  targets a hosting environment which is almost everything except a kernel
  -ffreestandings   ::  targets a freestanding environment for which the most obvious example is an OS kernel
```

More, see [3.4 Options controlling C dialect](https://gcc.gnu.org/onlinedocs/gcc-6.3.0/gcc/C-Dialect-Options.html#C-Dialect-Options)



### 1.3 Overall options
```c
  -c           ::  compile or assemble the source files but do not link them
                   The object filename is ```-.c, -.i, -.s etc ...``` into an ```-.o ``` filename
  -S           ::  stop after the compilation. The output is in the form of an assembler code file.
                   Means -.c, -.i, ... files > -.s
  -E           ::  stop after the preprocessing stage, hence the output is a preprocessed file > std output
  -o file      ::  place output in the file 'file'. If not specified, the default is to put an 
                   executable in 'a.out',
                   the object file for 'source.suffix', namely 'source.c', in 'source.o'
                   its assembler file in 'source.s'
                   precompiled header in 'source.suffix.gch', namely, 'source.c.gch'
                   all preprocessed C sources on standard output
  -v           ::  print on standard error output the commands executed to run the stages of compilation and also
                   the version number of the compiler driver program and of the preprocessor and the compiler proper.
  -###         ::  like '-v' exept .) the commands are not executed ..) arguments are quoted unless
                   they contain only alphanumeric characters or '.', '-', '/', '_'
                   Useful for the shell script to capture the driver-generated command lines
  --version    ::  display the GCC version number and copyright
  @cmdFile     ::  read command-line options from 'cmdFile', the options are read in place of the originals
                   if 'cmdFile' does not exist or cannot be read, the options receive a litteral treatment
```

**_Notes_**

1. With these options, respect to the case, unrecognized input or assembly files (-c), not requiring compilation (-c, -S) or preprocessing (-E) files are ignored.

2. The 'cmdFiles'

    • may recursively contain other @cmdFile1 ...
   
    • Options in 'cmFile' are separated with white space, -opt1 opt2
   
    • for whitespace option like -opt3 opt3_addOn, we get ' or ".Example "-opt3 opt3_addOn" 
   
    • \ for any character, including the backslash one, example \\
   



### 1.X Debug - Diagnostics

```c
	-pedantic         ::  to obtain all the diagnostics required by the standard
	-pedantic-errors  ::  if you want them to be erros rather than warnings
```





**[ &#8679; to the top](#table-of-content)**


<a name="2"></a><a name="main-comment-indentation"></a>
## [2](#main-comment-indentation) Main - Comment - Indentation

```c
/*
 * We choose this classical comment signs vs // which is more C++
 *
 */

#include <stdio.h>

int main(void){
  printf("I am Happy");   /* Inside code comment */
  return 0;
}
```

## We choose:

   1. to include the ``` { ``` on the same line as the function declaration;
   
   2. the *C11* satndard to define our ```main``` function, idem est, with ```int, void``` and ```return```
    
   
    
    
**[ &#8679; to the top](#table-of-content)**



&copy; mweet.me - Visit our website <a href="https://mweet.me" target="_blank">&raquo;&raquo;</a>
