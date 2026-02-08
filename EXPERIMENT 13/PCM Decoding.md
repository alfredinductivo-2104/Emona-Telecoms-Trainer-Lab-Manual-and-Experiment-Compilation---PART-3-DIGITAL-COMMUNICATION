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

### 1. Sampling a Simple Message



#### 1.1 OBSERVATION



### 2. Sampling Speech



#### 2.1 OBSERVATION



### 3. Reconstructing a Message Signal




#### 3.1 OBSERVATION



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
