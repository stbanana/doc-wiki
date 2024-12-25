---
class: heading_no_counter
draft: false
---

# DFlow_Ticks

### source

```c
void DFlow_Ticks(
               _DFlow *df
              );
```

The key functions that drive the Dataflow system must be called periodically. Only drive the incoming DFlow object, it is recommended to call once in 1ms, but it can also be called in a shorter period, which will slightly increase the CPU consumption and slightly reduce the delay of channel switching.

### Parameters

> - df：Expectation driven DFlow objects

### Return Value

> No return value.