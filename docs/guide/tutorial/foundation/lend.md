# Lending

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

## Function Lending

You cannot simply however just give a lent value to any function, lending capabilities of a function are part of their argument signature. For instance the function declarations for the functions in the above examples would be:

```uv
fn clean_dogs(a: @Dog, b: @Dog) {}
fn checkup(a: $Dog) {}
```

Also the lending state is part of the signature meaning you could have another definition for the checkup function which does mutate the dog declared.

```uv
fn checkup(a: @Dog) {}
```

## Upgrades

!!! danger
    This is not implemented in the current version of Uniview

If a immutable loan is the only loan on a value which itself is not a immutable loan or constant value. Then and only then can the reference be upgraded.

```uv
let ref = $value;
upgrade ref; // (1)
```

1. `ref` is now a mutable (`@`) reference

A counter example would be:

```uv
fn checkup(a: $Dog) {
  let b = $a;
  upgrade b; // error (1)
}
```

1. `b` cannot be upgraded as it is loaning a non-mutable value.

[Lending Manual :octicons-arrow-right-24:](/guide/manual/lending/){small}