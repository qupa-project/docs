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

[Functions Manual :octicons-arrow-right-24:](/guide/manual/functions/){small}

## Lending a Value

Sometimes sending a value to a function just to reassign it afterwards can get quite complicated, and annoying. Especially if you want to send your two dogs to get washed and have them come back to have the same names. That's where lending comes in, instead of giving your dogs away, then reassigning their names when you get them back, you can loan the values as a form of short hand.
```uv
clean_dogs(@geff, @john);
```

Putting an `@` sign before a variable name means you are simply lending the value, and that it will return back to it's name once the operation (in this case dog cleaning) is done.  
But what if you don't want to let them change your dogs? What if you just want a check up, and want to make sure they don't change your dogs?  
In that case you must use a `$` instead of the `@` sign since you are lending the worth (aka value) of the dog, but not loaning them the right to change it.

```uv
checkup($geff);
```

[Lending Manual :octicons-arrow-right-24:](/guide/manual/lending/){small}