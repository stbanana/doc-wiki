---
class: heading_no_counter
draft: false
---

# Sending and receiving data series API

## DFlow_Write

### source

```c
uint32_t DFlow_Write(_DFlow *df, 
                    uint8_t *pcBuf, 
                    uint32_t ui32Len
                    );
```

Send a piece of data using a DFlow object. It actually pushes the buffer to be sent and sends it all when the time is right.

### Parameters

> - df：DFlow object to be sent
> - pcBuf：Buffer header of the data expected to be sent
> - ui32Len：Len of the data to be sent

### Return Value

> - DFLOW_API_RETURN_DEFAULT(0x00)：Normal return
> - DFLOW_API_RETURN_BUFFER_FULL(0x20)：Buffer to be sent is full

## DFlow_Writec

### source

```c
uint32_t DFlow_Writec(_DFlow *df, 
                    uint8_t data
                    );
```

Send a byte using some DFlow object. It actually pushes the buffer to be sent and sends it all when the time is right.

### Parameters

> - df：DFlow object to be sent
> - data：Bytes of data expected to be sent

### Return Value

> - DFLOW_API_RETURN_DEFAULT(0x00)：Normal return
> - DFLOW_API_RETURN_BUFFER_FULL(0x20)：Buffer to be sent is full

## DFlow_Getc

### source

```c
uint32_t DFlow_Writec(_DFlow *df, 
                    uint8_t *data_rx
                    );
```

Take a byte from some DFlow object. Actually get the data from the received buffer.

### Parameters

> - df：DFlow object from which the data is expected
> - data_rx：Bytes of data to retrieve

### Return Value

> - DFLOW_API_RETURN_DEFAULT(0x00)：Normal return
> - DFLOW_API_RETURN_BUFFER_EMPTY(0x21)：Buffer to be received is empty