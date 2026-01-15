# Secure Speech Communication with Motion-Aware Encryption  
**Simulink-Based Android/iOS Application**

---

## Overview
This repository contains a **Simulink-based mobile application** for secure speech communication between two mobile devices (Phone A and Phone B). The system records audio, applies selectable encryption/authentication techniques, synchronously captures motion sensor data, and transmits all information over **Bluetooth and UDP**. On the receiver side, the signal is decrypted, authenticated, analyzed for quality, and played back.

The project integrates **speech encryption**, **authentication**, **motion–audio synchronization**, and **signal quality assessment**, making it suitable for academic and research use in digital signal processing and mobile embedded systems.

---

## System Architecture

### Transmitter (Phone A)
- Audio recording via mobile microphone  
- Real-time encryption/authentication (UI selectable)  
- Gyroscope and accelerometer data capture with timestamps  
- Bluetooth / UDP transmission of encrypted audio and motion data  

### Receiver (Phone B)
- Bluetooth / UDP reception  
- Decryption and authentication  
- Audio playback (encrypted or decrypted)  
- Motion data visualization/logging  
- Signal quality assessment  

---

## Encryption & Authentication Methods

### Method 1 – Frequency Scrambling with Key-Based Permutation
- Audio converted to frequency domain  
- Key-dependent permutation of frequency bins  
- Produces unintelligible audio without the correct key  
- Fully reversible at the receiver using the same key  

### Method 2 – Noise Masking with Adaptive Noise Shaping
- Adds synthetic noise (white, tonal, or shaped noise)  
- Adaptive noise shaping based on speech spectrum  
- Decryption includes adaptive noise cancellation  

### Method 3 – Speech Watermarking for Authentication
- Embeds an inaudible watermark (spread-spectrum or frequency-hopping)  
- Receiver extracts watermark before decryption  
- UI displays authentication **pass/fail** status  

---

## Motion Sensor Integration
- Gyroscope and accelerometer data captured during audio recording  
- Timestamped motion data synchronized with audio frames  
- Motion data transmitted alongside encrypted audio  
- Enables motion–audio correlation and analysis  

---

## Motion–Audio Synchronization
- Common timing reference for audio and sensor streams  
- Ensures accurate alignment between speech and device motion  
- Supports visualization and post-processing analysis  

---

## Signal Quality Assessment
After decryption, the receiver computes:
- **SNR (Signal-to-Noise Ratio)**  
- **PESQ (Perceptual Evaluation of Speech Quality)** *(simplified implementation)*  

These metrics are displayed in the receiver UI to estimate decrypted audio quality.

---

## User Interface Features

### Phone A (Transmitter)
- Start/stop voice recording  
- Select encryption/authentication method  
- Configure encryption key  
- Enable/disable motion sensing  

### Phone B (Receiver)
- Select playback mode:
  - Play encrypted audio  
  - Play decrypted audio (Method 1 / Method 2 / Method 3)  
- Display watermark verification result  
- View or log motion sensor data  
- Display SNR / PESQ values  

---

## Technologies Used
- MATLAB Simulink  
- Simulink Mobile Support Package  
- DSP System Toolbox  
- Bluetooth and UDP communication blocks  
- Mobile sensors (microphone, gyroscope, accelerometer)  

---


---

## How to Run
1. Install MATLAB with required toolboxes  
2. Install Simulink Mobile Support Package  
3. Deploy the **Transmitter model** to Phone A  
4. Deploy the **Receiver model** to Phone B  
5. Pair devices via Bluetooth or configure UDP IP/port  
6. Select encryption method and key on both devices  
7. Start transmission and observe playback, motion data, and quality metrics  

---

## Applications
- Secure voice communication  
- Motion-aware speech analysis  
- Embedded DSP and Simulink education  
- Encryption and authentication research  

---
