# Variables and Values

Variables within Uniview should be thought of in a slightly different way to most languages.
Instead of thinking about assigning values to variables, it would be more accurate to say that you're giving a name to a value.
You could think about it like naming a car; if you provide a car with a name, it doesn't change anything about the car itself or where it is stored - instead now you just have a way to refer to it.

Continuing with this metaphor, it would be confusing for any specific car to have multiple names; hence, it loses any previous name when receiving a new one.

```uniview
let a = Car.New(); //(1)
let b = a; //(2)
```

1. A new car is created, and the name `a` now refers to it.
2.  `a` is now undefined, as the value has been handed to `b`

Initally a `Car` is created, then the compiler knows this value will be referred to as `a`. Then the value which was previously refered to as `a` is now being renamed to `b` - leaving `a` as an undefined variable. The compiler will now throw an error if `a` is attempted to be used, as it refers to no value.

The transfer of a value between variable names has no compile time affect, unless that name needs to be recomposed into a structure, class, or actor.

!!! note
	The example above is using a linear type, this means a value is used always once. Hence it can only be used one time, but also cannot be left dangling and must always be consumed.
	Above ommits the destruction of car as that concept is discussed later.