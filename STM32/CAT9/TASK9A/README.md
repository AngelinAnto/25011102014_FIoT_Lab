# Continuous Lab Evaluation-9 (Task 9A)

**EXP:** Continuous Lab Evaluation-9  
**DATE:** 16/10/2026  
**NAME OF EXP:** USART1 Serial Polling Echo and Periodic Heartbeat Telemetry on STM32  
**HARDWARE SETUP / PLATFORM:** STM32CubeMX + Keil MDK-ARM + STM32F103C8T6 + USB-to-TTL Adapter (PA9 TX, PA10 RX) + PuTTY Terminal  

---

### Circuit Diagram
![Circuit Diagram](../CAT9.png)

---

### Core Logic

* **1. USART1 Hardware Initialization**  
  USART1 is initialized to 115200 baud, 8 data bits, 1 stop bit, no parity (`115200 8-N-1`).

* **2. Polling Reception with Instant Echo**  
  Non-blocking reception inspects incoming characters and echoes them back to the terminal:
  ```c
  if (HAL_UART_Receive(&huart1, &rx_data, 1, 10) == HAL_OK) {
      HAL_UART_Transmit(&huart1, &rx_data, 1, 100);
  }
  ```

* **3. Periodic Telemetry Heartbeat**  
  Every 3 seconds (`HAL_GetTick() - last_tx_time >= 3000`), the microcontroller transmits heartbeat character `'X'`.

---

### Inference
Serial communication using STM32 HAL UART drivers was verified. Polling reception combined with SysTick-based scheduling enables simultaneous echo response and periodic heartbeat transmission.
