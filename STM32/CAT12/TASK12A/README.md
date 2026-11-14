# Continuous Lab Evaluation-12 (Task 12A)

**EXP:** Continuous Lab Evaluation-12  
**DATE:** 06/11/2026  
**NAME OF EXP:** STM32 Nucleo Board Onboard User LED (PA5) Blinking via HAL Delay  
**HARDWARE SETUP / PLATFORM:** STM32CubeMX + Keil MDK-ARM + STM32 Nucleo-F401RE / F411RE + Onboard Green LED (PA5)  

---

### Circuit Diagram
![Circuit Diagram](../CAT12.png)

---

### Core Logic

* **1. Nucleo Clock & Peripheral Initialization**  
  Clock tree is configured with HSE bypass, driving the ARM Cortex-M4 core. `PA5` is configured as a push-pull output.

* **2. Periodic State Toggling**  
  ```c
  while (1) {
      HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_5);
      HAL_Delay(500);
  }
  ```

---

### Inference
Basic operation of the STM32 Nucleo ARM Cortex-M4 development platform was verified, blinking the onboard User LED at 1 Hz using `HAL_GPIO_TogglePin`.
