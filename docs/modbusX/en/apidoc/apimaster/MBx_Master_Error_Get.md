---
class: heading_no_counter
draft: false
---

# MBx_Master_Error_Get

### source
```c
uint32_t MBx_Master_Error_Get(_MBX_MASTER *pMaster, 
                              uint8_t     *Func,
                              uint8_t     *Error,
                              uint16_t    *AddrStart,
                              uint16_t    *RegNum
                             );
```

Get an error from the MBX master error queue. This error corresponds to the error code received from the slave.

### Parameters

> - pMaster: Pointer to the MBX master object that is expected to be operated on.
> - Func: The function code of the error instruction sent.
> - Error: The actual error code received.
> - AddrStart: The starting address operated on by the error instruction sent.
> - RegNum: The number of registers operated on by the error instruction sent.

### Return Value

> - MBX_API_RETURN_DEFAULT(0x00): Normal return.
> - MBX_API_RETURN_BUFFER_EMPTY(0x21): Queue is empty.
