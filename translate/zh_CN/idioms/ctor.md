# 构造函数(Contructors)

## 描述

Rust没有语言级的构造函数。所以我们约定，使用静态`new`方法来创建对象。



## 示例

```rust
// A Rust vector, see libcollections/vec.rs
pub struct Vec<T> {
    buf: RawVec<T>,
    len: usize,
}

impl<T> Vec<T> {
    // 构造一个新的空的 `Vec<T>`.
    // 注意这里是静态方法，而不是self.
    // 该构造函数没有任何参数，但有时候只是为了初始化对象
    
    pub fn new() -> Vec<T> {
        // Create a new Vec with fields properly initialised.
        Vec {
            // 注意这里有 RawVec 的构造函数.
            buf: RawVec::new(),
            len: 0,
        }
    }
}
```

## 相关

[builder pattern](../patterns/builder.md)用于构造有多个配置的对象。