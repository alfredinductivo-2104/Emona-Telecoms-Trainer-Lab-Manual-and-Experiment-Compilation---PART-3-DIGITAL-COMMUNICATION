# BINARY PHASE SHIFT KEYING (BPSK)

---

## INTRODUCTION:

Binary Phase Shift Keying (BPSK) is a digital modulation technique commonly used in digital communication systems and frequency division multiplexing (FDM) environments. In BPSK, digital information is transmitted by shifting the phase of a carrier signal between two discrete values, typically 0° and 180°, to represent logic 1 and logic 0. Unlike amplitude and frequency-based modulation schemes, the carrier’s amplitude and frequency remain constant while only the phase changes. One of the key advantages of BPSK is its strong immunity to noise, making it one of the most robust digital modulation techniques. Since information is encoded in the phase of the carrier, BPSK performs well in noisy channels and requires relatively low signal power for reliable transmission.

---

## OBJECTIVES:

In this experiment, we will be able to use the ETT-101 Trainer to generate a BPSK signal using the Multiplier module to implement its mathematical model. Additionally, we will be able to understand the restoration process of a BPSK signal using another Multiplier Module or Comparator.

---

## EQUIPMENT TO BE USED:
1. Emona Telecoms-Trainer 101 (plus power-pack)
2. Dual channel 20Mhz Oscilloscope
3. Two Emona Telecoms-Trainer Oscilloscope lead
4. Assorted Emona Telecoms-Trainer 101 patch leads
5. One set of Headphones (stereo)

---

## SUMMARY OF FINDINGS AND RESULTS:

### 1. Generating an BPSK Signal 

In the frst part of the experiment, we will be generating a BPSK signal using its mathematical model. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/64d85d65-ea3c-474b-a532-c9dd74498c58" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/5aca9864-0338-4ba0-acde-3d9839961112" />

#### 1.1 OBSERVATION

As observed in the gathered output that the oscilloscope displays two distinct signals used to generate Binary Phase Shift Keying (BPSK). The top waveform (red waveform) represents the digital message signal from the Sequence Generator, showing a clear pulse train that acts as the data input. The bottom waveform (yellow waveform) shows the modulated BPSK signal, where the phase of the 100 kHz carrier shifts by 180 degrees whenever the digital input changes state.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/cd56b007-24c2-4359-9e1e-acc28748c800" />

### 2. Demodulating an BPSK Signal using a Product Detector

In this part of the experimennt, as we know that BPSK is just really a DSBSC, it can be recovered using any of the DSBSC demodulation Scheme. Which in this case, we will be using the Product Detector scheme to demodulate the given BPSK signal. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/389d3787-9698-475f-9952-82428635e06b" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/f24896d5-e9e9-4649-9593-660aea8c7db8" />

#### 2.1 OBSERVATION

As observed in the gathered output that the oscilloscope captures the successful recovery of the original message through product detection. The top waveform (red) represents the original digital signal before modulation, while the bottom waveform (yellow) is the demodulated BPSK signal obtained after passing the product of the BPSK signal and the "stolen" carrier through the tuneable low-pass filter. The yellow waveform output signal closely follows the logic levels of the original red waveform signal, though it exhibits rounded edges and slight "ringing" or ripples.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/515f8251-7680-488f-84b3-9d5db275d6fe" />

### 3. Restoring the Recovered Data using a Comparator

In the next part of the experiment, using a comparator, we will be able to clean up the demodulated BPSK signal from the previous part of the experiment. This will allow us to understand the importance of Comparator circuit when it comes to restoring distorted digital signal. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/bb7dd390-00f1-41d6-8a4e-fd4324a15a41" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/251d7619-2ab1-44e8-bfc4-2196e34d5319" />

#### 3.1 OBSERVATION

As observed in the gathered output that the successful restoration of the digital data depends on the proper adjustment of the Variable DC control used as a reference for the comparator. In the restoration stage, the comparator receives the rounded, filtered signal and compares it against this adjustable DC threshold. By tuning the Variable DC control to the middle of the signal's voltage swing, we ensure the comparator accurately determines when a pulse is high or low, effectively removing the ripples and rounding seen in the product detector's output. If the DC level is set too high or too low, the comparator may fail to trigger or produce incorrect pulse widths, but with the correct setting, the restored yellow waveform becomes a perfect replica of the original red digital signal.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/7cdf2197-e310-42ce-b7a7-5b4b119d207e" />

---

## LAB QUESTIONS AND ANSWERS:

**Q1: What happen to the BPSK signal on the data stream logic transition?**

The BPSK signal undergoes a 180° phase shift whenever the digital data transitions between logic 0 and logic 1.

**Q2: What feature of the BPSK signal suggest that its a DSBSC signal?**  

The absence of a carrier component in the spectrum and the fact that the signal changes polarity indicate that BPSK is a form of Double Sideband Suppressed Carrier (DSBSC) modulation.

**Q3: Why the recovered digital signal not a perfect copy of the original?**  

The recovered signal passes through filters that introduce rounded edges, delay, and slight ripples. Additionally, The Noise and bandwidth limitations also affect the sharpness of the transitions, preventing a perfect replic

**Q4: What can be used to clean up the recovered digital signal?**

A comparator can be used to restore the digital signal.

**Q5: What does varying DC voltage on the comparator's input change the shape of the digital signal?**

Adjusting the DC reference voltage changes the switching threshold of the comparator. Additionally, When set correctly, it produces clean and accurate logic levels; when set too high or too low, it causes missed transitions or distorted pulse widths.

---

## CONCLUSIONS:
After analyzing the gathered data and observations about Binary Phase Shift Keying (BPSK), the following conclusions have been made:
- BPSK was successfully generated using the mathematical model implemented with the Multiplier module.
- The oscilloscope clearly showed 180° phase reversals in the carrier signal corresponding to changes in the digital data.
- The constant amplitude and frequency of the carrier confirmed that information is encoded solely in the phase.
- Product detection effectively demodulated the BPSK signal by multiplying it with a coherent carrier and applying low-pass filtering.
- The recovered signal closely followed the original data but exhibited rounding and ripples due to filtering and system limitations.
- The comparator played a crucial role in restoring clean digital levels by converting slow, distorted transitions into sharp logic pulses.
- Proper adjustment of the comparator’s DC reference voltage was essential for accurate data restoration.
