# Continuous Lab Evaluation-5 (Task 5B.5)

**EXP:** Continuous Lab Evaluation-5  
**DATE:** 04/09/2026  
**NAME OF EXP:** Burst Signal Generation with Active and Inactive Intervals on 8051  
**HARDWARE SETUP / PLATFORM:** Keil uVision + AT89S52 Microcontroller + Output Pin on Port 1 Pin 1 (P1.1)  

---

### Circuit Diagram
![Circuit Diagram](FINAL_CAT5B.png)

---

### Core Logic

* **1. State Interval Counter**  
  Timer 1 interrupt partitions signal timing into active oscillatory bursts and idle quiet intervals:
  ```c
  void timer1_ISR(void) interrupt 3 {
      TH1 = 0xFC;
      TL1 = 0x66;

      if(count < 10)
          OUTPUT = ~OUTPUT;  // Active Burst 1
      else if(count < 20)
          OUTPUT = 0;        // Idle Silence Period
      else
          OUTPUT = ~OUTPUT;  // Active Burst 2

      count++;
      if(count >= 30)
          count = 0;
  }
  ```

---

### Inference
Burst signal generation allows testing ultrasonic transmitters, sonar pulses, and packetized carrier wave systems. Timer 1 interrupts successfully governed burst packet envelope and inter-burst spacing.
