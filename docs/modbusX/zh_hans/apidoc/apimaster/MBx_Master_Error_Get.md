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

从 MBX 主机错误队列中获得一个错误，这个错误是接收到的从机错误码。

### 传参

> - pMaster：期望操作的MBX主机对象指针。
> - Func：该错误指令，发送时功能码。
> - Error：实际收到的错误码。
> - AddrStart：该错误指令，发送时操作的起始地址。
> - RegNum：该错误指令，发送时操作的寄存器数量。

### 返回值

> - MBX_API_RETURN_DEFAULT(0x00)：正常返回。
> - MBX_API_RETURN_BUFFER_EMPTY(0x21)：队列为空。
