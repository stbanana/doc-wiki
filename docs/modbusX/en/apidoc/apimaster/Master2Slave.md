---
class: heading_no_counter
draft: false
---

# Initiating Requests to Slave

## **MBx_Master_Read_Coil_Request**

```c
uint32_t MBx_Master_Read_Coil_Request(_MBX_MASTER *pMaster, 
                                      uint8_t      SlaveID,
                                      uint16_t     StartAddr,
                                      uint16_t     ReadNum);
```

 The MBX master issues a read coil request.

### Parameters

> - pMaster: Pointer to the MBX master object that is expected to issue the request.
> - SlaveID: The ID of the slave to be requested.
> - StartAddr: The starting address for reading.
> - ReadNum: The number of coils to read.

### Return Value

> - MBX_API_RETURN_DEFAULT(0x00): Normal return.
> - MBX_API_RETURN_BUFFER_FULL(0x20): Queue is full.
> - MBX_API_RETURN_MAP_UNFIND(0x102): Suitable MAP not found, usually means the slave ID is incorrect or the requested address is not defined in the address mapping table.

------



## **MBx_Master_Read_Disc_Input_Request**

```c
uint32_t MBx_Master_Read_Disc_Input_Request(_MBX_MASTER *pMaster, 
                                            uint8_t      SlaveID,
                                            uint16_t     StartAddr,
                                            uint16_t     ReadNum);
```

 The MBX master issues a read discrete input request.

### Parameters

> - pMaster: Pointer to the MBX master object that is expected to issue the request.
> - SlaveID: The ID of the slave to be requested.
> - StartAddr: The starting address for reading.
> - ReadNum: The number of coils to read.

### Return Value

> - MBX_API_RETURN_DEFAULT(0x00): Normal return.
> - MBX_API_RETURN_BUFFER_FULL(0x20): Queue is full.
> - MBX_API_RETURN_MAP_UNFIND(0x102): Suitable MAP not found, usually means the slave ID is incorrect or the requested address is not defined in the address mapping table.

------



## **MBx_Master_Read_Reg_Request**

```c
uint32_t MBx_Master_Read_Reg_Request(_MBX_MASTER *pMaster, 
                                     uint8_t      SlaveID,
                                     uint16_t     StartAddr,
                                     uint16_t     ReadNum);
```

 The MBX master issues a read holding register request.

### Parameters

> - pMaster: Pointer to the MBX master object that is expected to issue the request.
> - SlaveID: The ID of the slave to be requested.
> - StartAddr: The starting address for reading.
> - ReadNum: The number of coils to read.

### Return Value

> - MBX_API_RETURN_DEFAULT(0x00): Normal return.
> - MBX_API_RETURN_BUFFER_FULL(0x20): Queue is full.
> - MBX_API_RETURN_MAP_UNFIND(0x102): Suitable MAP not found, usually means the slave ID is incorrect or the requested address is not defined in the address mapping table.

------



## **MBx_Master_Read_Input_Reg_Request**

```c
uint32_t MBx_Master_Read_Input_Reg_Request(_MBX_MASTER *pMaster, 
                                           uint8_t      SlaveID,
                                           uint16_t     StartAddr,
                                           uint16_t     ReadNum);
```

 The MBX master issues a read input register request.

### Parameters

> - pMaster: Pointer to the MBX master object that is expected to issue the request.
> - SlaveID: The ID of the slave to be requested.
> - StartAddr: The starting address for reading.
> - ReadNum: The number of coils to read.

### Return Value

> - MBX_API_RETURN_DEFAULT(0x00): Normal return.
> - MBX_API_RETURN_BUFFER_FULL(0x20): Queue is full.
> - MBX_API_RETURN_MAP_UNFIND(0x102): Suitable MAP not found, usually means the slave ID is incorrect or the requested address is not defined in the address mapping table.

------



## **MBx_Master_Write_Coil_Request**

```c
uint32_t MBx_Master_Write_Coil_Request(_MBX_MASTER *pMaster, 
                                       uint8_t      SlaveID,
                                       uint16_t     Addr,
                                       uint16_t     Value);
```

 The MBX master issues a write single coil request.

### Parameters

> - pMaster: Pointer to the MBX master object that is expected to issue the request.
> - SlaveID: The ID of the slave to be requested.
> - Addr: The address to write to.
> - Value: The value to write. For coils, the value is essentially either 0 or greater than 0; the program will automatically handle the formatting of the request.

### Return Value

> - MBX_API_RETURN_DEFAULT(0x00): Normal return.
> - MBX_API_RETURN_BUFFER_FULL(0x20): Queue is full.
> - MBX_API_RETURN_MAP_UNFIND(0x102): Suitable MAP not found, usually means the slave ID is incorrect or the requested address is not defined in the address mapping table.

------



## **MBx_Master_Write_Reg_Request**

```c
uint32_t MBx_Master_Write_Reg_Request(_MBX_MASTER *pMaster,
                                      uint8_t      SlaveID,
                                      uint16_t     Addr,
                                      uint16_t     Value);
```

 The MBX master issues a write single holding register request.

### Parameters

> - pMaster: Pointer to the MBX master object that is expected to issue the request.
> - SlaveID: The ID of the slave to be requested.
> - Addr: The address to write to.
> - Value: The value to write.

### Return Value

> - MBX_API_RETURN_DEFAULT(0x00): Normal return.
> - MBX_API_RETURN_BUFFER_FULL(0x20): Queue is full.
> - MBX_API_RETURN_MAP_UNFIND(0x102): Suitable MAP not found, usually means the slave ID is incorrect or the requested address is not defined in the address mapping table.

------



## **MBx_Master_Write_Coil_Mul_Request**

```c
uint32_t MBx_Master_Write_Coil_Mul_Request(_MBX_MASTER *pMaster,
                                           uint8_t      SlaveID,
                                           uint16_t     StartAddr,
                                           uint16_t     WriteNum,
                                           uint8_t     *Data,
                                           uint16_t     DataLen);
```

 The MBX master issues a write multiple coils request. The parameters Data and DataLen need to be formatted by the user. See the section on"(0x0F)写多个线圈的格式 "for details.
[Introduction to Modbus Protocol](https://www.yono233.cn/posts/shoot/24_7_26_modbus协议介绍(未完成))

### Parameters

> - pMaster: Pointer to the MBX master object that is expected to issue the request.
> - SlaveID: The ID of the slave to be requested.
> - StartAddr: The starting address for writing.
> - WriteNum: The number of coils to write.
> - Data: Pointer to the start of the data to write.
> - DataLen: Length of the data to write [in bytes].

### Return Value

> - MBX_API_RETURN_DEFAULT(0x00): Normal return.
> - MBX_API_RETURN_BUFFER_FULL(0x20): Queue is full.
> - MBX_API_RETURN_MAP_UNFIND(0x102): Suitable MAP not found, usually means the slave ID is incorrect or the requested address is not defined in the address mapping table.

------



## **MBx_Master_Write_Reg_Mul_Request**

```c
uint32_t MBx_Master_Write_Reg_Mul_Request(_MBX_MASTER *pMaster, 
                                          uint8_t      SlaveID,
                                          uint16_t     StartAddr,
                                          uint16_t     WriteNum,
                                          uint8_t     *Data,
                                          uint16_t     DataLen);
```

 The MBX master issues a write multiple holding registers request.

### Parameters

> - pMaster: Pointer to the MBX master object that is expected to issue the request.
> - SlaveID: The ID of the slave to be requested.
> - StartAddr: The starting address for writing.
> - WriteNum: The number of coils to write.
> - Data: Pointer to the start of the data to write.
> - DataLen: Length of the data to write [in bytes].

### Return Value

> - MBX_API_RETURN_DEFAULT(0x00): Normal return.
> - MBX_API_RETURN_BUFFER_FULL(0x20): Queue is full.
> - MBX_API_RETURN_MAP_UNFIND(0x102): Suitable MAP not found, usually means the slave ID is incorrect or the requested address is not defined in the address mapping table.

------

