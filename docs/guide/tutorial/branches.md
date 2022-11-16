# Branches

Branches take a boolean expression, then will only execute a single block of code depending on the condition. You can chain multiple conditions with the `elif` clause. With an optional final `else` clause for if none of the conditions are met.

```uv
if (a > 0) {
  printf("Positive");
} elif (a < 0) {
  printf("Negative");
} else {
  printf("Zero is positive?");
}
```

Variables must be in the same state of definition after a branch has concluded.

```uv
let book: Book;
if (nearLibrary) {
  book = loanBook();
} else {
  book = buyBook();
}
// after either possibility
// book is always defined
```

```uv
let book = Book.new();
if (nearLibrary) {
  donate(book);
} else {
  sell(book);
}
// after either possibility
// book is always undefined
```