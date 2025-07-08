---
date: 2025-07-07
author: Ian C Mosquera
tags:
  - Documentation
Projects:
  - Metbuoy+
---

# 1	Command and Data Handling "C&DH" Baseboard
## 1.1	Description
The C&DH Baseboard is a docking board for the [[C&DH Primary Board]], mounted via two mezzanine connectors. This board is powered by an Power Control and Distribution Module [[PCDM]], connected via Card Edge Connector, or via USB Type C port. 

This board communicates houses digital isolator and sensor tranlatior devices such as RS232, RS485, SDI, CAN, etc, in which the data are then passed and processed by the attached Primary Board. 

The Baseboard, though has its own MCU (STM32WB55) devices which acts as a supervisory MCU for the Primary Board ensuring that it operates normally. This device is capable of wireless communication to a smartphone or any Bluetooth Low Energy-capable devices. The broadcasted data came from the primary board which are pooled in a desired time interval.

The baseboard communicates with the Primary board via serial uart, two GPIO pins and a watch dog input pin. 

The Baseboard also mounts an AST_designed LTE board and Lora board for added telemetry operation, primarily the LTE. 

This board was made under the arQ Project of DOST-ASTI, which is an upgraded version of the datalogger used on various Weather Sensor deployed through out the Philipppines.

![[Iso View 1.jpg|600]]

# 2	Basic Parameters
## 2.1	MicroController

| **Part**         | STM32WB55CGU6                |
| ---------------- | ---------------------------- |
| **Manufacturer** | ST-Microelectronics          |
| **Core**         | Arm Cortex-M4, Arm Cortex-M0 |
| **Package**      | 48-UFQFPN (7x7) Exposed Pad  |

## 2.2	Internal Memories

| **FLASH** | 1MB   |
| --------- | ----- |
| **SRAM**  | 256kB |
## 2.3	Oscillators

| HSE     | 32MHz     |
| ------- | --------- |
| **LSE** | 32.768KHz |
## 2.4	Power

| Sources       | USB Connector <br> 12V from PCDM |
| ------------- | -------------------------------- |
| **VDD Pins**  | 3.3V                             |
| **VDDA Pins** | 3.3V                             |
| **SMPS**      | 3.3V                             |
## 2.5	Regulator

| Manufacturer | Texas Instruments |
| ------------ | ----------------- |
| **Part**     | TPS62172DSGR      |
| **Package**  | 8-WFDFN           |
| **Input**    | +3V to +17V       |
| **Output**   | +3.3V @ 500mA     |

| Manufacturer | Texas Instruments                                                                                                    |
| ------------ | -------------------------------------------------------------------------------------------------------------------- |
| **Part**     | [[https://www.ti.com/product/TPS63060#tech-docs?HQS=ti-null-null-verifimanuf_df-manu-pf-octopart-wwe\|TPS63060DSCT]] |
| **Package**  | WSON (3x3)                                                                                                           |
| **Input**    | +2.5V to +12V                                                                                                        |
| **Output**   | +3.9V @ 1A                                                                                                           |
## 2.6	PCB

| Color          | Green         |
| -------------- | ------------- |
| **Size (LxW)** | 85.3mm x 60mm |
| **Thickness**  | 1.6mm         |
| **Layer**      | 4 Layers      |


# 3	Terminal Blocks, Connectors and Headers

## 3.1	J2 Terminal Block Pins

| #   | Name | Function | Connected To |
| --- | ---- | -------- | ------------ |
| 1   | AN1  | ADC      | J1.24        |
| 2   | AN2  | ADC      | J1.26        |
## 3.2	J3 Terminal Block Pins

| #   | Name | Function | Connected To |
| --- | ---- | -------- | ------------ |
| 1   | 18V2 | Power    | J8.7         |
| 2   | IN1  | Input    | U6.3         |
| 3   | GND  | Power    | Ground       |
| 4   | 18V1 | Power    | J8.8         |
| 5   | IN2  | Input    | U6.4         |
| 6   | GND  | Ground   | Ground       |
## 3.3	J4 Terminal Block Pins

| #   | Name  | Function      | Connected To |
| --- | ----- | ------------- | ------------ |
| 1   | CANL  | Diff. Pair    | U10.6        |
| 2   | CANH  | Diff. Pair    | U10.7        |
| 3   | GND   | Power         | Ground       |
| 4   | 232TX | Serial Output | J8.8         |
| 5   | 232RX | Serial Input  | U6.4         |
| 6   | GND   | Ground        | Ground       |
- [ ] Other Terminal Blocks and Pins are to be added