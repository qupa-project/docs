# Functions

While we haven't explained much you can do in the language yet, understanding functions are a fundamental part of the later explanations.

Functions are a way of reusing code, and allow for values to be parsed around. All functions must have a name, brackets for arguments and a body.
```uv
fn doSomething() {
  print("Hello");
}
```

Functions take arguments in a very similar way to reversing a name, however without the `let` keyword, and using a `,` instead of a `;` at the end of each one.
```uv
fn add(a: int, b: int) {}
```

Functions can also then have a return value which is stated after the brackets, again very similar to reserving a name like before.
```uv
fn add(a: int, b: int): int {
  return a + b; // (1)
}
```

  1. This takes the two numbers given, adds them together, then returns them

Once a function is defined it can be used indefinitely.
```uv
let a = add(3, 5);  // a = 8
let b = add(6, -3); // b = 3
// ...
```

!!! note
    When you give a variable to a function it becomes undefined, as you have given the value away - so now the variable refers to nothing.

Functions along with structures, traits, implements, and imports are top level statements. Meaning they can be written in the top level of the file. Unlike assignment and declaration which need to be within a function.

[Functions Manual :octicons-arrow-right-24:](/guide/manual/functions/){small}