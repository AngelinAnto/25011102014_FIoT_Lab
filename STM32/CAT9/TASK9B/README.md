# Continuous Lab Evaluation-9 (Task 9B)

**EXP:** Continuous Lab Evaluation-9  
**DATE:** 16/10/2026  
**NAME OF EXP:** Command-Line Interface (CLI) over USART1 for Peripheral LED Control on STM32  
**HARDWARE SETUP / PLATFORM:** STM32CubeMX + Keil MDK-ARM + STM32F103C8T6 + Onboard LED on PC13 + USB-to-TTL Serial Bridge  

---

### Circuit Diagram
![Circuit Diagram](../CAT9.png)

---

### Core Logic

* **1. Character Stream Buffering & Line Parsing**  
  Received bytes are echoed to the user terminal and accumulated in an internal buffer until a newline (`` or `
`) is encountered.

* **2. String Command Dispatcher**  
  The command string is evaluated to trigger LED modes:
  - `"ON"`: Drives `PC13` LOW to illuminate the onboard LED.
  - `"OFF"`: Drives `PC13` HIGH to turn OFF the LED.
  - `"BLINK"`: Initiates periodic 250 ms toggling:
  ```c
  if (strcmp(rx_buffer, "ON") == 0) {
      led_mode = 1;
  } else if (strcmp(rx_buffer, "OFF") == 0) {
      led_mode = 0;
  } else if (strcmp(rx_buffer, "BLINK") == 0) {
      led_mode = 2;
  }
  ```

---

### Inference
An embedded Command Line Interface was constructed over UART. String parsing enables user control over microcontroller operating modes from a remote terminal.
