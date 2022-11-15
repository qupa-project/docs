# Variables

Variables are a method to tell the compiler what data you're referring to, think of it like giving a name to something in real life. If you name your dog `geff`, it changes nothing about the dog, where it is, what type of dog it is, how clean it is; however now that the dog has a name, when we refer to something as `geff` we know you are referring to the dog you named earlier.

This is how variables behave in Uniview; unlike some other languages the act of assigning a variable does nothing to the value you're assigning a name to.

To assign a variable you simply use the `let` keyword with the name and an equals to specify what you are naming.
```uv
let a = 2;
```

You can also reserve a name without actually giving it a value yet, however when you don't specify an initial value, you need to tell the language what type of data this name will be given to later.
```uv
let number: int;
// some long calculations...
number = 42;
```

You can also be explicit though it is not necessary and define the type of a name when you initially assign it.
```uv
let number: int = 42;
```

## Undefined Variables

So what happens when you reserved a name, but haven't defined it? In this case the compile will tell you that you're trying to use a `undefined variable`, because you haven't defined what the variable refers to yet.
```uv
let number: int;
say(number); // Error: undefined variable 'number' (1)
```

1. This function doesn't actually exist, but for explanatory purposes we can say what ever number is in the brackets gets printed to the console.

Variables must always be assigned before they can be used, because a name which you haven't given to anything, can't be used to refer to anything.

## Revoking Variables

Variables can also return back to the initial undefined state, however they need to be assigned before they can be used again.
```uv
let geff = Buy_A_Dog();
// Geff now refers to a dog you just bought
Sell_Dog(geff);
// Geff no longer refers to anything
//  you must assign geff to something before it can be used again
```

## Renaming a value

You can also rename a value, and when a value has a new name, the old name no longer refers to anything and becomes undefined
```uv
let geff = Buy_A_Dog();
let john = geff;
// The dog you just bought is now referred to as John
// Geff now doesn't refer to anything
```
