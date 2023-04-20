# Notes

## String vs &str

String is an array of characters and is resizable. They can be altered after creation. After creation, we "own" this memory and can modify it.

&str is a pointer to the heap in memory shich is ready only. If you don't need to modify the string use &str.

Both &str and String content are stored in heap, while they are just pointers stored in stack. String point has address and length and capacity, while &str only has address and length.

## Display vs Debug trait

Display trait is implemented on all primitive types in Rust. But complex data structures such as vectors do not have display trait. They have Debug trait.

To derive the Debug trait, add `#[derive(Debug)]` to the top of your own struct and avoid implementing the trait.

Use "{:#?}" for multiline printing.

## Handling Option and Result with unwrap and expect

unwrap just panic, expecte panics with an error message. Do not use them in production. Always use match to handle error cases.

Result has an additional Error branch comparing to Option, which gives error message when something went wrong.
