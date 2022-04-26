# Variables and Values

Variables within Uniview should be thought of in a slightly different way to most languages.
Instead of thinking about assigning values to variables, it would be more accurate to say that you're giving a name to a value.
You could think about it like naming a car; if you provide a car with a name, it doesn't change anything about the car itself or where it is stored - instead now you just have a way to refer to it.

Continuing with this metaphor, it would be confusing for any specific car to have multiple names; hence, it loses any previous name when receiving a new one.

```uniview
let a = Car.New();
let b = a;
```

At line one, a blank ``Car`` is created, then the compiler knows that the term ``a`` refers to the car generated.
Once line two then has no affect at runtime, however the compiler now knows that ``b`` refers to the car - and ``a`` now becomes undefined

!!! note
	The example above is using a linear type, this means a value is used always once. Hence it can only be used one time, but also cannot be left dangling and must always be consumed.
	Above ommits the destruction of car as that concept is discussed later.