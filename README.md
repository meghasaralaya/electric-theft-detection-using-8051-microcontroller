# Electric-Theft-Detection-using-8051-Microcontroller
A microcontroller-based system that detects electricity theft by monitoring abnormal current differences acroos distribution points in real time. The system monitors energy flow between the power distribution line and the consumer meter using two current transformers (CTs)/ current sensors placed before and after the meter. The analog signal is converted to digital signal with the help of an ADC, through which the converted digital signal is sent to the microcontroller. The microcontroller continuously compares the input and output readings, and if discrepancies are detected indicating unauthorized usage through illegal tapping or meter tampering it immediately triggers an alert using a buzzer.

# What It Does
- Continuously monitors current at two points using ACS712 Hall-effect sensors.
- Reads analog sensor output via ADC0808 and feeds it to the 8051.
- Compares current values and triggers an alert if the difference exceeds a threshold.
- Displays real-time readings on an LCD and sounds a buzzer on anomaly detection.

# Technical Highlights
- Microcontroller: Intel 8051
- Language: Embedded C (Keil uVision)
- Simulation: Proteus 8
- Current Sensor: ACS712 (±30A variant)
- ADC: ADC0808 (8-channel, 8-bit)
- Output: 16x2 LCD + Buzzer

# How the Detection Works
ACS712 sensors output a voltage proportional to current (2.5V baseline, ±sensitivity).
ADC0808 converts both analog readings to 8-bit digital values.
8051 reads both values and computes the difference.
If `|I1 - I2| > THRESHOLD`, the system triggers buzzer and displays "THEFT DETECTED".
Normal readings display both current values continuously on LCD.

# Validation
- Full circuit simulated in Proteus 8 with virtual ACS712 and ADC models.
- Tested with varying input voltages to simulate different current scenarios.
- Verified LCD output and buzzer response for both normal and anomaly conditions.
