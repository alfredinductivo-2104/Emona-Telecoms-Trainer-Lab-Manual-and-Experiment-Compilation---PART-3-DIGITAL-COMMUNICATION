# FREQUENCY SHIFT KEYING (FSK)

---

## INTRODUCTION:

Frequency Shift Keying (FSK) is a digital modulation technique used in frequency division multiplexing (FDM) systems, where multiple users share a communication channel by transmitting signals in different frequency bands. In FSK, digital data is transmitted by shifting the frequency of a carrier signal between two distinct values: the mark frequency for logic 1 and the space frequency for logic 0. Unlike amplitude-based schemes, the carrier amplitude remains constant while only the frequency varies.

One of the main advantages of FSK is its improved noise immunity compared to amplitude modulation, since most noise affects signal amplitude rather than frequency. This makes FSK suitable for reliable digital communication in noisy environments. FSK signals can be generated using voltage-controlled oscillators (VCOs) and demodulated using FM demodulators such as zero-crossing detectors, phase-locked loops, or selective filtering techniques.

---

## OBJECTIVES:

In this experiment, we will be able to used the Emona Telecoms-Trainer 101 (ETT-101) to generate an FSK signal using a voltage-controlled oscillator (VCO). The digital message is produced by the Sequence Generator module. The transmitted data is then recovered by filtering one of the frequency components of the FSK signal and demodulating it with an envelope detector. Lastly, the distorted output is observed and a comparator is used to restore the original digital data.

---

## EQUIPMENT TO BE USED:
1. Emona Telecoms-Trainer 101 (plus power-pack)
2. Dual channel 20Mhz Oscilloscope
3. Two Emona Telecoms-Trainer Oscilloscope lead
4. Assorted Emona Telecoms-Trainer 101 patch leads
5. One set of Headphones (stereo)

---

## SUMMARY OF FINDINGS AND RESULTS:

### 1. Generating an FSK Signal 

In the first part of the experiment, we will be able to generate a Frequency Shift Keying Signal using the ETT 101 Sequence Generator, VCO, and an 8 KHz Digital input. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/7b95d923-6829-42b5-a342-ab49069c1cbd" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/7431df99-24ef-481e-b8b8-f3269f8ed9ac" />

#### 1.1 OBSERVATION

As observe in the gathered output that the oscilloscope displays a clear Frequency Shift Keying (FSK) signal where the red Channel 1 trace represents a digital pulse with a peak voltage (Vp) of 800.0 mV, and the yellow Channel 2 trace shows the modulated carrier wave. The yellow waveform shifts from a lower frequency to a higher frequency exactly when the digital signal transitions to a high state, confirming the VCO's response to the input. Quantitatively, the FSK signal maintains a peak-to-peak voltage of 4.560 V and an average frequency of 2.299 kHz, with the horizontal timebase set to 500 μs per division to capture the shift between the mark and space frequencies.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/23b3695b-4685-46aa-9937-ff9bde055ed5" />

### 2. Demodulating an FSK Signal using Filtering 

In the next part of the experiment, As FSK is just really an FM, it can be recovered using any of the FM Modulation Scheme. However, as the FSK signal switches back and fourth between two frequencies we can use a method of demodulating it that cannot be used to demodulate speech encoded signal. This was shown using the given Circuit. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/9d831118-ce98-4a61-bc3e-c6b371271fea" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/17e0811f-0527-4845-b54f-26ec36bf22e5" />


#### 2.1 OBSERVATION

As observe in the gathered output that the oscilloscope illustrates the FSK demodulation stage, where the red Channel 1 trace shows the input digital pulse with a peak voltage (Vp) of 5.400 V. The yellow Channel 2 trace displays the signal after the Tuneable Low-pass filter, which converts frequency shifts into amplitude variations for the envelope detector. This filtered signal exhibits a peak-to-peak voltage (Vpp) of 5.840 V and a frequency of 13.93 kHz, reflecting its transition from the 10 KHz rest frequency.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/5177ddaa-adb1-42d1-bc0a-729d431ce32f" />


### 3. Demodulating an FSK Signal using Filtering and Envelope Detector

From the previous part of the experiment, we will now add a envelope detector to the circuit using the DIODE & RC LPF, RECTIFIER, and BASEBAND LPF Module in the Emona Telecoms-Trainer 101. Refer the connection to the figure below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/ea7862dc-d08d-405d-a9bc-07c067d06470" />

#### 3.1 OBSERVATION

As observe in the gathered output that the oscilloscope shows the final Demodulated FSK signal on the yellow Channel 2 trace, which has been recovered after passing through the Envelope detector. This waveform closely follows the timing of the original digital pulse seen on the red Channel 1 trace. The obtained values for the recovered signal (yellow waveform) show a peak voltage (Vp) of 102.0 mV and a frequency (f) of 536.8 Hz, while the original digital input (red waveform maintains a peak voltage (Vp) of 5.400 V.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/7020b0b6-d5a1-4a80-864b-6442a6369075" />

### 4. Restoring the Recovered Digital Signal using a Comparator

In the last part of this experiment, it will show how useful a comparator is, when it comes to restoring distorted digital signal. Additionally, The comparator will be used to clean up the demodulated FSK Signal in the previous part of this experiment. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/95421985-3d6a-47b1-a7cf-faff98f2a1e1" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/687da668-251d-4ef2-b4d2-7e3cf23ba17d" />


#### 4.1 OBSERVATION

As observe in the gathered output that the oscilloscope illustrates the Restoration stage of the FSK receiver, where the yellow Channel 2 trace shows a noisy, low-amplitude signal attempting to represent the Restored digital signal. While the red Channel 1 trace provides a clear reference of the original digital pulse with a peak voltage (Vp) of 5.200 V, the restored output on Channel 2 is currently dominated by noise, showing a very low peak voltage (Vp) of only 17.52 mV and a frequency (F) of 8.311 kH

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/dc2f064e-c90a-43a1-848e-4fad18d3cb2d" />

---

## LAB QUESTIONS AND ANSWERS:

**Q1: What's the name for the VCO output frequency that corresponds with logic-1s in the digital data?**

The VCO output frequency that corresponds to logic-1s is called the mark frequency.

**Q2: What's the name for the VCO output frequency that corresponds with logic-Os in the digital data?**  

The VCO output frequency that corresponds to logic-0s is called the space frequency.

**Q3: Based on your observations of the FSK signal, which of the two is the higher frequency? Explain your answer.**  

The mark frequency is the higher frequency. This is observed on the oscilloscope where the carrier waveform increases in frequency whenever the digital input transitions to a logic-1 state, confirming the VCO’s response to a high input voltage.

**Q4: Which of the FSK signal's two sinewave is the filter picking out??**

The filter picks out one of the two frequency components, specifically the frequency that falls within the filter’s passband (either the mark or space frequency depending on tuning).

**Q5: What does the filtered FSK look like?**

The filtered FSK appears as a sinusoidal waveform with amplitude variations, where the presence or absence of the selected frequency produces changes in signal amplitude that can be detected by an envelope detector.

**Q6: What can be used to clean up the recovered digital signal**

A comparator is used to clean up the recovered digital signal.

**Q7: How does the comparator turn the slow rising voltage of the recovered digital signal into sharp transitions?**

The comparator compares the recovered signal to a reference voltage and switches its output instantly when the input crosses this threshold, converting slow and noisy voltage changes into clean, sharp digital transitions.

---

## CONCLUSIONS:
After analyzing the gathered data and observations about Frequency Shift Keying (ASK), the following conclusions have been made:
- Frequency Shift Keying was successfully generated using a VCO, where digital data controlled the switching between mark and space frequencies.
- The oscilloscope clearly showed frequency changes in the carrier signal corresponding to logic-1 and logic-0 states of the digital input.
- Filtering proved effective in isolating one frequency component of the FSK signal, converting frequency changes into amplitude variations.
- The envelope detector successfully recovered the baseband signal from the filtered FSK waveform, though with noticeable distortion and reduced amplitude.
- The recovered signal demonstrated the limitations of analog demodulation, including noise and slow voltage transitions.
- The use of a comparator significantly improved the recovered signal by restoring sharp logic levels and reducing distortion.
