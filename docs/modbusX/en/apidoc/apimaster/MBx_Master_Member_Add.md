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

Add a member slave to the MBX master object.

## Parameters

> - MBxMaster: Pointer to the MBX master object to which the member is expected to be added.
> - MBxMember: Pointer to the slave member object that is expected to be configured and added.
> - SlaveID: The slave ID to be configured for the member.
> - MAP: A pointer to a list ending with the MBX_MAP_LIST_END macro, defining all possible addresses to be configured for the member.

## Return Value

> - MBX_API_RETURN_DEFAULT(0x00): Normal return.
> - MBX_API_RETURN_ERR_PARAM(0x02): Parameter error, check the parameters passed during the call.
> - MBX_API_RETURN_MAP_UNFORMAT(0x101): The provided MAP table is not properly formatted.