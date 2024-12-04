---
class: heading_no_counter
draft: false
---


# MBx_Ticks

### source
```c
void MBx_Ticks(
               uint32_t Cycle
              );
```

This function must be called periodically and is a key function that drives the modbusX system. Both the master and slave are driven by this unique library tick.

### Parameters

> - Cycle：The period value in microseconds (us) for calling this function.

### Return Value

> No return value.
