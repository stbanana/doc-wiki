---
class: heading_no_counter
draft: false
---

# 对从机发起请求 系列API



## **MBx_Master_Read_Coil_Request**

```c
uint32_t MBx_Master_Read_Coil_Request(_MBX_MASTER *pMaster, 
                                      uint8_t      SlaveID,
                                      uint16_t     StartAddr,
                                      uint16_t     ReadNum);
```

 MBX 主机发出一条读线圈请求

### 传参

> - MBxMaster：期望发出请求的MBX主机对象指针。
> - SlaveID：期望请求的从机号。
> - StartAddr：读取起始地址。
> - ReadNum：读取数量。

### 返回值

> - MBX_API_RETURN_DEFAULT(0x00)：正常返回。
> - MBX_API_RETURN_BUFFER_FULL(0x20)：队列已满。
> - MBX_API_RETURN_MAP_UNFIND(0x102)：未查找到合适的MAP，通常意味着从机号错误、或请求地址在地址映射表中未定义。

------



## **MBx_Master_Read_Disc_Input_Request**

```c
uint32_t MBx_Master_Read_Disc_Input_Request(_MBX_MASTER *pMaster, 
                                            uint8_t      SlaveID,
                                            uint16_t     StartAddr,
                                            uint16_t     ReadNum);
```

 MBX 主机发出一条读离散输入请求

### 传参

> - MBxMaster：期望发出请求的MBX主机对象指针。
> - SlaveID：期望请求的从机号。
> - StartAddr：读取起始地址。
> - ReadNum：读取数量。

### 返回值

> - MBX_API_RETURN_DEFAULT(0x00)：正常返回。
> - MBX_API_RETURN_BUFFER_FULL(0x20)：队列已满。
> - MBX_API_RETURN_MAP_UNFIND(0x102)：未查找到合适的MAP，通常意味着从机号错误、或请求地址在地址映射表中未定义。

------



## **MBx_Master_Read_Reg_Request**

```c
uint32_t MBx_Master_Read_Reg_Request(_MBX_MASTER *pMaster, 
                                     uint8_t      SlaveID,
                                     uint16_t     StartAddr,
                                     uint16_t     ReadNum);
```

 MBX 主机发出一条读保持寄存器请求

### 传参

> - MBxMaster：期望发出请求的MBX主机对象指针。
> - SlaveID：期望请求的从机号。
> - StartAddr：读取起始地址。
> - ReadNum：读取数量。

### 返回值

> - MBX_API_RETURN_DEFAULT(0x00)：正常返回。
> - MBX_API_RETURN_BUFFER_FULL(0x20)：队列已满。
> - MBX_API_RETURN_MAP_UNFIND(0x102)：未查找到合适的MAP，通常意味着从机号错误、或请求地址在地址映射表中未定义。

------



## **MBx_Master_Read_Input_Reg_Request**

```c
uint32_t MBx_Master_Read_Input_Reg_Request(_MBX_MASTER *pMaster, 
                                           uint8_t      SlaveID,
                                           uint16_t     StartAddr,
                                           uint16_t     ReadNum);
```

 MBX 主机发出一条读输入寄存器请求

### 传参

> - MBxMaster：期望发出请求的MBX主机对象指针。
> - SlaveID：期望请求的从机号。
> - StartAddr：读取起始地址。
> - ReadNum：读取数量。

### 返回值

> - MBX_API_RETURN_DEFAULT(0x00)：正常返回。
> - MBX_API_RETURN_BUFFER_FULL(0x20)：队列已满。
> - MBX_API_RETURN_MAP_UNFIND(0x102)：未查找到合适的MAP，通常意味着从机号错误、或请求地址在地址映射表中未定义。

------



## **MBx_Master_Write_Coil_Request**

```c
uint32_t MBx_Master_Write_Coil_Request(_MBX_MASTER *pMaster, 
                                       uint8_t      SlaveID,
                                       uint16_t     Addr,
                                       uint16_t     Value);
```

 MBX 主机发出一条写单个线圈请求

### 传参

> - MBxMaster：期望发出请求的MBX主机对象指针。
> - SlaveID：期望请求的从机号。
> - Addr：写入地址。
> - Value：写入值。写入线圈，本质上只有0与大于0，程序会自动处理格式化请求。

### 返回值

> - MBX_API_RETURN_DEFAULT(0x00)：正常返回。
> - MBX_API_RETURN_BUFFER_FULL(0x20)：队列已满。
> - MBX_API_RETURN_MAP_UNFIND(0x102)：未查找到合适的MAP，通常意味着从机号错误、或请求地址在地址映射表中未定义。

------



## **MBx_Master_Write_Reg_Request**

```c
uint32_t MBx_Master_Write_Reg_Request(_MBX_MASTER *pMaster,
                                      uint8_t      SlaveID,
                                      uint16_t     Addr,
                                      uint16_t     Value);
```

 MBX 主机发出一条写单个保持寄存器请求

### 传参

> - MBxMaster：期望发出请求的MBX主机对象指针。
> - SlaveID：期望请求的从机号。
> - Addr：写入地址。
> - Value：写入值。

### 返回值

> - MBX_API_RETURN_DEFAULT(0x00)：正常返回。
> - MBX_API_RETURN_BUFFER_FULL(0x20)：队列已满。
> - MBX_API_RETURN_MAP_UNFIND(0x102)：未查找到合适的MAP，通常意味着从机号错误、或请求地址在地址映射表中未定义。

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

 MBX 主机发出一条写多个线圈请求 ，Data、DataLen传参需要自行格式化 见其中关于"(0x0F)写多个线圈的格式 "
[modbus协议介绍 ](https://www.yono233.cn/posts/shoot/24_7_26_modbus协议介绍(未完成))

### 传参

> - MBxMaster：期望发出请求的MBX主机对象指针。
> - SlaveID：期望请求的从机号。
> - StartAddr：写入起始地址。
> - WriteNum：写入数量。
> - Data：写入数据起始指针。
> - DataLen：写入数据长度[字节数]。

### 返回值

> - MBX_API_RETURN_DEFAULT(0x00)：正常返回。
> - MBX_API_RETURN_BUFFER_FULL(0x20)：队列已满。
> - MBX_API_RETURN_MAP_UNFIND(0x102)：未查找到合适的MAP，通常意味着从机号错误、或请求地址在地址映射表中未定义。

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

 MBX 主机发出一条写多个保持寄存器请求

### 传参

> - MBxMaster：期望发出请求的MBX主机对象指针。
> - SlaveID：期望请求的从机号。
> - StartAddr：写入起始地址。
> - WriteNum：写入数量。
> - Data：写入数据起始指针。
> - DataLen：写入数据长度[字节数]。

### 返回值

> - MBX_API_RETURN_DEFAULT(0x00)：正常返回。
> - MBX_API_RETURN_BUFFER_FULL(0x20)：队列已满。
> - MBX_API_RETURN_MAP_UNFIND(0x102)：未查找到合适的MAP，通常意味着从机号错误、或请求地址在地址映射表中未定义。

------

