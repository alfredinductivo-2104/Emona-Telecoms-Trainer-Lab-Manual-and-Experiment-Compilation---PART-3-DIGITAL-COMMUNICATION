# DIRECT SEQUENCE SPREAD SPECTRUM (DSSS) MODULATION AND DEMODULATION

---

## INTRODUCTION:
Direct Sequence Spread Spectrum (DSSS) is a digital modulation technique based on Double Sideband Suppressed Carrier (DSBSC) modulation. Instead of using a single sinusoidal carrier, DSSS multiplies the message signal with a high-speed pseudo-noise (PN) sequence. This spreads the signal energy over a wide bandwidth, making it more resistant to noise, interference, and jamming.

For proper demodulation, the receiver must use an identical and synchronized PN sequence. If the sequence does not match, the recovered signal appears as noise. Because of this requirement, DSSS provides both interference resistance and inherent security. DSSS is widely used in modern communication systems such as CDMA, GPS, and Wi-Fi technologies.

---

## OBJECTIVES:

In this experiment, we will be using the Emona Telecoms-Trainer 101 to generate A DSSS signal by implementing its mathematical model. Additionally, we are able to reproduce the message using the product detector with a stolen carrier. 


---

## EQUIPMENT TO BE USED:
1. Emona Telecoms-Trainer 101 (plus power-pack)
2. Dual channel 20Mhz Oscilloscope
3. Two Emona Telecoms-Trainer Oscilloscope lead
4. Assorted Emona Telecoms-Trainer 101 patch leads
5. One set of Headphones (stereo)

---

## SUMMARY OF FINDINGS AND RESULTS:

### 1. Generating a DSSS signal using a simple message 

In the first part of the experiment, we will be generating a DSSS signal by implementing the mathematical model for DSBSC, since DSSS is just basically a DSBSC with a pulse for the carrier instead of a simple sinusoid. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/0406ce6c-b97c-456b-98e5-59d3c96d8b47" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/ea151680-fd86-4840-b403-b0cd5f18653e" />

#### 1.1 OBSERVATION

In this setup, it is observed that the Multiplier module has combined a low-frequency message signal with a high-speed pseudo-noise (PN) sequence to produce a Direct Sequence Spread Spectrum (DSSS) signal. Looking at the oscilloscope, the red waveform (Channel 1) represents the original 2kHz sine wave message, which serves as the information to be transmitted. The yellow waveform (Channel 2) shows the resulting DSSS output, appearing as a high-frequency carrier whose amplitude envelope is shaped by the message, but containing rapid internal transitions caused by the 100kHz PN sequence. Additionally, we can see that the output is more likely replicates an AM signal.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/64ce2a40-dd43-4145-af63-22af0395c264" />

### 2. Generating a DSSS signal using speech

In the next part of the experiment, unlike the first part where a sinewave was used as the message signal, a real voice signal will be used to better replicate real-world communication conditions. Refer the connection to the figure below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/b958108a-1afb-4c37-bf3b-2f1ccc02c8ca" />

#### 2.1 OBSERVATION

In this setup, it is observed that replacing the fixed sine wave with a speech signal has resulted in a more complex and dynamic modulated waveform. Looking at the oscilloscope, the red waveform (Channel 1) now displays the actual voice signal, which is characterized by its irregular, non-repetitive shape and varying amplitudes compared to a standard tone. The yellow waveform (Channel 2) represents the resulting DSSS signal, which appears as a series of high-frequency bursts that expand and contract in direct response to the varying intensity of the speech input.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/59fa6f4d-4a86-412c-9a70-4ba48487ec99" />


### 3. Using the Product Detector to Recover the Message

In the next part of this experiment, using the Multiplier and Tuneable Low Pass Filter modules to implement a product detector, we will be able to recover the original message from the DSSS signal. Additionally, to facilitate this, the PN sequence is used for the modulator carries is stolen for the product detector local carrier. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/64089c0c-63d5-4b51-89f0-ca99a9858f95" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/8bc5f2b2-c270-4f88-aa76-7f3e5bd73fb7" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/f963e9a6-be23-4208-bcc8-607187e5c5e8" />


#### 3.1 OBSERVATION

It is observed that the Product Detector  has successfully extracted the original information from the spread spectrum signal. The red waveform (Channel 1) represents the reference message signal, while the yellow waveform (Channel 2) shows the recovered output after the despreading process. The despreading is achieved by multiplying the incoming DSSS signal with a locally generated "Stolen" PN sequence that is perfectly synchronized with the one used during modulation. Additionally, The recovered signal shows a much lower peak-to-peak voltage (Vpp) of 640.0mV. While its shape is clearly sinusoidal and matches the period of the reference signal, it contains some residual high-frequency noise and multiple overlapping traces

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/a5e0bd78-7ae3-4db1-9bd3-c1f468a374c8" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/09e2021a-3ef0-45f9-a644-5b8063eadbf0" />


### 4. Using the Product Detector to Recover the Message with Different PN sequence to the transmitter carrier

In the next part of the experiment, we will be modifying the previous setup in order to make the demodulator's local carrier a different PN sequence to the transmitter carrier. Refer the connection to the figure below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/0cbd51eb-3d3d-415e-b372-d67b6621b5a0" />

#### 4.1 OBSERVATION

In this setup, it is observed that using a different PN sequence for the local carrier in the demodulator results in a failure to recover the original message. While the red waveform (Channel 1) still shows the reference 2kHz sine wave message with a peak-to-peak voltage (Vpp) of 4V, the yellow waveform (Channel 2) no longer displays a recognizable sinusoidal shape. Instead, the output consists of low-amplitude, unstructured noise with a peak-to-peak voltage (Vpp) of only 725.7mV.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/38c350fd-b579-4c93-b337-6ad44073f0bd" />

### 5. DSSS and Deliberate Interference (Jamming)

In the next part of the experiment, we will be modifying the previous setup in order to make the demodulator's local carrier a different PN sequence to the transmitter carrier. Refer the connection to the figure below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/0cbd51eb-3d3d-415e-b372-d67b6621b5a0" />

#### 5.1 OBSERVATION

In this setup, it is observed that using a different PN sequence for the local carrier in the demodulator results in a failure to recover the original message. While the red waveform (Channel 1) still shows the reference 2kHz sine wave message with a peak-to-peak voltage (Vpp) of 4V, the yellow waveform (Channel 2) no longer displays a recognizable sinusoidal shape. Instead, the output consists of low-amplitude, unstructured noise with a peak-to-peak voltage (Vpp) of only 725.7mV.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/38c350fd-b579-4c93-b337-6ad44073f0bd" />

### 6. DSSS and Deliberate Interference (Jamming)

In the next part of the experiment, we will be modifying the previous setup in order to make the demodulator's local carrier a different PN sequence to the transmitter carrier. Refer the connection to the figure below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/0cbd51eb-3d3d-415e-b372-d67b6621b5a0" />

#### 6.1 OBSERVATION

In this setup, it is observed that using a different PN sequence for the local carrier in the demodulator results in a failure to recover the original message. While the red waveform (Channel 1) still shows the reference 2kHz sine wave message with a peak-to-peak voltage (Vpp) of 4V, the yellow waveform (Channel 2) no longer displays a recognizable sinusoidal shape. Instead, the output consists of low-amplitude, unstructured noise with a peak-to-peak voltage (Vpp) of only 725.7mV.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/38c350fd-b579-4c93-b337-6ad44073f0bd" />

### 7. DSSS and Deliberate Interference (Jamming)

In the next part of the experiment, we will be modifying the previous setup in order to make the demodulator's local carrier a different PN sequence to the transmitter carrier. Refer the connection to the figure below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/0cbd51eb-3d3d-415e-b372-d67b6621b5a0" />

#### 7.1 OBSERVATION

In this setup, it is observed that using a different PN sequence for the local carrier in the demodulator results in a failure to recover the original message. While the red waveform (Channel 1) still shows the reference 2kHz sine wave message with a peak-to-peak voltage (Vpp) of 4V, the yellow waveform (Channel 2) no longer displays a recognizable sinusoidal shape. Instead, the output consists of low-amplitude, unstructured noise with a peak-to-peak voltage (Vpp) of only 725.7mV.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/38c350fd-b579-4c93-b337-6ad44073f0bd" />






---

## LAB QUESTIONS AND ANSWERS:

**Q1: What is the relationship between the bit rate of these two digital signals and the bit rate of the Sequence Generator module's output?**

The two digital signals (Even and Odd bit streams) each have a bit rate that is half of the original Sequence Generator’s output bit rate. This is because the serial data stream is divided into two parallel streams using a serial-to-parallel converter. Since alternate bits are separated (even bits to one channel and odd bits to another), each channel carries only half of the total bits, reducing the bit rate by a factor of two.

**Q2: What feature of the Multiplier's output suggests that its a BPSK signal?**  

The Multiplier’s output shows a high-frequency carrier whose phase reverses (180° shift) depending on whether the input bit is logic 1 or logic 0. The amplitude remains constant, but the phase changes according to the digital data. This phase inversion characteristic is the defining feature of a Binary Phase Shift Keying (BPSK) signal.

**Q3: What type of signal is present on the Multipliers outptu?**  

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
