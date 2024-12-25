---
class: heading_no_counter
draft: false
---

# DFlow_Init

### source

```c
uint32_t DFlow_Init(_DFlow *df, 
                    void *AllBuffer, 
                    uint32_t TBufferLen, 
                    uint32_t RBufferLen, 
                    _DFLOW_COMMON_FUNCTION *Func
);
```

初始化 DFlow 对象，并传入各种配置参数对这个对象进行初始化。

### 传参

> - df：期望初始化的 DFlow 对象指针。
> - AllBuffer：所有可供分配的内存区，用于分配Tx、Rx的Buffer。注意：内存区大小必须不小于 `TBufferLen * 2 + RBufferLen * 2`。
> - TBufferLen：单个TxBuffer的长度。
> - RBufferLen：单个RxBuffer的长度。
> - Func：port 函数集合指针，也就是需要额外一个变量，绑定一些 port 函数，并统一绑定给 DFlow 对象。

### 返回值

> - DFLOW_API_RETURN_DEFAULT(0x00)：正常返回
> - DFLOW_API_RETURN_ERR_PARAM(0x02)：传参不符合要求，例如某些必需 port 函数没有绑定
