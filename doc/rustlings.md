+ ![image-20210705082408486](C:\Users\雨初\AppData\Roaming\Typora\typora-user-images\image-20210705082408486.png)
+ `slice` 没有对原变量的所有权，返回的是一个引用。
+ 设置一个元组 `ChangeColor(i32:i32:i32)` 
+ 函数返回时可以返回一个元组，这样可以达到返回多个返回值的目的。
+ `format!` 返回的也是一个 `String` 。
+ `str` 和 `String`之间的区别：`String`是一个可变的、堆上分配的UTF-8的字节缓冲区。而`str`是一个不可变的固定长度的字符串，如果是从`String`解引用而来的，则指向堆上，如果是字面值，则指向静态内存。
+ `Result<T, E>` ， `T` 是正常返回的话返回的值， `E` 是出现错误的话返回的错误信息。
+ `errors5.rs` 没明白。先跳过了。
+ 想要在遍历的时候获取当前元素的下标的话可以 `iter as usize` 。