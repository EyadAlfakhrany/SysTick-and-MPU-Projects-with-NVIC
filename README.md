# TM4C123GH6PM SysTick and MPU Projects with NVIC

## Overview

This repository contains two example projects for the TM4C123GH6PM microcontroller, demonstrating the use of the SysTick timer, MPU (Memory Protection Unit), and NVIC (Nested Vectored Interrupt Controller) priority configuration.

Both projects toggle the LEDs on the TM4C123G LaunchPad board every second using the SysTick timer interrupts, and also show the configuration and handling of memory management faults via the MPU.

---

## Project 1: Basic MPU and SysTick Timer with NVIC Priority Setup

### Description

- Initializes the SysTick timer to generate interrupts every 1 second.
- Toggles Red, Blue, and Green LEDs sequentially on PORTF pins PF1, PF2, and PF3.
- Configures the MPU regions for Flash, SRAM, and GPIO PORTF.
- Sets the SysTick interrupt priority using the NVIC system priority registers.
- Enables memory management fault exception.
- Demonstrates memory protection fault by enabling the clock for PORTF without MPU configuration on the System Control area.

### Features

- SysTick timer interrupt handler to toggle LEDs.
- MPU initialization and region programming.
- NVIC priority assignment for SysTick interrupt.
- Memory Management Fault handler.

---

## Project 2: Enhanced MPU Configuration with Privilege Default Enable and SysTick with NVIC Priority

### Description

- Similar to Project 1 but with MPU configured to enable privilege default access to the background region.
- Uses NVIC to assign priority to SysTick interrupt.
- Enables memory management fault and handles MPU faults.
- Toggles LEDs on PORTF every 1 second using SysTick interrupts.

### Features

- MPU enabled with `PRIVDEFEN` bit for background region privilege access.
- SysTick timer initialization with NVIC interrupt priority configuration.
- Memory Management Fault handler.
- LED control on TM4C123 GPIO PORTF.

---

## Hardware Requirements

- TM4C123GH6PM microcontroller (e.g., TM4C123 LaunchPad)
- LEDs connected on PORTF pins PF1 (Red), PF2 (Blue), PF3 (Green)

---

## Software Requirements

- ARM GCC Compiler or compatible toolchain.
- Debugger or programmer supporting TM4C123 series.
- TM4C123 register definitions header (`tm4c123gh6pm_registers.h`).

---

## How to Build and Run

1. Include `tm4c123gh6pm_registers.h` in your project.
2. Compile the code using your preferred ARM toolchain.
3. Flash the binary to the TM4C123 LaunchPad.
4. Observe the LEDs toggle in sequence every second.
5. The MPU will protect specified memory regions and trigger faults if misconfigured accesses occur.

---

## Notes

- NVIC priority registers are accessed directly to set interrupt priorities.
- MPU faults will cause the system to halt inside the fault handler.
- The MPU configuration ensures memory safety and controlled access to critical regions.
- Project 2 includes privilege default region access enabled, providing more flexibility.

---

## Author

Eyad
