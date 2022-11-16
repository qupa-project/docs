# Structures

Structures are away of composing data so multiple bits of information can be parsed together rather than individually.
To define a new type of structure you need to use the `struct` keyword in the top level of a file, then define the attributes similar to how variable names are reserved.

```uv
struct Person {
  name: String,
  height: float,
  age: int
}
```

You can then create a instance of a structure in a very similar manner

```uv
let geff = Person {
  name: "Geff",
  height: 178,
  age: 27
};
```

When accessing the values of a structure it is `decomposed`, meaning each attribute is now treated like a variable. And thus like a standard variable they can return back to the undefined state.

```uv
printNameTag(geff.name); // (1)
```

  1. Geff's name has been consumed by the function, and thus they now have an undefined name attribute.

The only issue with leaving a structure's attribute undefined is when the value is dropped or when you attempt to use the whole structure. Continuing from the previous example if we attempted to run the code.

```uv
employ(geff); // error: geff.name undefined
```

We will get a compile error as Geff does not have a name property.

Similarly if the function returns, or the variable falls out of scope (the code travels up a block from when it was defined) - if this structure has the `drop trait` implemented. You will get a compile error, as the compiler cannot call `drop` on your variable as it has an undefined attribute.