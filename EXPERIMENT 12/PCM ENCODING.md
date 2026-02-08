# PULSE CODE MODULATION (PCM) ENCODING

---

## INTRODUCTION:

Pulse Code Modulation (PCM) is a digital technique used to convert analog signals into a serial stream of binary data for transmission. As digital communication systems increasingly replace analog systems in telecommunications, understanding PCM encoding becomes essential. PCM encoding involves sampling the analog signal at regular intervals, comparing each sample to predefined quantization levels, assigning the closest level, and encoding this level into a binary number that is transmitted serially. The performance of a PCM system depends largely on the sampling clock frequency and the number of quantization levels, as these factors affect aliasing and quantization error. In this experiment, the PCM Encoder module of the Emona Telecoms-Trainer 101 is used to encode fixed DC, variable DC, and continuously varying analog signals to observe PCM operation and investigate quantization effects.

---

## OBJECTIVES:

In this experiment, we will be able to use the Emona Telecoms-Trainer PCM Encoder module to convert a fixed DC voltage, a variable DC voltage, and continuously changing signal to PCM. In this experiment, we are able to verify the operation of PCM encoding and investigate quantization error a little. 

---

## EQUIPMENT TO BE USED:
1. Emona Telecoms-Trainer 101 (plus power-pack)
2. Dual channel 20Mhz Oscilloscope
3. Two Emona Telecoms-Trainer Oscilloscope lead
4. Assorted Emona Telecoms-Trainer 101 patch leads
5. One set of Headphones (stereo)

---

## SUMMARY OF FINDINGS AND RESULTS:

### 1. An Introduction to PCM Encoding using a Static DC voltage

In the first part of the experiment, an 8 kHz digital signal is used as the clock input and ground is applied to Input 1 of the PCM Encoder module. This setup allows us to observe a simple PCM-converted digital signal. Refer to the connections shown in the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/ad53e0f1-72ea-4cc3-9caa-f463bac9caa4" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/0e463454-9d3b-4eb8-91a3-47b821ec6302" />

#### 1.1 OBSERVATION

In the figure below, the input voltage, the 8 kHz digital signal (blue waveform), and the output produced by the circuit (yellow waveform) can be observed. As observed, the frequency of the signal increases significantly as it undergoes PCM encoding, increaes from 1.041 kHz to approximately 8 kHz. Additionally, the period of the signal increases during PCM encoding, while the peak-to-peak voltage remains the same.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/b3ac00b3-4ea8-42d1-9e20-886947c2db1a" />


### 2. PCM Data of the PCM-converted digital signal

After observing the FS output of the PCM-encoded digital signal, the PCM data of the PCM-converted signal is then examined. This is done by connecting the oscilloscope directly to the PCM Data socket of the PCM Encoder module on the ETT-101 Trainer. Refer to the connections shown in the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/41776f69-121b-45b9-ad1b-ac911a73f5cf" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/dd7ecda0-aa15-4f3a-b5fe-690abde5d354" />

#### 2.1 OBSERVATION

The PCM Data of a PCM-converted digital signal is observed to transformed the simple pulse into a complex digital message. The original input (yellow waveform) is a steady pulse that repeats at a relatively slow rate of about 1 kHz. The output PCM Data (blue waveform) is the digital translation of that pulse, operating at a much faster frequency of roughly 2.78 kHz.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/0a4c0d8c-f6e0-4f22-9117-2b63e7eb446d" />

### 3. PCM Encoding of a Variable DC Voltage

In the first parts of the experiment, we are able to see a PCM converted digital signal, now using the VDC module we will see what happens when we vary the DC voltage inputted in the PCM Encoder module. Refer to the connections shown in the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/c116e2a2-ff1c-4f15-b356-2aea5708306b" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/1d9f8f9f-d9ea-40ba-9fdf-91dcb399b792" />

#### 3.1 OBSERVATION

It is observed that the input voltage appears as a noisy or fluctuating line, representing a signal whose amplitude varies over time. Meanwhile, the output of the PCM-encoded VDC signal shows that the pattern of the blue pulses is no longer a simple repeating shape. Because the input voltage is continuously changing, the PCM encoder generates different binary patterns to represent each new voltage level it detects.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/b2d54485-452d-4311-8bb1-6eff5b7beeba" />

### 4. PCM Encoding a Continously Changing Voltage

In the last part of the experiment, we will be able to see what happens when the PCM encoder is used to convert a continously changing signals like a sinewave. Refer to the connections shown in the figure below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/3f7d413b-9512-4fd9-aad2-323beea08a22" />

#### 4.1 OBSERVATION

In this observation, the yellow waveform represents the Frame Synchronization (FS) signal, and the blue waveform is the PCM Data output representing a sampled sinewave.The FS signal acts as a constant trigger that tells the encoder exactly when to take a measurement of the changing sinewave. Every time the yellow line pulses, the encoder looks at the sinewave and converts its current height into a digital code, which appears as the cluster of blue pulses immediately following it.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/8f0d7f77-d005-4862-9dc1-64fbd0cdcbcc" />

---

## CONCLUSIONS:
After analyzing the gathered data and observations about the different PCM Encoding setups, the following conclusions have been made:
- Pulse Code Modulation (PCM) successfully converts analog signals into digital data by sampling, quantizing, and encoding the input voltage into binary form.
- Using a fixed DC voltage as input produces a stable and repetitive PCM output, confirming the correct operation of the PCM encoder module.
- The clock frequency plays a critical role in PCM encoding, as it determines the sampling rate and directly affects the frequency and timing of the encoded digital signal.
- Observation of the PCM Data output shows that a simple analog input is transformed into a more complex digital pulse pattern, representing the binary encoding of the signal.
- When a variable DC voltage is applied, the PCM output changes continuously, demonstrating how the encoder generates different binary patterns in response to varying input amplitudes.
- Encoding a continuously changing signal such as a sinewave illustrates the sampling process clearly, with the Frame Synchronization (FS) signal indicating when each sample is taken.
