# PCM DECODING

---

## INTRODUCTION:

Pulse Code Modulation (PCM) decoding is the process of recovering an analog signal from a stream of binary data produced by PCM encoding. The decoder identifies each data frame, converts the binary numbers into proportional voltage levels, and holds each value until the next frame is decoded, forming a pulse amplitude modulated (PAM) signal. This PAM signal is then passed through a low-pass filter to reconstruct the original message. Proper clock and frame synchronization are essential for accurate decoding; therefore, the PCM Decoder module on the Emona Telecoms-Trainer 101 uses the same clock and frame synchronization signals as the PCM Encoder module to ensure correct signal recovery.

---

## OBJECTIVES:

In this experiment, we will be able to use the Emona Telecoms-Trainer 101 to convert a sinewave and speech to a PCM data stream then convert it to a PAM signal using the PCM Decoder module. For this to work correctly, the decoder's clock and frame synchronisation signal are simply "stolen" the PCM Encoder module. You'll then recover the message using the Tuneable Low-pass filter module.

---

## EQUIPMENT TO BE USED:
1. Emona Telecoms-Trainer 101 (plus power-pack)
2. Dual channel 20Mhz Oscilloscope
3. Two Emona Telecoms-Trainer Oscilloscope lead
4. Assorted Emona Telecoms-Trainer 101 patch leads
5. One set of Headphones (stereo)

---

## SUMMARY OF FINDINGS AND RESULTS:

### 1. Setting up the PCM Encoder 

The first part of the experiment focuses on setting up the PCM Encoder. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/9f7727b9-bbeb-48fa-a03d-8af995f9146f" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/d0cc4af2-d149-4419-ae53-793d545e325f" />


#### 1.1 OBSERVATION

It is observe the yellow waveform  the Frame Synchronization (FS) signal acts as a steady heartbeat for the system. It marks the exact moment a new "sample" or measurement of the input voltage is taken. The blue waveform is the PCM Data output, which carries the digital "translation" of that voltage.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/754ea447-c54f-4271-ad89-073b805c326d" />

### 2. PCM Encoder with VCO input

In the next part of the experiment, we add the VCO module to input 1 of the PCM Encoder module. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/7596ea50-a127-4dfa-9c81-1130de3f2372" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/42736f79-6ea6-471f-a5e5-bace68030fb2" />

#### 2.1 OBSERVATION

In this  setup, adding a Voltage Controlled Oscillator (VCO) to the input introduces a signal that is constantly changing its frequency. The red waveform serves as the Frame Synchronization (FS) signal. Just like in previous tests. On the other hand the Yellow waveform is the PCM Data output, which now carries the digital code for a signal that is moving and shifting in real-time.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/7e858660-7b6c-45e7-967d-b486fe0ee466" />

### 3. Decoding the PCM Data

In the next part of the experiment, we will decode the encoded PCM Data in the first part of the experiment. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/a54361da-c8d4-4894-9577-75c43e787bc2" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/39208a0f-7a04-45d1-9bce-4aa42152e735" />

#### 3.1 OBSERVATION

It is observed that the red waveform is the original analog message (sinewave) and the yellow waveform is the reconstructed output signal from the PCM decoder. The output signal looks like a "staircase" because the decoder is recreating the original wave based on the digital samples it receives. Each step represents a specific digital value that was captured during the encoding process. While it follows the same shape and frequency as the red sinewave (roughly 1.04 kHz), it is composed of these sharp edges because the system only updates the voltage at every clock pulse.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/0e1bc74b-6efa-489e-b4a7-be92185e12bc" />

### 4. Encoding and Decoding Speech

In the next part of the experiment, a speech signal will be encoded and decoded to replicate a real-world communication application. This demonstrates how PCM systems are used in practical scenarios such as digital telephony, where voice signals are converted into digital data for transmission and then reconstructed at the receiver. Refer the connection to the figure below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/2cec5792-9157-4661-9193-1f61cfb43e40" />

#### 4.1 OBSERVATION

It is observed that the red waveform is the original speech signal and the yellow waveform is the reconstructed speech output from the PCM decoder. Unlike a simple sinewave, a speech signal is highly complex and irregular. When this signal is processed through the PCM Encoder, it is sampled at a high rate . Each unique peak and valley of the voice is converted into a digital code. The yellow waveform is observe to show the decoder’s attempt to rebuild that voice. 

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/dfc14146-e208-448a-bb0c-0d49ab9386ff" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/a410e007-4129-44d9-b71a-6bf04de67894" />

### 5. Recovering the Message

In the last part of the experiment, we will be able to reconstruct the PCM decoder output using a low pass filter. Refer the connection to the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/97f264e2-f136-410b-9fd2-4f142db033b5" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/6ac7bfe8-fcfc-461a-951c-8859318f9fff" />

#### 5.1 OBSERVATION

It is observed that the red waveform is the original analog message (sinewave) and the yellow waveform is the filtered output signal after passing through the reconstruction filter. In its current state, the yellow signal is observe to be highly distorted. This happens because the filter's "cut-off" frequency needs to be tuned correctly to allow the original message's frequency through while blocking the high-frequency sampling noise.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/2ede565b-4c6b-443e-af87-7494ea6d97ce" />

---

## LAB QUESTIONS AND ANSWERS:

**Q1: What does the PCM Decoder stepped output tell you about the type of signal that is?**

The stepped output of the PCM Decoder shows that the signal is a pulse-amplitude modulated (PAM) version of the original analog signal. Each step corresponds to a discrete voltage level representing a sampled value of the original signal.

**Q2: What must be done to the PCM Decoder Module output to reconstruct the message properly?**  

To properly reconstruct the original message, the stepped output must be passed through a low-pass filter. This smooths out the steps and produces a continuous analog signal that approximates the original waveform.

**Q3: Even though the two signals look and sound the same, why isn't the reconstructed message a perfect copy of the original message?** 

The reconstructed message isn’t perfect because of quantization error. Each sample is rounded to the nearest quantization level during encoding, so some small differences between the original and decoded signals are inevitable. Additionally, any sampling or filtering limitations may also introduce minor distortions.

---

## CONCLUSIONS:
After analyzing the gathered data and observations about PCM Decoding, the following conclusions have been made:
- PCM decoding successfully converts a digital PCM data stream back into an analog signal, demonstrating the reverse process of PCM encoding.
- Proper reconstruction of the original signal requires passing the decoder’s stepped output through a low-pass filter to smooth the voltage steps into a continuous waveform.
- Accurate decoding depends on clock and frame synchronization; the decoder must use the same clock and frame signals as the encoder to interpret the digital data correctly.
- Decoding a simple sinewave shows that the reconstructed output follows the same shape and frequency but appears as a staircase due to discrete sampling. While, Decoding a complex signal, such as speech, demonstrates how PCM can handle real-world signals, though the reconstructed waveform may still show minor irregularities.
- The reconstructed message is not a perfect copy of the original due to quantization error and the limitations of sampling and filtering.
- Adjusting the low-pass filter is essential for reducing distortion and recovering the message more accurately.
