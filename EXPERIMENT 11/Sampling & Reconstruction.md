# SAMPLING & RECONSTRUCTION

---

## INTRODUCTION:

As the world of telecommunications evolves day by day, digital transmission has largely superseded analog methods due to its superior resistance to electrical noise and interference. However, because natural signals like speech and music are inherently analog, they must first undergo a conversion process to be transmitted digitally. This process begins with sampling, where the continuous voltage of an analog message is measured at precise, regular intervals this depends of the systems requirements. While sampling only captures discrete pieces of a message, the original signal can be recovered through the principles of frequency multiplication. Additionally, the reconstruction of the signal is made possible by passing the sampled data through a low-pass filter, which isolates the original message by rejecting the higher-frequency harmonics and sidebands created during the sampling process.

---

## OBJECTIVES:

In this experiment, we will be able to use the Emona Telecoms-Trainer to produce a sample message signal using natural sampling and a sample and hold scheme. Additionally, we will be able to understand how to properly reconstruct a message signal and examine the effect of aliasing to the signal.

---

## EQUIPMENT TO BE USED:
1. Emona Telecoms-Trainer 101 (plus power-pack)
2. Dual channel 20Mhz Oscilloscope
3. Two Emona Telecoms-Trainer Oscilloscope lead
4. Assorted Emona Telecoms-Trainer 101 patch leads
5. One set of Headphones (stereo)

---

## SUMMARY OF FINDINGS AND RESULTS:

### 1. Sampling a Simple Message

In the first part of the experiment, using the ETT-101 Dual Analog Switch Module and an 8 kHz digital and sine signal, we are able to sample a message signal. Refer to the connections shown in the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/3eb6d284-ed34-43e8-af95-a1d5cc44d607" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/19ab760e-97f0-483a-9115-a908d2adb366" />

#### 1.1 OBSERVATION

After constructing the given circuit, we are able to obtain the message signal, as seen in the figure below. As observed, the signal appears highly distorted in comparison to the original signal (red waveform). Additionally, the peak-to-peak voltage (Vpp) of the message signal was very low compare to the original but the frequency of the signal increases significantly from 2.08 Khz to 7.85 Khz. 

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/1fa11ca3-5197-4156-9942-eb321f44fe4f" />

### 2. Sampling Speech

In the next part of the experiment, we use the speech module to simulate a real voice application. This allows the system to process a more practical input signal and demonstrate how sampling affects real-world audio signals compared to ideal test waveforms. Refer to the connections shown in the figure below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/a84f4541-a1fd-49c5-a055-c5924df98e0a" />

#### 2.1 OBSERVATION

As we hum or speak into the microphone, it is observed that the output changes depending on the tone of the input voice signal. When the voice tone is higher and clearer, the output signal becomes more stable and resembles a digital signal (as seen in the figure below). Additionally, the parameters such as the frequency, Vpp, Maximum (Ma) and Minimum (Mi) voltage changes depending on the tone and clarity of the inputted voice signal. 

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/fdb7d794-dad4-49e9-a655-fd7b202c8d4a" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/6338912f-a570-4a30-99f9-4a16ff901565" />

### 3. Reconstructing a Message Signal

In this part of the experiment, using the sampled message signal from the first part, we will reconstruct the signal to a more continuous form, aiming to closely resemble the original message signal before sampling. Refer to the connections shown in the figure and block diagram below.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/725e2aab-2ba1-4848-89ed-fc709fa6d5db" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/f3fa70da-2f0a-4797-bf2c-ad5ccebc457f" />


#### 3.1 OBSERVATION

As observed in the output, the signal initially did not resemble the original signal. As seen in the first figure below, the output was nearly flat. However, when the gain was set to the middle and the cut-off frequency fully counterclockwise, the recovered message signal began to resemble the original signal, as shown in the second figure.

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/97d4b339-0063-4a62-aeba-e906823c5776" />

<img width="500" height="380" alt="image" src="https://github.com/user-attachments/assets/78ccf5dc-d266-419b-a719-1bb20522165d" />

https://github.com/user-attachments/assets/e0860a3c-3797-44b9-95bb-5a021905cc98

---

## LAB QUESTIONS AND ANSWERS:

**Q1: What type of sampling is shown in the first part of the experiment? and What two features of the sampled signal confirm this?**

The output shown was a Natural Sampling.
This was a Natural Sampling because the sample voltages was affected during the sampling and the signal's voltage returns to zero volts between the samples. 

**Q2: What two features of the sampled signal confirm that the set-up models the sample-and-hold scheme?**  

The first feauture that shows that the sampled signal upholds a sample-and-hold scheme is there are no spaces found in between the samples. Then, the sample voltages doesn't change during the sampling process. 

**Q3: What’s the name of the distortion that appears when the VCO module’s Frequency Adjust control is turned far enough?**  

Aliasing

**Q4: Given the message is a 2kHz sinewave, what’s the theoretical minimum frequency for the sampling signal?**

4kHz (2 × 2kHz)

**Q5: Why is the actual minimum sampling frequency higher than the theoretical minimum that you calculated for Question 4?**

The actual minimum sampling frequency higher than the theoretical minimum calculated because the filters are not that accurate and their cut off are not instantenous.

---

## CONCLUSIONS:
After analyzing the gathered data and observations about Sampling and Reconstruction of a signal, the following conclusions have been made:
- Digital transmission requires analog signals to be converted into discrete samples for effective processing and transmission.
- Sampling a signal using the ETT-101 Dual Analog Switch Module successfully captures discrete values of the original message signal.
- Natural sampling was observed, as the signal’s voltage returns to zero between samples, and sample amplitudes vary with the original signal.
- The sample-and-hold scheme was demonstrated, with each sample holding a constant voltage during the sampling interval and no gaps between samples.
- Signal reconstruction using a low-pass filter restores the sampled signal to closely resemble the original, with the proper adjustments to gain and cut-off frequency improving fidelity.
- Aliasing occurs when the sampling frequency is too low, highlighting the importance of adhering to the Nyquist criterion.


