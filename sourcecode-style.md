## Style and code requirements

Source code that has a common style is easier to read than code that uses
different styles in different places. It helps making the code feel like one
continuing code base. Easy-to-read is a very important property of code and
helps making it easier to review when new things are added and it helps
debugging code when develoers are trying to figure out why things go wrong. A
unified style is more important than individual contributors having their own
personal tastes satisfied.

Our C code has a few style rules. Most of them are verified and upheld by the
lib/checksrc.pl script. Invoked with `make checksrc` or even by default by the
build system when built after `./configure --enable-debug` has been used.

It is normally not a problem for anyone to follow the guidelines, as you just
need to copy the style already used in the source code and there are no
particularly unusual rules in our book.

We also work hard on writing code that are warning-free on all the major
platforms and in general on as many platforms as possible. Code that obviously
will cause warnings is not be accepted as-is.

Some the rules that you won't be allowed to break are

### Indentation

We use only spaces for indentation, never TABs. We use two spaces for each new
open brace.

### Comments

Since we write C89 code, // aren't allowed. They weren't introduced in the C
standard until C99. We use only /* and */ comments:

    /* this is a comment */

### Long lines

Soure code in curl may never be wider than 80 columns and there are two
reasons for maintaining this even in the modern era of very large and high
resolution screens:

1. Narrower columns are easier to read than very wide ones. There's a reason
   newspapers haved used columns for decades or centuries.

2. Narrower columns allow developers to easier show multiple pieces of code
   next to each other in different windows. I often have two or three source
   code windows next to each other on the same srceen - as well as multiple
   terminal and debugging windows.

### open brace on the same line

In if/while/do/for expressions, we write the open brace on the same line as
the keyword and we then set the closing brace on the same indentation level as
the initial keyword. Like this:

    if(age < 40) {
      /* clearly a youngster */
    }

### else on the following line

When adding an `else` clause to a conditional expression using braces, we add
it on a new line after the closing brace. Like this:

    if(age < 40) {
      /* clearly a youngster */
    }
    else {
      /* probably intelligent */
    }

### No space before parens

When writing expressions using if/while/do/for, there shall be no space
between the keyword and the open parenthesis. Like this:

    while(1) {
      /* loop forever */
    }