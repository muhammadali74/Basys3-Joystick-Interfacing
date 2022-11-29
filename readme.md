# Basys3 Joystick Interfacing using XADC

This project demonstrates how to interface a **non-PMOD analog joystick module** with the **Basys3 FPGA** using its built-in **XADC (Analog-to-Digital Converter)**.  
It safely reads the joystick’s **X and Y axis** voltages and converts them into digital signals for FPGA-based applications such as games or robotic control.

---

## Overview

The Basys3 board features a dual 12-bit, 1 MSPS XADC capable of reading analog voltages between **0–1V**.  
Since standard joysticks output 0–5V, a **voltage divider** is used to bring the signal to a safe input range.

The joystick contains two potentiometers (VRx, VRy). Because the XADC can sample only **one channel at a time**, a **multiplexer** is used to rapidly switch between the two input channels.

---

## Hardware Requirements

- Basys3 FPGA  
- Analog Joystick Module (4-pin)  
- Resistors: **15kΩ** and **680Ω** (for voltage divider)  
- Breadboard & jumper wires  
- (Optional) Logic analyzer / oscilloscope for debugging  

---

## Circuit Summary

- Joystick outputs → voltage divider → Basys3 XADC PMOD (JXADC)  
- Unipolar configuration (negative pins grounded)  
- XADC samples VRx and VRy separately  
- Multiplexer selects input channel at high frequency  

A detailed diagram is included in the PDF report.

---

## How the Code Works

- The XADC module continuously samples one analog input at a time.  
- A multiplexer selects between VRx and VRy.  
- The XADC output `data` (16-bit) is used as joystick position.  
- These digital values can be fed into a game engine, servo driver, or any custom logic.

---

## Documentation

Brief Guide:   
**Interfacing Joystick Using Basys3 XADC** (included in repo)

---


## References

- Basys3 Reference Manual  
- Xilinx 7-Series XADC User Guide  
- Digilent Basys3 repositories  
- https://github.com/Digilent/Basys3
---

## 📣 Contributions

Feel free to open issues or submit PRs to improve the code or documentation.

---

