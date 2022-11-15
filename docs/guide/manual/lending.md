# Lending

Axioms:

  * A muttable lend (`@`) can only be created if **all** of the following:
    * The variable is defined
    * No immutable lends exist on the variable already
    * No mutable lends exist on the variable already (though a variable referring to lent value can be mutably lent)
    * The variable itself is not a constant
  * An immutable lend (`$`) can only be created if **all** of the following:
    * The variable is defined
    * No mutable lends exist on the variable

## Syntax

```bnf
lend ::= ( "@" | "$" ) <variable>
```