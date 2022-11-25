# Generator

```uv
fn range(from: int, to: int): Gen#[int] {
  let nx = from;
  
  return unfold (val=from) {
    let nx = from;
    from = from + 1;
    return nx;
  } terminate (val){return val == to};
}

fn take(gen: Gen#[type], int: count): Gen#[int] {
  let tally = 0;

  return gen terminate (val) {
    tally = tally + 1;
    return tally == count;
  }
}


range(1, 100) -> take(5)
1 -> add(2)
```