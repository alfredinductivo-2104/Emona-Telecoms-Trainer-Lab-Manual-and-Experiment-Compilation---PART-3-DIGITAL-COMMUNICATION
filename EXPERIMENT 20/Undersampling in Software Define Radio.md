# UNDERSAMPLING IN SOFTWARE DEFINED RADIO

---

## INTRODUCTION:

In Software-defined radio (SDR), flexibility is achieved by converting incoming radio frequency (RF) signals into digital form and processing them through software rather than fixed hardware circuits. Since SDR systems may need to receive signals at very high carrier frequencies (such as 2.4 GHz in cellular communications), it might seem that the Analog-to-Digital Converter (ADC) must sample at extremely high rates according to the Nyquist criterion. However, this requirement mainly applies to baseband signals.

Most communication signals are bandwidth-limited bandpass signals, meaning their information is confined within a small bandwidth around a high carrier frequency and not near DC. According to Shannon's Information Theorem, all the information in such a signal can be captured by sampling at a rate at least twice its bandwidth—not necessarily twice its highest carrier frequency. This technique is called undersampling, also known as band-pass sampling or super-Nyquist sampling. For example, a 2.4 GHz carrier with a 30 kHz bandwidth can theoretically be sampled at just 60 kHz while still preserving all transmitted information, provided the sampling frequency is carefully chosen to avoid unwanted aliasing.

---

## OBJECTIVES:

In this experiment, we will be using the Emona Telecoms-Trainer 101 to set up a bandwidth limited signal. Then use undersampling in order to demodulate the bandwidth limited signal and recover the signal. Additionally, this experiment will allow the students to effects on the recovered message of mismatches between the modulated carrier bandwidth and the frequency used for undersampling. 

---

## EQUIPMENT TO BE USED:
1. Emona Telecoms-Trainer 101 (plus power-pack)
2. Dual channel 20Mhz Oscilloscope
3. Two Emona Telecoms-Trainer Oscilloscope lead
4. Assorted Emona Telecoms-Trainer 101 patch leads
5. One set of Headphones (stereo)

---

## SUMMARY OF FINDINGS AND RESULTS:

### 1. Setting up a Bandwidth Limited Signal

In this experiment, we will begin by producing a bandwidth-limited signal, which will be used in the next parts of the experiment. In this part of the experiment, any modulation scheme can be used, but for simplicity, we will use a DSBSC signal. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/1f8b7be5-8594-4c1b-b6ee-ef2c02b60299" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/66ba91a9-30c9-4b70-87b3-51e6d6aa4fe7" />

#### 1.1 OBSERVATION

it is observe that the oscilloscope shows the successful generation of a DSBSC (Double Sideband Suppressed Carrier) signal through the multiplication of a 2 kHz message signal and a 100 kHz carrier. The red waveform on Channel 1 represents the original message signal, while the yellow waveform on Channel 2 displays the modulated output. 

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/ead4bbb5-e8a8-4721-ac57-00c726059c85" />

To know more about Bandwidth limited signals proceed to Experiment 14  
[ EXPERIMENT 14/Bandwidth Limiting and Restoring Digital Signal.md)](https://github.com/alfredinductivo-2104/Emona-Telecoms-Trainer-Lab-Manual-and-Experiment-Compilation---PART-3-DIGITAL-COMMUNICATION/blob/645b5ab63a04476e3ead1198147e6e05916bf87b/EXPERIMENT%2014/Bandwidth%20Limiting%20and%20Restoring%20Digital%20Signal.md)

### 2. Direct Down-Conversion using Undersampling

In the next part of the experiment, we will be able to demodulate the constructed bandwidth limited signal in the previous part to recover the 2 KHz message using undersampling instead of using product detector which is used in the previous experiments. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/e60d41dd-3350-439e-9116-952ae4865b4d" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/53de9e37-a9ae-498a-89eb-9eab61a57753" />

#### 2.1 OBSERVATION

It is observed that the captured direct down-conversion via undersampling reveals a distinct staircase-shaped waveform on Channel 2 (yellow waveform), which represents the output of the Sample and Hold (S/H) block. While the red waveform on Channel 1 confirms the original 2.083 kHz message signal, the yellow waveform demonstrates how the high-frequency DSBSC signal is translated to a lower frequency by sampling it at a rate of 8 kHz.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/ff2a4fbf-6f07-4be6-8b84-387778f89142" />

### 3. Direct Down-Conversion using Undersampling w/ VCO

After obtaining the output produced from direct down-conversion using undersampling with an 8 kHz digital signal, we will replace this signal with a digital signal from the VCO module of the ETT-101. This will more likely make the VCO module’s output exactly the correct frequency for successful demodulation. Refer to the connection shown in the figure below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/c6ad2057-7107-43aa-aa3f-ece55079a50f" />

#### 3.1 OBSERVATION

It is observe that by replacing the fixed 8 kHz clock with the VCO digital output transforms the down-conversion process into a tunable system where the sampling rate is no longer static. In the oscilloscope Channel 1 (red waveform), it  consistently monitors the 2.083 kHz message signal, while Channel 2 (yellow waveform) displays the result of the Sample and Hold (S/H) block driven by the VCO. The yellow waveform is  appears as a dense, modulated pulse train with a measured frequency of 58.74 kHz, indicating that the VCO is sampling the 100 kHz carrier at a rate that produces a specific high-frequency alias. While on the other hand, the output on Channel 2 retains its characteristic staircase-like texture, but the density and width of these sampling steps are now governed by the VCO's frequency settings rather than a fixed digital signal. 

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/34156aab-6a7d-44f8-a5f0-0dd4f30e0fa3" />

---

## LAB QUESTIONS AND ANSWERS:

**Q1: For the given inputs to the Multiplier module, what are the frequencies of the two sinewaves that makes up the DSBSC signal?**

2 Khz sine wave and 100 Khz sine wave makes up the DSBSC signal

**Q2: What's the bandwidth of the DSBSC signal?**  

The bandwidth of a DSBSC signal is equal to twice the message frequency (2fm). Since the message signal is 2 kHz, the bandwidth is approximately 4 kHz. This bandwidth represents the frequency span between the lower and upper sidebands.

**Q3: What significance of the signal on the Baseband LPF output?**  

The signal at the Baseband LPF output is significant because it represents the recovered message signal after undersampling. The low-pass filter removes the higher-frequency alias components generated during the sampling process and allows only the baseband component to pass. This confirms that undersampling effectively performs the demodulation process by shifting the modulated signal down to baseband.

**Q4: Given the sampling frequency of 8.333 KHz (the signal's specified value of 8 KHz is rounded down for simplicity), which harmonic in the sampling signal is demodulating the DSBSC signal?**  

Given the sampling frequency of 8.333 kHz, the harmonic of the sampling signal that demodulates the DSBSC signal is the one closest to the 100 kHz carrier frequency. Dividing 100 kHz by 8.333 kHz gives approximately 12, meaning the 12th harmonic of the sampling frequency (around 100 kHz) acts as the effective mixing frequency. This harmonic causes the carrier signal to alias down to baseband, enabling demodulation.

**Q5: Why doesn't this solve the problem and allow the demodulator to recover message?**  

This method does not completely solve the problem because successful demodulation depends on precise alignment between the sampling frequency and the carrier frequency. Even a small frequency mismatch can cause distortion or incomplete recovery of the message.

---

## CONCLUSIONS:
After analyzing the gathered data and observations about Undersampling in Software Define Radio, the following conclusions have been made:
- Undersampling allows high-frequency bandpass signals to be sampled at rates much lower than twice the carrier frequency.
- The experiment demonstrated that a 100 kHz DSBSC signal can be effectively demodulated using an 8 kHz sampling signal.
- The sampling process produces aliasing, which shifts the signal spectrum to baseband, effectively performing direct down-conversion.
- The Baseband LPF plays a crucial role in recovering the original 2 kHz message by filtering out unwanted high-frequency components.
- The harmonic relationship between the sampling frequency and the carrier frequency determines successful demodulation.
- Replacing the fixed digital clock with a VCO makes the system tunable and improves frequency alignment for accurate signal recovery.
