---
class: heading_no_counter
draft: false
---

# 收发数据 系列API

## DFlow_Write

### source

```c
uint32_t DFlow_Write(_DFlow *df, 
                    uint8_t *pcBuf, 
                    uint32_t ui32Len
                    );
```

使用某个 DFlow 对象发送一段数据。实际上是推入待发送 buffer，在合适时机统一发送。

### 传参

> - df：期望发送的 DFlow 对象
> - pcBuf：期望发送的数据buffer头
> - ui32Len：期望发送的数据长度

### 返回值

> - DFLOW_API_RETURN_DEFAULT(0x00)：正常返回
> - DFLOW_API_RETURN_BUFFER_FULL(0x20)：待发送 buffer 已满

## DFlow_Writec

### source

```c
uint32_t DFlow_Writec(_DFlow *df, 
                    uint8_t data
                    );
```

使用某个 DFlow 对象发送一个字节。实际上是推入待发送 buffer，在合适时机统一发送。

### 传参

> - df：期望发送的 DFlow 对象
> - data：期望发送的字节数据

### 返回值

> - DFLOW_API_RETURN_DEFAULT(0x00)：正常返回
> - DFLOW_API_RETURN_BUFFER_FULL(0x20)：待发送 buffer 已满

## DFlow_Getc

### source

```c
uint32_t DFlow_Writec(_DFlow *df, 
                    uint8_t *data_rx
                    );
```

从某个 DFlow 对象取一个字节。实际上从已接收 buffer 获得数据。

### 传参

> - df：期望获得数据的 DFlow 对象
> - data_rx：取到的字节数据

### 返回值

> - DFLOW_API_RETURN_DEFAULT(0x00)：正常返回
> - DFLOW_API_RETURN_BUFFER_EMPTY(0x21)：已接收 buffer 是空的