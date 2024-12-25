---
class: heading_no_counter
draft: false
---

# DFlow_Ticks

### source

```c
void DFlow_Ticks(
               _DFlow *df
              );
```

必须周期调用, 驱动 Dataflow 系统的关键函数。仅驱动传入的 DFlow 对象，推荐是 1ms 调用一次，也可以更短的周期进行调用，会稍微增加 CPU 的消耗，并稍微减小通道切换的延时。

### 传参

> - df：期望驱动的 DFlow 对象

### 返回值

> 无返回