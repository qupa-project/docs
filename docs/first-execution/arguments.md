# UVC Arguments

Arguments are any statements after a given command.
For UVC (Uniview Compiler) the first argument must always be the entry file.
UVC only ever takes on file, any extra files must be included within the code itself.

By default UVC will compile your code to binary, then immediately execute it -
however there are command lines to change this behaviour.
Please note that any argument which includes a space, must be surrounded by ``"``.
(i.e. ``-o "./hello world.exe"``)

| Argument | Use |
|:-|:-|
| ``-o {filename}`` | The destination file name for the LLVM IR and binary output |
| ``-s`` | "The compilation level to perform ``llvm``, ``assembly``" |
| ``--execute`` | Executes the binary output after successful compilation |
| ``--version`` | Prints the version of the compiler |
| ``--verifyOnly`` | "Compiles to LLVM, but does not store the results or compiles further" |
| ``--opt {num}`` | Runs optimisation passes over the output (any number between 0-3 inclusive) |