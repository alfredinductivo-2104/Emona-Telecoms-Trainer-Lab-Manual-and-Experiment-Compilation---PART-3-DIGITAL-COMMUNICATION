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

### 4. Decoding the PCM Data with Buffer Module




#### 4.1 OBSERVATION

### 5. Decoding the PCM Data with Buffer Module and VC0. 




#### 5.1 OBSERVATION

### 6. Encoding and Decoding Speech




#### 6.1 OBSERVATION

### 7. Recovering the Message




#### 7.1 OBSERVATION





---

## LAB QUESTIONS AND ANSWERS:

**Q1:What type of sampling is shown in the first part of the experiment? and What two features of the sampled signal confirm this? **


**Q2:What two features of the sampled signal confirm that the set-up models the sample-and-hold scheme?**  


**Q3: What’s the name of the distortion that appears when the VCO module’s Frequency Adjust control is turned far enough?**  


**Q4: Given the message is a 2kHz sinewave, what’s the theoretical minimum frequency for the sampling signal?**


**Q4: Why is the actual minimum sampling frequency higher than the theoretical minimum that you calculated for Question 4**


---

## CONCLUSIONS:
After analyzing the gathered data and observations about Sampling and Reconstruction of a signal, the following conclusions have been made:
