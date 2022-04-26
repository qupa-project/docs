# Type Systems

!!! note
	If you are a novice programmer, this section has a lot of information to take in.
	Do not expect to fully understand the concepts just from reading this page.
	However through applying these concepts in the later sections it will become clear.

There are actually three different type systems within Uniview, which may sound complicated, but most programmers will only ever interact with two of them.
And even then it actually assists you a lot more than you might otherwise think.


## Normal Types
Any sort of primitive, or intrinsic types such as numbers or booleans, act under the ``normal`` type system.
This allows you to reuse these values.
```uniview linenums="1"
let a = 3;
println(a); // 3
println(a); // 3
println(a); // 3
```

!!! note
	There are no errors in this example as the value ``a`` is never consumed due to it being of a ``normal`` type ``int``.

| Category | Types |  |  |  |  |
|:-|:-:|:-:|:-:|:-:|:-:|
| Integers | int | i64 | i32 | i16 | i8 |
| |  | u64 | u32 | u16 | u8 |
| Floats | double | float |
| Booleans | bool |
| Nulls | void |


## Linear Types
Values of this type must always be consumed.
In the first example since ``Car`` is a ``class`` it means it follows a linear type system - hence it would crash the earlier code snippet as the value is never consumed.
To recreate the snippet in a form that would compile, we would write.
```uniview
let a = Car.New();
let b = a;
delete b;
```

After the final line, we know ``a`` was consumed in the assignment for ``b`` - and ``b`` was deleted.
So all values have been destroyed, so it's safe to execute.


## Affine Types

!!! warning
	This type system is primarily to allow interfacing with forign languages.
	If you are not planning on creating core commponents or added features to the language.
	You do not need to read or understand these features.

Values of this type can only be used once, however they can also be used zero times.
```uniview hl_lines="4" linenums="1"
struct Person {}

let a = Blank#[Person]();
print(a);
```

After the final line in the above example, ``a`` becomes undefined, as the value was consumed by the ``print`` function.
However if that line was commented out, there would also be no error.