## Lending

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

[Lending Manual :octicons-arrow-right-24:](/guide/manual/lending/){small}