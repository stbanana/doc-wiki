---
update:
  - date: 2024-12-25
    author: yono
    version: 0.1.0
    content: 基础的介绍
update_open: true
---

建立这个库的本意是补充 [modbusX](/modbusX/zh_hans/) 在实际应用中没有照顾到的点，辅助外设驱动的开发。

总用时约 5 小时，仍有诸多不足之处。

# 作用

期望帮助那些管理不好以下两项的小白，符合任何一项都可以使用本库解决。

>传输流的 DMA。
>
>传输流的半双工用法。

一个典型的应用场景是，串口的 RS485 通信。

# 副作用
>**延迟**: 会带来收发数据 1~2ms 的额外延迟，主要是确保切换半双工方向的稳定性。
>
>**资源**: 会加倍 RAM 空间的消耗。