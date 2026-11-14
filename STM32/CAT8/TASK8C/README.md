# Continuous Lab Evaluation-8 (Task 8C)

**EXP:** Continuous Lab Evaluation-8  
**DATE:** 09/10/2026  
**NAME OF EXP:** Multi-Action Push Button Handler (Short Press Toggle vs Long Press Blinking) on STM32  
**HARDWARE SETUP / PLATFORM:** STM32CubeMX + Keil MDK-ARM + STM32F103C8T6 (Blue Pill) + Button on PA0 + LED on PA5 + ST-Link V2  

---

### Circuit Diagram
![Circuit Diagram](../CAT8.png)

---

### Core Logic

* **1. Press Duration Measurement Using SysTick**  
  `HAL_GetTick()` records start time on press detection. The elapsed hold time determines the action:
  ```c
  uint32_t press_start = HAL_GetTick();
  while (HAL_GPIO_ReadPin(GPIOA, GPIO_PIN_0) == GPIO_PIN_RESET) {
      if (is_blinking && (HAL_GetTick() - last_blink_time >= 200)) {
          HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_5);
          last_blink_time = HAL_GetTick();
      }
  }
  uint32_t press_duration = HAL_GetTick() - press_start;
  ```

* **2. Dual Mode Action Classifier**  
  - **Short Press (< 1000 ms):** Toggles LED state once.
  - **Long Press (>= 1000 ms):** Enters continuous non-blocking 200 ms blinking mode.

---

### Inference
SysTick time-tracking enables multi-functional input gestures from a single push button, distinguishing between short taps and prolonged holds.
