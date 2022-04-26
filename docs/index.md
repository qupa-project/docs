# Uniview

The core concept behind the language is adding the smallest restrictions of variable visibility and lifetime to create massively possitive side affects. Each value may only be viewed once, the only way to re-view a value is if a clone was produced within the first sighting. Otherwise values are treated as complete black boxes until viewing is necessary.
```uniview
let p = Blank#[Person]();
print($p); // prints a clone of p
print(p); // p is consumed by print
// p is now undefined
```

There is also another very important concept to this language of inline-returns. This can be thought of as like lending a value forwards, however it would be more accurate to say you are giving the value forward, then reassigning that name to the result.
```uniview
age($p);
print(p); // no change as a clone was passed

age(@p);
print(p); // the person is now older
```
