# **GlucoRoko**

**Proof-of-concept** for a **non-invasive blood glucose monitoring system** based on the principle of **Near-Infrared (NIR) Spectroscopy**. The system aims to provide a painless and real-time method for tracking blood glucose levels, targeting early detection and preventive healthcare.

---

### 🧪 Core Idea  
Users place a finger between an NIR LED and photodiode. The transmitted signal, modulated by the glucose concentration in the blood, is amplified and processed by a microcontroller, which predicts the glucose level using trained regression models.

---

### 🔧 Technical Components Used
- **STM32F411CEU6** – ARM Cortex-M4 Microcontroller for signal processing and prediction.  
- **ESP32** – Wi-Fi module for pushing data to Firebase Cloud.  
- **SI5313-H (IR Transmitter)** and **PT333-3B (IR Receiver)** – For capturing NIR signals.  
- **AD620 Instrumentation Amplifier** – To amplify the weak NIR signal from the receiver.  
- **GlucoRoko Android App** – Fetches real-time glucose data from Firebase and displays history.

---

### 📱 App Features
- Displays real-time blood glucose level.  
- Personalized greeting after entering user's name on first use.  
- Maintains a historical log of previous readings (up to 100 entries).  
- Clean and intuitive UI built using **Node.js** and **Firebase Realtime Database**.

---

### 📡 System Flow Overview
1. **Signal Capture**: Finger placed between emitter and detector.  
2. **Amplification**: Signal passed through AD620.  
3. **Data Processing**: STM32 averages ADC readings and computes glucose level using a pre-trained regression models.  
4. **Cloud Upload**: ESP32 uploads the value to Firebase.  
5. **App Display**: GlucoRoko Android app fetches and displays the latest glucose level.
