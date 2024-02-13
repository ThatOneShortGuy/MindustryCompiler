# MindustryCompiler
Compiler for Mindustry logic. Implements a modified version of the KXI language. The reason the code isn't available is because it is based off the capstone project.
Making the code public would be a violation of the academic integrity policy and would likely result in my degree being revoked.
Once there is sufficient changes to the grammar and the code is no longer recognizable as the original, I will make the code public.
As of now, there is not an executable for Linux, but I will be working on that soon.

# Usage
Download the compiler from the [releases page](https://github.com/ThatOneShortGuy/MindustryCompiler/releases)
Download the assembler from the [assembler repository](https://github.com/ThatOneShortGuy/MindustryAssembler)

## Options
Command syntax is as follows:
```Shell
compiler [options] <input_file>
```
- `-l` : lex the input and print the token stream
- `-p` : check if the program is syntactically valid and print any syntax errors that arise
- `-a` (only valid with `-p`, `-s`, `-c`, or `-e`) : create a graphical representation of the abstract syntax tree
- `-s` : check the program for semantic correctness and display any errors that arise
- `-c` : compile the program to assembly
- `-e` : assemble the compiled program and copy it to the clipboard (not yet implemented)
- `-o <filename>`: specify the output filename for assembly code (only relevant for `-c` and `-e`)

# Language
Mindustry KXI (MKXI) has the feel of if Java and C++ had a baby. The best way to learn the language is through the [examples](#examples) below.

When the program ends, the `stop` command is called on the processor so it stops completely.

## Types
type : void
     | num
     | char
     | bool
     | string
     | ID ([a-zA-Z_][a-zA-Z0-9_]*)

Note that `string` and `char` probably don't work currently.

## Examples
### Fibonacci
```Java
class A {
    public num fib(num n) {
        if (n < 2)
            return n;
        return fib(n - 1) + fib(n - 2);
    }
}
void main() {
    A a;
    cout << a.fib(4);
}
```
Functions have to be defined inside of classes. The `main` function is the entry point of the program. The `cout` with the `<<` operator is used to print to `message1`
There is no `cin` because there is no way to get input from the user.
