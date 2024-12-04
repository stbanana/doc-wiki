---
class: heading_no_counter
draft: false
---

# MBx_Ticks

### source

```c
void MBx_Ticks(
               uint32_t Cycle
              );
```

必须周期调用, 驱动 modbusX 系统的关键函数。无论主机还是从机，均由这个唯一的库tick进行驱动。

### 传参

> - Cycle：调用本函数的周期值us

### 返回值

> 无返回
