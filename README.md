# range

Iterate through the specfic range like Python's `range()` in V.

## Why

- `a..b` in V can only be in increasing order and not in negative order.
- Lacks inbuilt `step` which most people need or want.
- No support for `float`.

## Features

- Make `range` arrays easily
- Make ranges for `int` and `f32`
- Positive as well as Negative Support!
- No need to write the whole for loop! (*this maybe slower than the normal one*)
- Use `range` for functional programming
- Full Python's `range()` functionality

## Installation

- Via `git clone`
    - `git clone https://github.com/Delta456/range`
- Via `v install`
    - `v install range`
- Via `vpkg`
    - `vpkg install range`

### Usage

- `range.range(start:0, stop:value, step:1)` 
  makes a range of `int` with the following parameters:
  - `start`: `start` value of the range *by default it's 0*
  - `stop`: `stop` value of the range
  - `step`: `step` value of the range *by default it's 1*

- `range.range_float()` makes a range of `f32` with the following parameters:
  - `start`: `start` value of the range *by default it's 0.0*
  - `stop`: `stop` value of the range
  - `step`: `step` value of the range *by default it's 1.0*

**Note**: If `range.range(step:0)` or `range.range_float(step:0)` then an error will be raised because `step` cannot be zero.

In `main.v`

```v
import delta456.range

fn main() {
    // using range.range
    for i in range.range(stop:10) {
        println(i)
    }

    for i in range.range(start:1, stop:10) {
        println(i)
    }

    for i in range.range(start:1, stop:10, step:2) {
        println(i)
    }

    for i in range.range(start:10, stop:1, step:-1) {
        println(i)
    }

    for i in range.range(start:-5, stop:-1, step: 1) {
        println(i)
    }

    // using range.range_float
    for i in in range.range_float(stop:10) {
        println(i)
    }

    for i in in range.range_float(stop:10, step:0.2) {
        println(i)
    }

    for i in in range.range_float(start:0.1, stop:10) {
        println(i)
    }

    for i in in range.range_float(start:10, stop:1.0, step:-0.2) {
        println(i)
    }

    for i in in range.range_float(start:-10, stop:-1.0, step:0.2) {
        println(i)
    }
}
```

### Acknowledgments

I thank [@Hungry Blue Dev](https://github.com/hungrybluedev) for giving me the idea of using a `struct` with default parameters so that `range` function for each type can be the same.

### License

Released under [MIT](LICENSE)
