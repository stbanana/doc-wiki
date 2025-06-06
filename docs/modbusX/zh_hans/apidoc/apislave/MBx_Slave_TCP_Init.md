---
class: heading_no_counter
draft: false
---

# MBx_Slave_TCP_Init

### source

```c
uint32_t MBx_Slave_TCP_Init(_MBX_SLAVE                *MBxSlave, 
                            uint8_t                    SlaveID,
                            const _MBX_MAP_LIST_ENTRY *MAP,
                            MBX_SEND_PTR               MBxSend,
                            MBX_GTEC_PTR               MBxGetc,
                            uint8_t                   *RxBuffer,
                            uint32_t                   RxBufferSize,
                            uint8_t                   *TxBuffer,
                            uint32_t                   TxBufferSize
                           );
```

作为 TCP 初始化 MBX 从机对象，并传入各种配置参数对这个 _MBX_SLAVE 类型从机对象进行初始化。

### 传参

> - MBxSlave：期望初始化的从机对象指针。
> - SlaveID：该从机对象配置为的从机 ID ，范围 1~247 。
> - MAP：该头指针指向以 MBX_MAP_LIST_END 宏为结尾的 list 表。定义所有可能的地址。
> - MBxSend：另实现的数据发送 port ，是一个函数指针。
> - MBxGetc：另实现的数据接收port，是一个函数指针。
> - RxBuffer：用于存放接收数据的一段内存空间头指针。
> - RxBufferSize：用于存放接收数据的内存空间总长度。这个内存空间决定了解析单条请求的最大长度。
> - TxBuffer：用于存放发送数据的一段内存空间头指针。
> - TxBufferSize：用于存放发送数据的内存空间总长度。这个内存空间决定了发送单条回复的最大长度。

### 返回值

> - MBX_API_RETURN_DEFAULT(0x00)：正常返回
> - MBX_API_RETURN_MAP_UNFORMAT(0x101)：传入的MAP表不规范