# Declaration

When simply declaring a name, the type must be explicitly stated
```uniview
let a: int;
```

However if a name is being assigned on declaration the type can be inferred, and thus ommited from the code
```uniview
let a = 1;
```

Both of these statements define ``a`` as an ``int``, however only the second one defines the value.
Attempting to use an undefined value will result in a crash at compile time.

!!! info inline
	This example will not compile, as line 3 attempts to use an undefined value.

```uniview hl_lines="2" linenums="1"
let a: int = 0;
println(a); // (1)
println(a);
```

1. The value refered to by `a` has been consumed
