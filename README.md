# Reflow Oven Controller – PIC18F458 & MAX6675 (Simulation Project)

This repository contains the source code for a simulated reflow oven controller developed using the **PIC18F458** microcontroller and the **MAX6675** digital thermocouple sensor. The system replicates a four-phase industrial reflow soldering profile using time-based interrupts, proportional PWM control, and real-time UART data transmission. Developed as part of the *Microprocessor Systems* course.

---

## 🔧 Key Features

- 48-step reflow temperature-time profile (Preheat, Soak, Reflow, Cooling)
- Timer0-based 5-second interrupt system for periodic control
- Proportional control algorithm for PWM duty cycle calculation
- PWM signal generation using CCP1 module
- Conditional actuator control logic (heater/fan)
- UART communication for real-time data output
- Fully simulated in Proteus (hardware-independent)

---

## 🧠 System Architecture

- **Microcontroller**: PIC18F458 (8 MHz crystal)
- **Temperature Sensor**: MAX6675 (SPI, bit-banged)
- **Interrupt Module**: Timer0 (5s interval)
- **PWM Generator**: CCP1 module
- **UART Interface**: 9600 baud for PC communication
- **Control Logic**: Proportional control with switching logic

---

## 🔄 Workflow Summary

1. Timer0 interrupt triggers every 5 seconds.
2. Current temperature is read via MAX6675.
3. Target temperature is selected from the profile array.
4. Proportional control calculates the PWM duty cycle.
5. Depending on temperature error, heater or fan logic is enabled.
6. Temperature and time data are sent to PC via UART.
7. System continues until the profile is completed.

---

## 📤 UART Output Format

The system transmits temperature readings in the following format:

```

Time: \<elapsed\_time>, Temp: \<measured\_temp>

```

This output can be visualized on a PC using Python and Matplotlib.

---


## 📈 How to Simulate

1. Open the code in MPLAB X or any compatible IDE.
2. Build the project and generate a `.hex` file.
3. Load the `.hex` into Proteus with:
   - PIC18F458
   - MAX6675 sensor
   - UART terminal
4. Monitor UART data for temperature-time behavior.

---

## 🚀 Future Enhancements

- PID control for smoother transitions
- Onboard LCD or GUI display
- Data logging functionality
- Custom profile support
- Real hardware deployment

---


---

## 🔖 Tags

`PIC18F458` `Embedded Systems` `PWM Control` `UART` `MAX6675` `Temperature Regulation` `Reflow Oven` `Simulation` `Proteus` `Microcontroller` `C Programming`

