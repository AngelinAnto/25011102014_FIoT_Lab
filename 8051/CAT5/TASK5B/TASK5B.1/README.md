# Continuous Lab Evaluation-5 (Task 5B.1)

**EXP:** Continuous Lab Evaluation-5  
**DATE:** 04/09/2026  
**NAME OF EXP:** Software Pulse Width Modulation (PWM) LED Breathing / Fading on 8051  
**HARDWARE SETUP / PLATFORM:** Keil uVision + AT89S52 Microcontroller + LED on Port 1 Pin 0 (P1.0)  

---

### Circuit Diagram
![Circuit Diagram](FINAL_CAT5B.png)

---

### Core Logic

* **1. High-Frequency Timer 0 Interrupt for PWM Generation**  
  Timer 0 is configured with short reload periods (`TH0 = 0xFF; TL0 = 0xF7;`) to generate rapid timebase slices.

* **2. 100-Step Duty Cycle Modulation**  
  A counter `pwm_count` tracks the current phase. The pin is asserted HIGH when `pwm_count < duty`, and deasserted LOW otherwise:
  ```c
  void timer0_ISR(void) interrupt 1 {
      TH0 = 0xFF;
      TL0 = 0xF7;

      if(pwm_count < duty)
          LED = 1;
      else
          LED = 0;

      pwm_count++;
      if(pwm_count >= 100) {
          pwm_count = 0;
          fade_count++;
          // Ramp duty cycle up and down
      }
  }
  ```

* **3. Bi-Directional Intensity Fading**  
  Every completed PWM cycle updates `duty`, smoothly ramping LED brightness from 0% to 100% and back down to 0% continuously.

---

### Inference
Software-based PWM generation on a microcontroller lacking dedicated hardware PWM channels was demonstrated. Fast periodic timer interrupts successfully modulate average voltage, achieving smooth LED fading.
