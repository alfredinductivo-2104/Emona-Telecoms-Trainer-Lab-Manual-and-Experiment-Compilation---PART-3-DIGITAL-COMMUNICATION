# BANDWIDTH LIMITING AND RESTORING DIGITAL SIGNALS

---

## INTRODUCTION:

In any communication system, a message is transmitted from a sender to a receiver through a channel, which may include metal conductors, optical fibers, or the air. Every transmission medium has a limited bandwidth, allowing only a specific range of frequencies to pass while attenuating frequencies outside this range. This filtering effect not only reduces the amplitude of certain signal components but also shifts their phase, potentially distorting the original signal. Digital signals, like analog signals, are composed of multiple sinewaves, the fundamental frequency and its harmonics. If the channel’s bandwidth is insufficient, some of these components are attenuated or lost, altering the signal’s shape. This distortion can lead to errors in interpreting logic levels in digital circuits, making the recovered message noisy.

---

## OBJECTIVES:

In this experiment, we will use the Emona Telecoms-Trainer 101 to set up a PCM communication system. We will model the system by limiting the channel bandwidth using a Low Pass Filter (LPF). Additionally, we will observe the effect of bandwidth limitation on the PCM data using an oscilloscope and listen to how it affects the recovered message.

---

## EQUIPMENT TO BE USED:
1. Emona Telecoms-Trainer 101 (plus power-pack)
2. Dual channel 20Mhz Oscilloscope
3. Two Emona Telecoms-Trainer Oscilloscope lead
4. Assorted Emona Telecoms-Trainer 101 patch leads
5. One set of Headphones (stereo)

---

## SUMMARY OF FINDINGS AND RESULTS:

### 1. The Effects of Bandwidth Limiting on PCM Decoding

In the first part of the experiment, we will be able to prove that bandwidth limiting in a channel can distort signals and upset the operation of the receiver. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/211901ae-2869-42fc-b564-d385dd626806" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/e2b0ee12-423b-4cb3-975f-a0c11c769a97" />

#### 1.1 OBSERVATION

I observe that while the input signal (red waveform) remains a constant Variable DCV, the output signal (yellow waveform) represents a Pulse Code Modulation (PCM) encoded bitstream that is heavily impacted by the channel's characteristics. The output is observe to show a series of pulses with varying widths and noticeable noise, which indicates that as the signal travels through the channel from the encoder to the decoder, it is experiencing bandwidth limiting.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/394d450c-5c47-4e9b-a901-ad2c394f1cbe" />

### 2. The Effects of Bandwidth Limiting on PCM Decoding with Added Low Pass Filter

In the next part of the experiment, a Low Pass Filter was added in between the Encoding and Decoding process of the given signal.  Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/256e7a89-d6a3-4aa9-922d-226fea58ede7" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/cdb54056-1c4e-43fe-98c3-4bd5051fdfa5" />

#### 2.1 OBSERVATION

I observe that with the addition of the Tuneable LPF (Low Pass Filter) into the transmission channel, the PCM bitstream on Channel 2 (yellow waveform) shows significant changes in pulse shape compared to the first setup without the LPF. While the Message to Ch.1 remains a constant DC level

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/26e21b56-6083-4695-82d6-178cced23420" />

### 3. The Effects of Bandwidth Limiting on Digital Signal Shape

After we are able to see how channel bandwidth can upset the receiver operation. In this part of the experiment, we will look how this affect the shape of the digital signal at the receiver input. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/2dfbc78d-a808-4f84-b97b-3ad374eb2c6a" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/e7d3c785-5dcf-4bf4-8a09-93acd4d4814c" />

#### 3.1 OBSERVATION

It is observe that the original digital signal on Channel 1 (red waveform) consists of sharp, well-defined square pulses with rapid transitions between logic levels. Once this signal passes through the bandwidth-limited channel, the output on Channel 2 (yellow waveform) is severely distorted, losing its square characteristic and appearing as a continuous, rounded waveform. The pulses on Channel 2 show significant "smearing" and reduced peak amplitudes where the filter has removed the high-frequency components, causing the individual bits to blend into one another.

### 4. The Effects of Bandwidth Limiting on Digital Signal Shape with added VCO 

In the next part of the experiment, the Sequence Generator clock is now provided with VCO module's Digital Output and so it is variable. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/c322a3f8-adb2-4167-a2e4-8b08f291f06b" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/76efa549-b725-4339-b460-615c562bd589" />

#### 4.1 OBSERVATION

I observe that introducing the VCO (Voltage Controlled Oscillator) to provide a variable frequency clock to the Sequence Generator (Figure 10) allows for the direct observation of how bit rate interacts with channel bandwidth. On the oscilloscope, the original digital signal on Channel 1 (red) maintains its square shape regardless of frequency, but the bandwidth-limited signal on Channel 2 (yellow) becomes increasingly distorted as the VCO frequency increases. At higher bit rates, the yellow pulses fail to reach full amplitude and begin to overlap significantly, demonstrating that the channel's fixed bandwidth acts as a physical limit on how fast data can be transmitted before the individual bits become indistinguishable.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/221ec595-9a0a-44ea-8d0c-52663e2c8dd0" />

### 5. Restoring Digital Signal

In this part of the experiment, we are able to restore a bandwidth limited digital signal using a comparator and observe the limitation of this. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/d82fdf07-22b4-479a-8f83-0c5a0c7b9d22" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/caad6464-43a7-43d7-a761-c5087d7b0471" />

#### 5.1 OBSERVATION

It is observed that as we adjust the cutoff frequency control, the output signal gradually starts to recover and begins to resemble the original signal (red waveform). Increasing the cutoff frequency allows more of the signal’s higher-frequency components to pass through the channel, which reduces distortion caused by bandwidth limitation.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/7707b325-c574-4962-9fd6-0a96a3494b84" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/b3a30b6a-5949-4919-b01c-f1d37445cc1c" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/529da373-f83c-4cc7-a8be-06a35ab5ed4c" />

---

## LAB QUESTIONS AND ANSWERS:

**Q1: Why does bandwidth limiting of the channel cause the PCM Decoder module to output incorrect voltage as well as correct one?  **

Bandwidth limiting removes or attenuates the higher-frequency components of the PCM signal that are responsible for sharp pulse transitions. This causes pulse distortion and timing errors, leading the decoder to sometimes misinterpret logic levels and output incorrect voltages.

**Q2: If this were a communication system transmitting speech, what would these errors sound like when the message is reconstructed? **  

These errors would sound like distortion, muffling, crackling noises, or brief dropouts in the reconstructed speech. In severe cases, parts of the speech may become unintelligible.

**Q3: What two things are happening to cause the digital signal to change shape? ** 

a. Attenuation of high-frequency harmonics due to limited bandwidth
b. Phase shifting of frequency components, causing pulse spreading and intersymbol interference

**Q4: What other change to your communication system distorts the digital signal in the same way as increasing its bit rate? ** 

Reducing the channel bandwidth (lowering the LPF cutoff frequency) distorts the digital signal in the same way as increasing the bit rate, since both reduce the ratio of bandwidth to data rate.

**Q5: Although the restored digital signal is almost identical to the original digital signal, there is a difference. Can you see what it is? ** 

Yes. The restored signal shows slight timing delays, reduced amplitude accuracy, and minor jitter at the transitions compared to the original digital signal.

**Q6: Can this difference be ignored? ** 

In many practical digital systems, this difference can be ignored as long as the logic levels remain within valid thresholds. However, at higher data rates or in noisy environments, these differences may lead to bit errors and cannot be ignored.

**Q7: What do some DC Voltages cause the comparator to output the wrong information? ** 

DC voltages that are close to the comparator’s threshold voltage can cause incorrect outputs, as small noise or distortion can force the comparator to switch states unintentionally.

**Q8: Why does the comparator begin to output the wrong information when this control is turned enough ** 

As the control is adjusted further, distortion and noise increase, causing the input signal to cross the comparator threshold at incorrect times. This results in false triggering and incorrect logic outputs.

---

## CONCLUSIONS:
After analyzing the gathered data and observations about Bandwidth limiting and Restoration of Digital Signal, the following conclusions have been made:
- Bandwidth limiting significantly distorts digital signals by attenuating high-frequency components essential for sharp pulse transitions.
- Insufficient channel bandwidth leads to pulse spreading and intersymbol interference, which can upset receiver and decoder operation.
- Increasing the bit rate without increasing channel bandwidth worsens signal distortion and limits reliable data transmission.
- The shape of a digital signal changes from sharp square pulses to rounded waveforms when passed through a bandwidth-limited channel.
- A Low Pass Filter clearly demonstrates the trade-off between bandwidth and signal integrity in digital communication systems.
- The use of a comparator can successfully restore a distorted digital signal by reshaping it into valid logic levels.
- Despite restoration, small timing and amplitude differences remain due to channel limitations and filtering effects.
- Proper selection of bandwidth, bit rate, and threshold levels is critical for accurate digital signal transmission and recovery.
