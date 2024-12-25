---
update:
  - date: 2024-12-25
    author: yono
    version: 0.1.0
    content: Basic
update_open: true
---

This library is intended to complement the practical aspects of [modbusX](/modbusX/en/) ， assist in the development of peripheral drivers.

The total time is about 5 hours, and there are still many shortcomings.

# Effects

Hope to help those who can not manage the following two small white, conform to any one can use this library to solve.

> DMA of the transport stream.
>
> Half-duplex usage of transport streams.

A typical application scenario is the serial port RS485 communication.

# Side effects

>**Latency**: Introduces an additional 1-2ms delay between sending and receiving data, mainly to ensure the stability of switching half-duplex directions.
>
>**Resources**: Doubles RAM space consumption.