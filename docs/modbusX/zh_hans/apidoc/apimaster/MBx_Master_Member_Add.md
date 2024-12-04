---
class: heading_no_counter
draft: false
---

# MBx_Master_Member_Add

### source

```c
uint32_t MBx_Master_Member_Add(_MBX_MASTER               *MBxMaster, 
                               _MBX_MASTER_TEAM_MEMBER   *MBxMember,
                               uint8_t                    SlaveID,
                               const _MBX_MAP_LIST_ENTRY *MAP
                               );
```

向 MBX 主机对象添加一个成员从机

### 传参

> - MBxMaster：期望添加到的MBX主机对象指针
> - MBxMember：期望配置并添加进的从机成员对象指针
> - SlaveID：从机 ID 。将配置给从机成员
> - MAP：该头指针指向以 MBX_MAP_LIST_END 宏为结尾的 list 表。定义所有可能的地址。将配置给从机成员。

### 返回值

> - MBX_API_RETURN_DEFAULT(0x00)：正常返回
> - MBX_API_RETURN_ERR_PARAM(0x02)：传参异常，检查调用时的传参。
> - MBX_API_RETURN_MAP_UNFORMAT(0x101)：传入的MAP表不规范