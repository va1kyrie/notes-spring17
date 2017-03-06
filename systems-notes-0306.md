# Notes 6 March

- Assignment 2 due in 3 Fridays - but one of them is Spring Break (next)

- byte code >> useful program -- object-dump
  - give byte code for command
  - clearly shows you which byte code letters correspond to which operands in assembly.
    - ex: different versions of `mov` depending on hardware.
    - useful b/c later, once shell code written, going to need byte code
- need to understand how programs do and don't work and why

- base pointer: points to bottom of stack right at beginning of function call
- lot of times stacks are word-aligned
  - can't start something on a stack that's not a multiple of a word
  - or quad-word-aligned
    - very specific tradeoff

- direction of stacks will change with printf
  - top of stack will be at top


- want to figure out where bad and buffer are
  - see bunch of stuff
    - find bad
    - see what it points to and change

- typical buffer overflow bug:
  - strcpy
    - does not check inputs (sanitize your input!)
    - how to take advantage of?
      - provide filename - attack code
        - attack code will go in stack
          - has to fit in space available (in-class ex: 127 bytes)
        - modify return pointer to access the stack
          - provide address to buffer[0] << how to know?? that is the question
        - function returns and executes attack
- most modern programs, C is a DLL and only that which is needed is loaded
- can't just have constants; have to insert them into program
- really big thing is going to provide this as input -- strcpy stops copying at a null
  - cannot have a null in your program
  
