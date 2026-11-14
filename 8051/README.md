# 8051 Microcontroller Laboratory Exercises (AT89S52)

This directory contains all laboratory experiments executed on the 8051 (AT89S52) microcontroller architecture using the Keil uVision C51 IDE.

## Experiment Index

| CAT Folder | Task | Description | Core Peripherals / Modules |
|---|---|---|---|
| **CAT2** | `TASK2B` | Basic LED Blinking with Software Delay | Port 1 (P1.0), Software Loops |
| **CAT3** | `TASK3A` | External Interrupt INT0 Button & Multi-Pattern LED Sequencer | INT0 (P3.2), Timer 0 (1 ms Tick), 4 LEDs (P1.0-P1.3) |
| **CAT4** | `TASK4A` | 4x4 Matrix Keypad Scanning & Display Mode Decoding | 4x4 Matrix Keypad (Port 2), LEDs (Port 1) |
| **CAT5** | `TASK5A` | Hardware Timer 0 Mode 1 (16-bit) 1-Second Periodic Delay | Timer 0 (Mode 1), P1.0 LED |
| **CAT5** | `TASK5B.1` | Software Pulse Width Modulation (PWM) Breathing / LED Fading | Timer 0, 100-step Duty Modulation, P1.0 |
| **CAT5** | `TASK5B.2` | Variable Frequency Square Wave Generation | Timer 0, Dynamic TH0/TL0 Reloads, P1.1 |
| **CAT5** | `TASK5B.3` | Variable Duty Cycle Waveform Synthesis | Timer 1 (Mode 1), PWM Comparator, P1.0 |
| **CAT5** | `TASK5B.4` | Asymmetric Pulse Train Generation (1:7 Mark-Space Ratio) | Timer 1, P1.1 Pulse Output |
| **CAT5** | `TASK5B.5` | Burst Signal Generation (Active Oscillation & Quiet Windows) | Timer 1, Envelope Timing, P1.1 |
| **CAT5** | `TASK5C` | Stepper Motor Commutation & Keypad Speed Control | 4x4 Keypad, ULN2003 Driver, Stepper Motor (Port 2) |
| **CAT6** | `TASK6A` | Serial UART String Transmission (9600 Baud) | UART, Timer 1 Mode 2 Auto-Reload, Interrupt 4 |
| **CAT6** | `TASK6B` | Full-Duplex UART Echo Receiver and Transmitter | UART, RI/TI Serial Interrupts, SBUF |
| **CAT7** | `TASK7A` | 16x2 Character LCD Interfacing (4-bit Mode Static Display) | 16x2 HD44780 LCD (Port 2: RS=P2.0, EN=P2.1) |
| **CAT7** | `TASK7B` | Dynamic Integer Counter with In-Place LCD Screen Refresh | 16x2 LCD, In-Place DDRAM Cursor Addressing |
| **CAT7** | `TASK7C` | Interactive Matrix Keypad Character Navigation on LCD | 4x4 Keypad (Port 1), 16x2 LCD (Port 2) |
