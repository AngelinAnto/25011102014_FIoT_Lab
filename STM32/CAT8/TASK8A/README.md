# Continuous Lab Evaluation-8 (Task 8A)

**EXP:** Continuous Lab Evaluation-8  
**DATE:** 09/10/2026  
**NAME OF EXP:** Direct GPIO Input Polling - Push Button Controlling LED on STM32  
**HARDWARE SETUP / PLATFORM:** STM32CubeMX + Keil MDK-ARM + STM32F103C8T6 (Blue Pill) + User Button on PA0 + LED on PA5 + ST-Link V2  

---

### Circuit Diagram
![Circuit Diagram](../CAT8.png)

---

### Core Logic

* **1. GPIO Pin Configuration via STM32 HAL**  
  `PA0` is configured as a digital input with an internal pull-up resistor. `PA5` is configured as a push-pull digital output.

* **2. Direct Polling Execution Loop**  
  The main loop continuously checks the state of `PA0`. When the button is pressed (Active-LOW: `GPIO_PIN_RESET`), `PA5` is driven HIGH to turn ON the LED:
  ```c
  while (1) {
      if (HAL_GPIO_ReadPin(GPIOA, GPIO_PIN_0) == GPIO_PIN_RESET) {
          HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);   // Turn PA5 LED ON
      } else {
          HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET); // Turn PA5 LED OFF
      }
      HAL_Delay(10);
  }
  ```

---

### Inference
Basic digital input and output capabilities of the STM32 ARM Cortex-M3 architecture were verified. Polling `HAL_GPIO_ReadPin` provides immediate state-matching control of an output LED.
