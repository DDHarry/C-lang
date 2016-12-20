# C-lang
The C language from ANSI-C to the C11 edition

# The *C* Programming Style Guide for mweet.me 


## Conventions


## Sources

From gcc.gnu.org, the [GCC manual](https://gcc.gnu.org/onlinedocs/)


<a name="table-of-content"></a>
## Table of content

1. [A compiler short reminder](#compiler-short-reminder)

3. [Main, Comment, Indentation](#main-comment-indentation)

t



<a name="1"></a><a name="compiler-short-reminder"></a>
## [1](#compiler-short-reminder) The Compiler : A short reminder



We get the *GCC* compiler, even it can be linked to the CLang compiler, as for example on MacOS. We go from the *ANSI-C* original edition to the latest and fourth version *C11*

```c
gcc greetings.c
    -ansi ::  compile respect to the ANSI-C standard ratified in 1989 (also C89
    -std=c90
    -std=iso-9899:1990
    -pedantic           ::  to obtain all the diafnostics required by the standard,
    -pedantic-errors    ::  if you want them to be erros rather than warnings
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

**[ &#8679; to the top](#table-of-content)**



&copy; mweet.me - Visit our website <a href="http://mweet.me" target="_blank">&raquo;</a>
