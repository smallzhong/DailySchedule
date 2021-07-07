+ `rust` 中没有GC，内存首先由编译器来分配， `rust` 代码被编译为 `llvm ir` ，其中携带了内存分配的信息。所以编译器需要事先知道类型的大小，才能分配合理的内存。
+ ![image-20210707183040002](https://cdn.jsdelivr.net/gh/smallzhong/new-picgo-pic-bed@master/image-20210707183040002.png)
+ `rust` 中不支持传统面向对象的继承，但是可以支持 `trait` 的继承。
+ 

