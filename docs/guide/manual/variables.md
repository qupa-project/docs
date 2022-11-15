# Variables

Axioms:

  * All variables must be initially defined with the `let` keyword
  * Variables can start in and return to an undefined state
  * Variables being used in an undefined state will throw a compile time error
  * Variables with an initially undefined state must have their [type](/manual/types.md) explicitly defined
  * A variable cannot be defined with the same name as a variable that is already in scope
  * At the end of a scope of which a variable was declared, if the variable is not undefined; the drop trait will be called if implemented for the type

## Syntax

```bnf
name ::= ( "a".."z" | "A".."Z" | "0".."9" | "_" )+

declare ::= "let" <name> (":" <type>)? ("=" <expr>)? ";"
variable ::= <name> ( <access-static> | <access-dynamic> | <access-template> )*
  access-static ::= "." <name>
  access-dynamic ::= "[" <variable> ( "," <variable> )* "]"
  access-template ::= "#[" <type> ( "," <type> )* "]"
```