# Functions

## Syntax
```bnf
func ::= "fn" <name> "(" arg ("," arg)* ")" ( ":" <type> )? ( ";" | <body> )
  arg ::= <name> ":" <type>
  body ::= "{" <stmt>* "}"
  stmt ::= <declare> | <branch> | <return> | <drop> | <assign> | <call>
```