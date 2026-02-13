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

Interference occurs when an unwanted electrical signal gets added to the transmitted signal (typically in the channel) and changes it enough to change the recovered message. Electrical noise is a significant source of unintentional interference.

However, sometimes noise is deliberately added to the transmitted signal for the purpose of interfering or "jamming" it. In the next part of the experiment models deliberate interference to show how spread spectrum signals are highly resistant to it. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/ec70c60c-d65e-447c-84ca-3a61cea8f2c8" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/d4d9fe44-bd5f-4719-b954-31dbd4e468fa" />

#### 5.1 OBSERVATION

In this setup, it is observed that the addition of a Jamming signal in the communication channel creates significant distortion in the transmitted signal, yet the system successfully recovers the message. Looking at the oscilloscope, the red waveform (Channel 1) represents the DSSS signal with interference, which now appears as a highly erratic and noisy high-frequency burst. The yellow waveform (Channel 2) displays the Recovered message, which, despite the heavy interference, maintains a clear sinusoidal shape that matches the original 2kHz source.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/36d03a32-d0ad-4ab9-b090-ad61e26e0ff1" />

### 6. DSSS and Deliberate Interference Part 2 (Jamming)

A more sophisticated approach to jamming involves automatically sweeping the jamming signal through a wide range of frequencies to increase the chances of upsetting the transmitted signal. In the next part of the experiment let's you see how spread spectrum handles this kind of jamming signal. Refer the connection to the figure below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/20424edf-42b0-4423-85b8-2329bed1eae4" />

#### 6.1 OBSERVATION

It is observed that while the system remains resistant to jamming, the swept-frequency interference introduces more noticeable fluctuations in the recovered output compared to a fixed-tone jammer. On the oscilloscope, the red waveform (Channel 1) shows the DSSS signal combined with a frequency-swept jamming signal, appearing as a dense, high-frequency mass with rapidly shifting characteristics. The yellow waveform (Channel 2) displays the recovered message, which still maintains its general sinusoidal shape despite the more aggressive interference but we can see that the recovered signal is more jammed than the previous setup. 

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/60ce2d93-c85a-45e9-a2fd-18fe14d15611" />

### 7. DSSS and Deliberate Interference Part 3 (Jamming)

In the next part of the experiment, a much more sophisticated approach to jamming is implemented using a Noise signal added to the recovered message. Refer the connection to the figure below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/9d4935fc-396b-450a-945b-dc5b73de37b9" />

#### 7.1 OBSERVATION

It is observed that the more sophisticated jamming signal creates a noticeably more distorted and unstable output compared to the previous fixed or basic swept jamming experiments. The red waveform (Channel 1) shows a dense, highly irregular mass of interference with a peak-to-peak voltage (Vpp) of 3.800V. Consequently, the yellow waveform (Channel 2) displays a recovered message that is much more jagged and inconsistent in shape, with its dropping to 592.00mV.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/e611b4fd-3f89-4410-88a2-a146ac143a84" />

---

## LAB QUESTIONS AND ANSWERS:

**Q1: What feature of the Multiplier's output suggests that its basically a DSBSC signal?**

The Multiplier’s output shows that the carrier (PN sequence) is present only when multiplied by the message and does not appear as a separate constant component. There is no distinct carrier frequency visible on its own, indicating that the carrier is suppressed. The output consists of sideband components shaped by the message signal, which is the defining characteristic of a Double Sideband Suppressed Carrier (DSBSC) signal.

**Q2: Why is the DSSS signal so large when it's supposed to be small and indistinguishable from noise?**  

In the laboratory setup, the DSSS signal appears large because it is generated and observed in a controlled environment with minimal background noise and sufficient signal amplitude for measurement. In real-world long-distance transmission, the signal energy is spread over a wide bandwidth, making the power spectral density very low and difficult to distinguish from noise.

**Q3: Why isn't there any signal out of the DSSS modulator when you're not talking, etc?**  

When there is no input message, the message signal amplitude is nearly zero. Since DSSS is implemented using multiplication, multiplying the PN sequence by zero results in zero output. Therefore, no significant transmitted signal is observed during silence.

**Q4: What does the signal out of the low pass filter look like?**  

The signal at the output of the low pass filter resembles the original baseband message signal. After despreading in the product detector, the high-frequency PN components are removed by the filter, leaving a low-frequency waveform that matches the original sine wave or speech signal, although it may contain some residual noise.

**Q5: Why does using the wrong PN sequence for the local carrier cause the product detector output to look like this?**  

Using an incorrect PN sequence means the receiver is not synchronized with the transmitter. As a result, the despreading process fails because the multiplied components do not align in frequency and phase. Instead of coherently adding to reconstruct the message, the components cancel randomly, producing a low-amplitude noise-like output rather than the original signal.

**Q6: Why doesn't the jamming signal interference with the recovery of the message ?**  

The jamming signal typically occupies a narrow frequency band, while the DSSS signal is spread across a wide bandwidth. During despreading, the correct PN sequence compresses the spread signal energy back into the original narrowband message, while the narrowband jammer becomes spread out over a wide bandwidth. This significantly reduces the jammer’s power density in the recovered signal, allowing the original message to be recovered with minimal distortion.

---

## CONCLUSIONS:
After analyzing the gathered data and observations about Direct Sequence Spread Spectrum (DSSS) Modulation and Demodulation, the following conclusions have been made:
- DSSS is fundamentally a DSBSC modulation scheme that uses a high-speed pseudo-noise (PN) sequence instead of a sinusoidal carrier.
- The spreading process distributes the message energy across a much wider bandwidth, increasing resistance to noise and interference.
- Successful demodulation requires an identical and synchronized PN sequence; otherwise, the recovered signal appears as noise.
- The product detector combined with a low pass filter effectively despreads the signal and reconstructs the original message.
- Using a mismatched PN sequence demonstrates the inherent security of DSSS, as unauthorized receivers cannot easily recover the transmitted information.
- DSSS shows strong resistance to deliberate interference (jamming), including fixed-tone, swept-frequency, and noise-based jamming signals.
- During despreading, the desired signal is compressed back to baseband while interference is spread out, reducing its impact on the recovered output.
