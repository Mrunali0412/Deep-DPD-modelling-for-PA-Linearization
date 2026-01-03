

# ⚡ Deep Learning for Power Amplifier Linearization 🛰️

A project focused on **modeling Power Amplifiers (PA)** and training **neural network–based Digital Pre-Distorters (DPD)** for linearization. This project demonstrates how deep learning architectures can improve PA performance while considering memory effects and nonlinearity.

---

## 📝 Problem Statement

* Power Amplifiers exhibit **non-linearities near saturation** ⚡
* **Digital Pre-Distorter (DPD)** is used to compensate these non-linearities
* **Neural network–based DPDs** adapt to changing PA characteristics, but training is time- and resource-intensive ⏱️
* **Goal:** Create a **NN-based PA model** to simulate real PA behavior and train DPDs efficiently

---

## 🏗️ NN-PA Model Architecture

* **Neural Network–Based Power Amplifier (NN-PA)** acts as a **data-driven surrogate** for physical PA
* Input: **I/Q samples + delayed memory taps** 🔄
* Output: **Distorted I/Q samples** learning **AM-AM and AM-PM nonlinearities**
* Trained with **supervised learning** on input-output PA data
* NN-PA is **kept fixed** for fair comparison of DPD architectures

---

## 🤖 DPD Architectures Evaluated

Tested on the fixed NN-PA model:

| Model               | NMSE Improvement | EVM Improvement | ACPR Improvement | Notes                                                  |
| ------------------- | ---------------- | --------------- | ---------------- | ------------------------------------------------------ |
| **Feed Forward NN** | 14.06 dB         | 21.29 %         | -7.13 dB         | Best for **low-memory PAs**                            |
| **RNN**             | 10.50 dB         | 18.00 %         | -11.22 dB        | Good for **moderate memory PAs**                       |
| **LSTM**            | 18.59 dB         | 23.58 %         | -5.34 dB         | Handles **long-term memory**; high complexity          |
| **GRU**             | 20.19 dB         | 24.08 %         | -4.87 dB         | Best overall **trade-off**; practical for real systems |

---

## 📊 Key Insights

* **Feed Forward DPD:** effective for low-memory PAs but fails with strong memory effects
* **Recurrent architectures (RNN, LSTM, GRU):** explicitly model PA memory, outperform feedforward models
* **GRU-based DPD:** best balance of performance, training stability, and moderate complexity ✅
* **LSTM:** comparable to GRU but higher computational cost

---

## 💻 Skills & Tools

* **Deep Learning Architectures:** Feed Forward, RNN, LSTM, GRU 🧠
* **PyTorch Framework** 🐍
* **Signal Processing & PA Modeling** 📡
* Performance Metrics: **NMSE, EVM, ACPR** 📊

---

## ⚡ Conclusion

* Deep learning–based DPD significantly improves PA linearity for 16-QAM signals
* **Architecture selection** should consider PA memory characteristics and system constraints
* GRU provides a **practical and robust solution** for real-world transmitters


Check out the ppt here:
Check out project report here:
