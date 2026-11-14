# Continuous Lab Evaluation-12 (Task 12B)

**EXP:** Continuous Lab Evaluation-12  
**DATE:** 06/11/2026  
**NAME OF EXP:** STM32 Nucleo User Push Button (PC13) Debounced LED Toggle  
**HARDWARE SETUP / PLATFORM:** STM32CubeMX + Keil MDK-ARM + STM32 Nucleo-F401RE / F411RE + Blue User Button (PC13) + LED (PA5)  

---

### Circuit Diagram
![Circuit Diagram](../CAT12.png)

---

### Core Logic

* **1. Nucleo User Button Debouncing (PC13)**  
  Onboard blue push button `PC13` is polled. Contact noise is debounced with 50 ms delay:
  ```c
  if (HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_13) == GPIO_PIN_RESET) {
      HAL_Delay(50);
      if (HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_13) == GPIO_PIN_RESET) {
          HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_5);
          while (HAL_GPIO_ReadPin(GPIOC, GPIO_PIN_13) == GPIO_PIN_RESET);
      }
  }
  ```

---

### Inference
User button handling and contact debouncing were validated on the STM32 Nucleo board, ensuring reliable toggle transitions on `PA5`.
