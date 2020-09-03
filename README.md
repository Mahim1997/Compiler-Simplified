# Compiler-Simplified
Compiler for a subset of C language

> Input: A program in C language (a subset)

> Output: Corresponding assembly code (with certain optimizations)

## Highlights

- Performed lexical analysis using Flex.

- Performed syntactic analysis using Bison.

- Implemented certain optimizations while generating assembly code eg. NOP removal, efficient usage of temp. variables, faster multiplication/division using shift operations.


## Execution Commands

#### For script execution
```bash
  ## Input file:  1505022_Input.txt 
  ## Output file: 1505022.asm
  ./command.sh
```

#### For step-by-step execution
```bash
  bison -d -y 1505022.y  # To run Bison
  echo '===>>> 1st step bison -d -y 1505022_Bison.y done\n'

  g++ -fpermissive -w -c -o y.o y.tab.c
  echo '===>>> 2nd step g++ -fpermissive -w -c -o y.o y.tab.c done \n'

  flex 1505022.l  # To run flex
  echo '====>> 3rd step flex 1505022_Flex.l done \n'

  g++ -fpermissive -w -c -o l.o lex.yy.c
  echo '====>> 4th step g++ -fpermissive -w -c -o l.o lex.yy.c done\n'

  g++ -o a.out y.o l.o -lfl -ly
  echo '====>> 5th step g++ -o a.out y.o l.o -lfl -ly done\n\n\n'

  ./a.out 1505022_Input.txt  # Run the program

  g++ -o outOpt.out IntermediateCodeStuffs/OptimizerRunner.cpp  # Run optimizations
  ./outOpt.out

```
