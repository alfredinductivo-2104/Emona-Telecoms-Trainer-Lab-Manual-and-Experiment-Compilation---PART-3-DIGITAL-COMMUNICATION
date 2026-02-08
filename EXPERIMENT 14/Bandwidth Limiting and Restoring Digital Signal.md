# BANDWIDTH LIMITING AND RESTORING DIGITAL SIGNALS

---

## INTRODUCTION:


---

## OBJECTIVES:


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




#### 1.1 OBSERVATION



### 2. PCM Encoder with VCO input



#### 2.1 OBSERVATION



### 3. Decoding the PCM Data



#### 3.1 OBSERVATION



### 4. Encoding and Decoding Speech



#### 4.1 OBSERVATION

 />

### 5. Recovering the Message



#### 5.1 OBSERVATION



---

## LAB QUESTIONS AND ANSWERS:

**Q1: What does the PCM Decoder stepped output tell you about the type of signal that is?  **

The stepped output of the PCM Decoder shows that the signal is a pulse-amplitude modulated (PAM) version of the original analog signal. Each step corresponds to a discrete voltage level representing a sampled value of the original signal.

**Q2: What must be done to the PCM Decoder Module output to reconstruct the message properly? **  

To properly reconstruct the original message, the stepped output must be passed through a low-pass filter. This smooths out the steps and produces a continuous analog signal that approximates the original waveform.

**Q3: Even though the two signals look and sound the same, why isn't the reconstructed message a perfect copy of the original message? ** 

The reconstructed message isn’t perfect because of quantization error. Each sample is rounded to the nearest quantization level during encoding, so some small differences between the original and decoded signals are inevitable. Additionally, any sampling or filtering limitations may also introduce minor distortions.

---

## CONCLUSIONS:
After analyzing the gathered data and observations about PCM Decoding, the following conclusions have been made:

