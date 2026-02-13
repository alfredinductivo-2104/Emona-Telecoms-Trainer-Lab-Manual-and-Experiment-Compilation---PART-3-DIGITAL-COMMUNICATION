# QUADRATURE PHASE SHIFT KEYING (QPSK)

---

## INTRODUCTION:

Quadrature Phase Shift Keying (QPSK) is a digital modulation technique derived from Binary Phase Shift Keying (BPSK). Like BPSK, QPSK is based on Double Sideband Suppressed Carrier (DSBSC) modulation. However, unlike BPSK which transmits one bit at a time, QPSK transmits two bits simultaneously by combining two BPSK signals that are 90° out of phase with each other.

In QPSK, the incoming digital data stream is divided into even and odd bits using a bit-splitter. Each bit stream modulates the same carrier frequency, but one carrier is phase-shifted by 90°. These two phase-shifted signals are then added together for transmission. Because the carriers are orthogonal (90° apart), the receiver can separate them using phase-sensitive product detectors during demodulation.

Although QPSK sends two bits at a time, it does not double the data rate compared to BPSK because the bit stream is converted into bit pairs, effectively reducing the bit rate. Its main advantage is improved spectral efficiency, QPSK requires only half the bandwidth of BPSK for reliable transmission. This makes QPSK widely used in modern digital communication systems where bandwidth conservation is important.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/d7973814-6230-462b-8682-23a8d298ea6c" />

---

## OBJECTIVES:

In this experiment, we will be using the Emona Telecoms-Trainer 101 to generate a Quadrature Phase Shift Keying (QPSK) signal by implementing its mathematical model. Additionally, we wil be able to examine how phase discrimination using a product detector can be used to pick out the data on one BPSK signal or other.

---

## EQUIPMENT TO BE USED:
1. Emona Telecoms-Trainer 101 (plus power-pack)
2. Dual channel 20Mhz Oscilloscope
3. Two Emona Telecoms-Trainer Oscilloscope lead
4. Assorted Emona Telecoms-Trainer 101 patch leads
5. One set of Headphones (stereo)

---

## SUMMARY OF FINDINGS AND RESULTS:

### 1. Generating an QPSK Signal 

In the first part of the experiment, we will be generating a QPSK signal using the Emona Telecoms-Trainer Sequence Generator, Divider, and Serial to Parallel Module with a 8 Khz Digital signal as input. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/e1c77025-c23f-46e1-b4f0-05cbafbae4aa" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/ace7b933-e37c-4fcf-b8cd-690e3c01bd4d" />


#### 1.1 OBSERVATION

In this setup, it is observed that the oscilloscope displays two distinct pulse trains representing the Even (red waveform) and Odd (yellow waveform) bit streams. Both waveforms maintain a clean, rectangular square wave shape, which is characteristic of the digital signal modeling stage before it undergoes actual phase modulation. The transitions between high and low states are sharp, showing that the 2-bit serial-to-parallel converter is accurately holding each bit value for the required duration dictated by the master clock. Additionally, we are able to see the measured values of both channels show a consistent peak-to-peak voltage (Vpp) of 4.240V, which represents the logic high level of the digital "1" bits. The frequency (F) for the red channel is measured at 1.006kHz and the yellow at 1.075kHz, with corresponding periods (T) of approximately 0.994ms and 0.930ms.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/c12a711f-55f6-48c3-a815-ffaecb29e440" />

### 2. Generating an QPSK Signal with Independent Multiplier Module.

In the next part of the experiment, the bit spliiter two outputs are now connected to independent multiplier modules with different multiplier signals. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/4cb8a259-0d60-4f49-8981-655550fa1e62" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/69f94900-39c9-4ddc-bb8b-ff8c795f15b1" />


#### 2.1 OBSERVATION

In this setup, it is observed that the insertion of the Multiplier modules has transformed the simple digital pulses into high-frequency modulated signals. The waveform shape is no longer a flat square wave; instead, the traces appear as dense, solid blocks because the 100kHz Sine and Cosine carriers are oscillating much faster than the original data rate. In both channels a synchronized frequency of 1.215kHz and a period of 0.823ms, which reflects the timing of the data transitions. The peak-to-peak voltage (Vpp) is recorded at 4.240V for Channel 1 and 5.760V for Channel 2, indicating the amplitude of the carrier signals after they have been processed by the independent multiplier modules.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/c3e93c80-2177-4d46-9f89-a28a7e82e8b6" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/4a3a851a-b304-4042-a34a-54df7868ee89" />


### 3. Generating an QPSK Signal with Independent Multiplier and Adder Module.

In the next part of this experiment, a Adder module is added in order to add the two PSK signals to produce a QPSK signal. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/04eb53f2-57a2-424b-b7d7-ad8cba181cc7" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/1896f159-f75e-4f58-a293-b3ab10949ec6" />


#### 3.1 OBSERVATION

In this setup, it is observed that the insertion of the Adder module has combined the two separate phase-modulated streams into a single complex output known as the QPSK signal. Looking at the oscilloscope, the red waveform now displays the final composite QPSK signal, which appears as a high-density burst of carrier waves where the phase shifts continuously to represent the combined even and odd bit pairs. On the other hand, the yellow waveform shows a low-frequency, irregular signal with a peak-to-peak voltage (Vpp) of 544.0mV and a frequency of 60.10Hz, indicating it is likely monitoring a filtered or auxiliary component rather than the primary carrier.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/23873e38-5030-4802-af60-0c776be02466" />


---

## LAB QUESTIONS AND ANSWERS:

**Q1: What is the relationship between the bit rate of these two digital signals and the bit rate of the Sequence Generator module's output?**

The two digital signals (Even and Odd bit streams) each have a bit rate that is half of the original Sequence Generator’s output bit rate. This is because the serial data stream is divided into two parallel streams using a serial-to-parallel converter. Since alternate bits are separated (even bits to one channel and odd bits to another), each channel carries only half of the total bits, reducing the bit rate by a factor of two.

**Q2: What feature of the Multiplier's output suggests that its a BPSK signal?**  

The Multiplier’s output shows a high-frequency carrier whose phase reverses (180° shift) depending on whether the input bit is logic 1 or logic 0. The amplitude remains constant, but the phase changes according to the digital data. This phase inversion characteristic is the defining feature of a Binary Phase Shift Keying (BPSK) signal.

**Q3: What type of signal is present on the Multipliers output?**  

The signal present at the Multiplier’s output is a Double Sideband Suppressed Carrier (DSBSC) modulated signal carrying digital information. Since the carrier is multiplied by a bipolar digital signal, the result is a BPSK waveform, which is a special case of DSBSC modulation with phase variations representing binary data.

---

## CONCLUSIONS:
After analyzing the gathered data and observations about Quadrature Phase Shift Keying (QPSK), the following conclusions have been made:
- QPSK is formed by combining two BPSK signals that are 90° out of phase with each other.
- The serial-to-parallel conversion reduces the bit rate of each individual stream to half of the original input bit rate.
- Each Multiplier module produces a BPSK signal, identifiable by its constant amplitude and phase reversals.
- The Adder module successfully combines the two orthogonal BPSK signals into a single QPSK waveform.
- QPSK improves spectral efficiency by transmitting two bits per symbol while occupying the same bandwidth as a single BPSK signal.
- Phase discrimination in the receiver allows proper recovery of the even and odd bit streams using product detectors.
- Although QPSK transmits two bits per symbol, the overall data rate is not doubled because the bit stream is divided into two parallel channels.
- QPSK significantly improves spectral efficiency, requiring only half the bandwidth of BPSK for the same bit rate.
- The constant amplitude nature of QPSK makes it more power-efficient compared to amplitude-based modulation schemes.
