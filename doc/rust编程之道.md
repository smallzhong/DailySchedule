+ `rust` 中没有GC，内存首先由编译器来分配， `rust` 代码被编译为 `llvm ir` ，其中携带了内存分配的信息。所以编译器需要事先知道类型的大小，才能分配合理的内存。

+ ![image-20210707183040002](https://cdn.jsdelivr.net/gh/smallzhong/new-picgo-pic-bed@master/image-20210707183040002.png)

+ `rust` 中不支持传统面向对象的继承，但是可以支持 `trait` 的继承。

+ 想要进行 `trait` 的继承的话如下 `trait Paginate: Page + PerPage {...}` 。这里冒号后面的代表 `trait` 继承。其后跟随要继承的父 `trait` 名称。如果是多个 `trait` 则用加号相连。

+ 可以对泛型的实现进行泛型约束

  ![image-20210707183652314](https://cdn.jsdelivr.net/gh/smallzhong/new-picgo-pic-bed@master//image-20210707183652314.png)

  这里实现 `sum` 这个 `trait` 的对象必须继承 `Add` 这个 `trait` 。在代码清单3-35中，我们使用＜T：Add＜T，Output=T＞＞对泛型进行了约束，表示sum函数的参数必 须实现Add trait，并且加号两边的类型必须一致。这里值得注意的是，对泛型约束的时候，Add＜T， Output=T＞通过类型参数确定了关联类型Output也是T，也可以省略类型参数T，直接写为Add＜Output=T ＞。

+ ![image-20210707184244836](https://cdn.jsdelivr.net/gh/smallzhong/new-picgo-pic-bed@master//image-20210707184244836.png)

  `A + B` 表示交集

+ 变量遮蔽并不会主动析构原来的变量。它会一直存在直到函数退出（离开作用域）。

+ 常量没有固定的内存地址，因为其生命周期是全局的，随着程序的消亡而消亡，并且会被编译器有效地内联到每个使用它的地方。

+ 静态变量的生命周期也是全局的，但它并不会被内联，每个静态变量都有一个固定的内地址。


### unsafe

+ 对于不可变静态变量来说，访问它不存在任何安全问题。 `rust` 也允许定义可变的静态变量。但是如果多个线程同时访问这个可变静态变量，一定会引起数据竞争，这是 `rust` 安全检查绝对不允许发生的事情。因此如果想要修改可变的静态变量的话必须将代码块包在 `unsafe` 块中。
+ `#repr(C)` 表示此联合体使用和C语言一样的内存布局。
+ 