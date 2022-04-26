# Hello World

First of all we are just going to create a file called ``hello.uv`` with the following code.

```uniview
import "print.uv";

fn main(): int {
	println("Hello World!");

	return 0;
}
```

Once we have that, simply run the command
```uniview
uvc hello.uv
```

Then you should see the output
```
Hello World!
```


## What just went on

Line 1, we imported ``print.uv``, as there is no such file defined in the local directly,
``uvc`` instead imported the file from the standard library.
That file then defined ``println`` amongst other functions for us to use.

Lines 3, is us defining the starting point for our program, ``fn`` denoting this is a function,
``main`` tells the compiler this is the entry point, the function itself takes no inputs, hence the ``()`` -
then finally there is ``: int`` which tells the compiler this function returns an integer.

!!! note
	Why return an integer? It allows the operating system to know if our program executed successfully.
	If a program returns ``0``, then the OS knows the program finished successfully, if it returns any other value
	(typically ``1``) then the operating system knows the program failed.

Line 4, we parsed the constant value ``Hello World`` to the function ``println``, which then sent the input to the standard output of the system.
Hence why we saw it.

Finally line 5, we return ``0``, as our program executed successfully.