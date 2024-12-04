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

Initialize the MBX slave object for TCP and pass various configuration parameters to initialize this _MBX_SLAVE type slave object.

### Parameters

> - MBxSlave: Pointer to the slave object to be initialized.
> - SlaveID: The slave ID to be configured for this slave object, in the range of 1 to 247.
> - MAP: A pointer to a list ending with the MBX_MAP_LIST_END macro, defining all possible addresses.
> - MBxSend: A function pointer for the data sending port.
> - MBxGetc: A function pointer for the data receiving port.
> - RxBuffer: Pointer to a memory space for storing received data.
> - RxBufferSize: Total length of the memory space for storing received data. This memory space determines the maximum length of a single request that can be parsed.
> - TxBuffer: Pointer to a memory space for storing data to be sent.
> - TxBufferSize: Total length of the memory space for storing data to be sent. This memory space determines the maximum length of a single response that can be sent.

### Return Value

> - MBX_API_RETURN_DEFAULT(0x00): Normal return.
> - MBX_API_RETURN_MAP_UNFORMAT(0x101): The provided MAP table is not properly formatted.