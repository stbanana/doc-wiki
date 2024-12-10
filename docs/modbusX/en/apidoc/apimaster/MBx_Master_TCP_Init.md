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

Initialize the MBX master object for TCP and pass various configuration parameters to initialize this _MBX_MASTER type master object.

### Parameters

> - MBxMaster: Pointer to the master object to be initialized.
> - MBxSend: A function pointer for the data sending port.
> - MBxGetc: A function pointer for the data receiving port.
> - RxBuffer: Pointer to a memory space for storing received data.
> - RxBufferSize: Total length of the memory space for storing received data. This memory space determines the maximum length of a single slave response that can be parsed.
> - TxBuffer: Pointer to a memory space for storing data to be sent.
> - TxBufferSize: Total length of the memory space for storing data to be sent. This memory space determines the maximum length of a single master request that can be sent.

### Return Value

> - MBX_API_RETURN_DEFAULT(0x00): Normal return.
> - MBX_API_RETURN_ERR_PARAM(0x02): Parameter error, check the parameters passed during the call.