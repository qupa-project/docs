# Functions

There are three main rules applied to functions to ensure the safety of code within Uniview.

- A child function can never outlive it's parent
- Any function must have ownership over all values it touches through it's entire life time
- All functions must return a value


## Declaration

All functions must have three main elements

- Name
- Signature
- Return type

The combination of a name, and signature must also make any function unique.
Hence you cannot have two instances of the same function.

All types within a function header must be explicit as they cannot be efficiently infered.


??? example
	This function takes no inputs, but outputs one int
	```uniview
	fn main(): int {
		// body
		return 0;
	}
	```

	This function takes two input ints, but returns no output
	```uniview
	fn main(a: int, b: int): void {
		// body
		return;
	}
	```


## Calling Convensions
To be written

## Lending

Values of any type can also be lent to function calls (but only in function calls).
This may appear as reusing a value, but instead is actually a contraction of a reassignment.
Any value that is lent, is actually parsed forward,
then the function returns an extra result which is then reassigned to the same name.


??? example
	Here is an example of adding integers not using lending.
	```uniview
	fn main() {
		let value = 3;
		value = add(value, 3);
		println(value); // 9
	}

	fn add(a: int, b: int) {
		return a + b;
	}
	```


	Here is an example of adding integers not using lending.
	```uniview
	fn main() {
		let value = 3;
		add(@value, 3);
		println(value); // 9
	}

	fn add(a: @int, b: int) {
		a = a + b;
	}
	```

#### Why using lending? The two examples are the same length.
In this example we were using ``int`` which is a primative type, hence there is no real advantage.
However later when we introduce classes, this method can have minor improvements
due to the compiler being able to easily determine more information about the program.

When classes are introduced later, the benfits will become more obvious of the reduce code needed,
and the increased clarity.

#### When should I use lending?
If the primary goal of your function is to alter some value then return it,
it is generally better to use lending for any none ``normal`` type values.

#### What happens to a name while a value is lent?
While a value is lent the name will appear undefined, only once the value has returned will the name be reuseable
The below example will not compile as for the second argument is attempting to lend a now undefind value, because ``a`` has already been temporarily consumed.
```uniview
consume(@a, @a);
```