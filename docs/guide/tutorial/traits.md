# Traits

Traits are a way to specifying a type meets certain requirements, for instance we can say anything that talks, will have a speak function associated with it:

```uv
trait Speak {
  fn speak(thing: $Self);
}
```

Traits can have a list of abstract functions, which are functions with don't have a body. These traits can then be implemented on a type, allowing them to act under that trait. Hence you can have functions which take values which implement speaking, and then you know they will always have the speak function.

You can also see the speak function takes in a immutable reference to a type of itself. The `Self` type is only available in certain scopes such as within a `trait` definition. This type will be replaced with the type of anything that it is being implemented on. For instance if you implemented `Speak` on a `Human` then the `speak` function will need to take `$Human` as it's argument.

There are a few built in traits which aren't required for types, but do have certain compilation behaviour.

This trait is called when a value falls out of scope, this also includes when a return statement is called as the function will end at that point.
```uv
trait Drop {
  fn drop(Self);
}
```