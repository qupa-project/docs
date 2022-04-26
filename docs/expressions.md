# Expressions

Three locations for valid expressions:

- Call argument
- If statement
- Assignment

Unlike some other languages such as Javascript, only one type of expression can exist standalone.
The only valid standalone expression is a call, which then must also be followed by a semi-colon (``;``) for code consistency.

```uniview hl_lines="2"
fn main() {
	println("Hello World");
	return 0;
}
```

## Opperations

!!! note
	An operator is any: constant value (i.e. ``1``, ``true``, ``"Hello"``), variable, or another expression.

## Logical

!!! note
	If one operator is able to determine the result of the operations - then the second operator may never compute.

	For instance if the first opperator or an or opperation is true, it is not necessary to compute the second, as the result will always be true.

#### And Opperator
Takes two boolean operators values and returns true when both values are true. ``a && b``

#### Or Opperator
Takes two boolean opperators and returns true when both values are true. ``a || b``

#### Invert Opperator
Takes one opperator and returns the inverse value. For instace a true opperator would return false.  ``!a``

## Comparison

In all cases, takes two operators and comparse the two values as according to standard mathematical principles. ``a < b``, ``a > b``, ``a <= b``, ``a >= b``, ``a == b``, ``a != b``.

## Arithmetic

#### Add
Returns the sum of two operators ``a + b``

#### Subtract
Returns the subtration of second opperator from the first ``a - b``

#### Multiply
Returns the multiple of two operators ``a * b``

#### Divide
Returns the division of the second operator from the first ``a / b``

#### Remainder
Returns the remainder of a division of the second operator from the first ``a % b``

## Value Management

#### Lend Opperator
This opperator can only exist direct as an argument for another function.  
It cannot be pressent in any other location.  
The lend opperator is a ``@`` followed by a variable.

#### Clone Opperator
This opperator can exist in any valid expression, and will create a duplicate of the value without consuming it.  
This allows effectively allows a value to be used multiple times without breaking memory safety.  
This expression is made with a ``$`` followed by a variable name.  