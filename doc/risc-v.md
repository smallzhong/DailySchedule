+ `x0` 这个寄存器的值通过硬连线的方式固定为0。主要是为了性能考虑。例如 `add x0, x3, x4` 这样的指令是无效的。因为没法往 `x0` 里面写东西。
+ ![image-20210706192954734](https://cdn.jsdelivr.net/gh/smallzhong/new-picgo-pic-bed@master/image-20210706192954734.png)
+ `RISC-V` 指令集中没有专门的逻辑非指令。使用 `xor` 让值与 `0x11111111` 异或即可得到逻辑非的结果。

