# 用 `format!` 连接字符串

## 描述

对于可变`String`，可以使用`push`和`push_str`来构建字符串，或者使用`+`操作符。然而，通常更方便的是使用`format!`，尤其是存在字面量和非字面量字符串混合使用的时候。


## 示例

```rust
fn say_hello(name: &str) -> String {
    // 我们可以这样构建字符串.
    // let mut result = "Hello".to_owned();
    // result.push_str(name);
    // result.push('!');
    // result

    // 但是使用format! 更好.
    format!("Hello {}!", name)
}

fn main() {
    let hi = say_hello("blackanger");
    println!("{}", hi);
}
```


## 优点

使用 `format!` 通常是最简洁最可读的组合字符串的方式。

## 缺点

它通常不是最有效率的组合字符串的方式，对于可变字符串`push`操作才是最有效率的（尤其是已经预分配给定大小的字符串）。

