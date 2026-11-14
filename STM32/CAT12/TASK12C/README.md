# Continuous Lab Evaluation-12 (Task 12C)

**EXP:** Continuous Lab Evaluation-12  
**DATE:** 06/11/2026  
**NAME OF EXP:** STM32 Nucleo Dual-Mode Push Button (Short Press Toggle vs Long Press Blinking)  
**HARDWARE SETUP / PLATFORM:** STM32CubeMX + Keil MDK-ARM + STM32 Nucleo Board + User Button (PC13) + User LED (PA5)  

---

### Circuit Diagram
![Circuit Diagram](../CAT12.png)

---

### Core Logic

* **1. Hold Duration Timing on Nucleo PC13**  
  Samples duration between button press and release using SysTick timer ticks.

* **2. Multi-Mode Output Action**  
  - Press < 1000 ms: Single toggle of `PA5`.
  - Press >= 1000 ms: Switches into rapid 200 ms blinking mode:
  ```c
  uint32_t press_duration = HAL_GetTick() - press_start;
  if (press_duration >= 1000) {
      blinking_mode = 1;
  } else {
      blinking_mode = 0;
      HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_5);
  }
  ```

---

### Inference
Demonstrated multi-gesture input handling on the STM32 Nucleo board, discriminating between momentary clicks and continuous holds to trigger distinct system modes.
