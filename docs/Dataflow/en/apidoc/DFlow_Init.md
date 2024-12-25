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

Initialize the DFlow object and pass it various configuration parameters.

### Parameters

> - df：DFlow object。
> - AllBuffer：All available memory areas are used to allocate buffers for Tx and Rx. Note: The memory area must be no smaller than `TBufferLen * 2 + RBufferLen * 2`.
> - TBufferLen：The length of a single TxBuffer.
> - RBufferLen：The length of a single RxBuffer.
> - Func：The port function collection pointer, that is, an additional variable, binds a number of port functions and binds them uniformly to the DFlow object.

### Return Value

> - DFLOW_API_RETURN_DEFAULT(0x00)：Normal return.
> - DFLOW_API_RETURN_ERR_PARAM(0x02)：Passing parameters does not meet the requirements; for example, some required port functions are not bind.
