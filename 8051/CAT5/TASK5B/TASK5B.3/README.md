# Continuous Lab Evaluation-5 (Task 5B.3)

**EXP:** Continuous Lab Evaluation-5  
**DATE:** 04/09/2026  
**NAME OF EXP:** Variable Duty Cycle Waveform Synthesis Using Timer 1  
**HARDWARE SETUP / PLATFORM:** Keil uVision + AT89S52 Microcontroller + Output Pin on Port 1 Pin 0 (P1.0)  

---

### Circuit Diagram
![Circuit Diagram](FINAL_CAT5B.png)

---

### Core Logic

* **1. Timer 1 Timebase Generation**  
  Timer 1 is configured in Mode 1 (16-bit) to produce rapid periodic interrupts (`interrupt 3`), updating a 100-step cycle counter `pwm_count`.

* **2. Configurable Duty Ratio Comparator**  
  ```c
  void timer1_ISR(void) interrupt 3 {
      TH1 = 0xFF;
      TL1 = 0xF7;

      if(pwm_count < duty)
          LED = 1;
      else
          LED = 0;

      pwm_count++;
      if(pwm_count >= 100)
          pwm_count = 0;
  }
  ```

---

### Inference
Generating signals with non-symmetric duty cycles enables precise power regulation and speed control in embedded systems. Timer 1 successfully implemented selectable duty cycle waveform synthesis.
