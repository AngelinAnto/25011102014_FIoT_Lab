# Continuous Lab Evaluation-10 (Task 10A)

**EXP:** Continuous Lab Evaluation-10  
**DATE:** 23/10/2026  
**NAME OF EXP:** ESP8266 Wi-Fi Module AT Command Handshake & Terminal Relay on STM32  
**HARDWARE SETUP / PLATFORM:** STM32CubeMX + Keil MDK-ARM + STM32F103C8T6 + WeMos ESP8266 (USART3 PB10/PB11) + PC Terminal (USART1 PA9/PA10)  

---

### Circuit Diagram
![Circuit Diagram](../CAT10.png)

---

### Core Logic

* **1. Dual USART Dual-Bridge Configuration**  
  `USART3` communicates with the WeMos ESP8266 Wi-Fi modem, while `USART1` interfaces with the host PC serial terminal.

* **2. AT Command Handshake**  
  STM32 sends `"AT
"` over `USART3` and captures the response (`"OK"`), relaying output to `USART1` for debugging:
  ```c
  char at_cmd[] = "AT
";
  HAL_UART_Transmit(&huart3, (uint8_t *)at_cmd, strlen(at_cmd), 1000);
  HAL_StatusTypeDef status = HAL_UART_Receive(&huart3, rx_buffer, sizeof(rx_buffer) - 1, 2000);
  if (status == HAL_OK || rx_buffer[0] != '\0') {
      HAL_UART_Transmit(&huart1, rx_buffer, strlen((char *)rx_buffer), HAL_MAX_DELAY);
  }
  ```

---

### Inference
Modem communication between the STM32 microcontroller and the ESP8266 Wi-Fi transceiver was established using Hayes AT commands, forming the foundation for IoT network connectivity.
