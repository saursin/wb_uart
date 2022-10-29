# wb_uart


## Register MAP
```
-------+------+--------+--------------------------
Offset | Name | Access | Function
-------+------+--------+--------------------------
0x00   | RBR  | RO     | Recieve Buffer Register
0x04   | TBR  | WO     | Transmit Buffer Register
0x08   | LCR  | RW     | Line Control Register
0x0c   | LSR  | RW     | Line Status Register
0x00   | DIV  | RW     | Divisor Register
-------+------+--------+--------------------------
```

## Register Definitions

```
1. (0x00) Recieve Buffer Register
   ------------------------------
    [31:8]  Reserved
    [7:0]   RX_Data     (0x00)


2. (0x04) Transmit Buffer Register
    ------------------------------
    [31:8]  Reserved
    [7:0]   TX_Data     (0x00)


3. (0x08) Line Control Register
    ------------------------------
    [31:4]  Reserved
    [7]     Divisor Access bit {b0=access RBR & TBR, b1=allow access to DLO & DHI}
    [3]     Parity bits {b0 = Disable, b1 = Enable}
    [2]     Stop bits   {b0=1 bit, b1=2 bits}
    [1:0]   Word length {b00=5, b01=6, b02=7, b03=8}


4. (0x0c) Line Status Register
    ------------------------------
    [31:5]  Reserved
    [4]     TX Done     {1b=Data transmitted}
    [3]     Framing Error
    [2]     Parity Error
    [1]     Overrun Error
    [0]     RX Ready  {1b=Complete incoming character has been recieved into RBR}


5. (0x00) Divisor Register
    ------------------------------
    [31:0]  Div
```