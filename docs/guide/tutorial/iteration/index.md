# Iteration

Iteration in Uniview is designed to follow the flow of data rather than the flow of execution. Because of this it doesn't follow traditional for/while loop patterns, and instead uses data flow operands of: `unfold`, `map`, `filter`, `fold`.

!!! note "A note for experienced developers"
    It important to note when these operations are chained no intermediary values are generated unlike some other languages. In languages such as Javascript, if you run a map on an array, then map on that result; you actually generate an entire intermediary array. Where as in Uniview these features are an abstraction of flow control, and thus don't generate entire intermediary results unless the program is explicitly designed in that way.