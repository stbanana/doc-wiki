---
class: heading_no_counter
draft: false
---

# MBx_Master_TCP_Init

### source

```c
uint32_t MBx_Master_RTU_Init(_MBX_MASTER *MBxMaster, 
                             MBX_SEND_PTR MBxSend,
                             MBX_GTEC_PTR MBxGetc,
                             uint32_t     BaudRate,
                             uint8_t     *RxBuffer,
                             uint32_t     RxBufferSize,
                             uint8_t     *TxBuffer,
                             uint32_t     TxBufferSize
                             );
```

作为 TCP 初始化 MBX 主机对象，并传入各种配置参数对这个 _MBX_MASTER 类型主机对象进行初始化。

### 传参

> - MBxSlave：期望初始化的主机对象指针。
> - MBxSend：另实现的数据发送 port ，是一个函数指针。
> - MBxGetc：另实现的数据接收port，是一个函数指针。
> - RxBuffer：用于存放接收数据的一段内存空间头指针。
> - RxBufferSize：用于存放接收数据的内存空间总长度。这个内存空间决定了解析单条从机回复的最大长度。
> - TxBuffer：用于存放发送数据的一段内存空间头指针。
> - TxBufferSize：用于存放发送数据的内存空间总长度。这个内存空间决定了发送单条主机请求的最大长度。

### 返回值

> - MBX_API_RETURN_DEFAULT(0x00)：正常返回
> - MBX_API_RETURN_ERR_PARAM(0x02)：传参异常，检查调用时的传参。