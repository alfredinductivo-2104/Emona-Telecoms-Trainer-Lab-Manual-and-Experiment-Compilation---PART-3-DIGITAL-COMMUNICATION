# UNDERSAMPLING IN SOFTWARE DEFINED RADIO

---

## INTRODUCTION:

In Software-defined radio (SDR), flexibility is achieved by converting incoming radio frequency (RF) signals into digital form and processing them through software rather than fixed hardware circuits. Since SDR systems may need to receive signals at very high carrier frequencies (such as 2.4 GHz in cellular communications), it might seem that the Analog-to-Digital Converter (ADC) must sample at extremely high rates according to the Nyquist criterion. However, this requirement mainly applies to baseband signals.

Most communication signals are bandwidth-limited bandpass signals, meaning their information is confined within a small bandwidth around a high carrier frequency and not near DC. According to Shannon's Information Theorem, all the information in such a signal can be captured by sampling at a rate at least twice its bandwidth—not necessarily twice its highest carrier frequency. This technique is called undersampling, also known as band-pass sampling or super-Nyquist sampling. For example, a 2.4 GHz carrier with a 30 kHz bandwidth can theoretically be sampled at just 60 kHz while still preserving all transmitted information, provided the sampling frequency is carefully chosen to avoid unwanted aliasing.

---

## OBJECTIVES:

In this experiment, we will be using the Emona Telecoms-Trainer 101 to set up a bandwidth limited signal. Then use undersampling in order to demodulate the bandwidth limited signal and recover the signal. Additionally, this experiment will allow the students to effects on the recovered message of mismatches between the modulated carrier bandwidth and the frequency used for undersampling. 

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



#### 1.1 OBSERVATION


### 2. Generating a DSSS signal using speech



#### 2.1 OBSERVATION




### 3. Using the Product Detector to Recover the Message



#### 3.1 OBSERVATION




### 4. Using the Product Detector to Recover the Message with Different PN sequence to the transmitter carrier


#### 4.1 OBSERVATION


### 5. DSSS and Deliberate Interference (Jamming)


#### 5.1 OBSERVATION


### 6. DSSS and Deliberate Interference Part 2 (Jamming)



#### 6.1 OBSERVATION


### 7. DSSS and Deliberate Interference Part 3 (Jamming)



#### 7.1 OBSERVATION



---

## LAB QUESTIONS AND ANSWERS:

**Q1: What feature of the Multiplier's output suggests that its basically a DSBSC signal?**



**Q2: Why is the DSSS signal so large when it's supposed to be small and indistinguishable from noise?**  



**Q3: Why isn't there any signal out of the DSSS modulator when you're not talking, etc?**  


**Q4: What does the signal out of the low pass filter look like?**  


**Q5: Why does using the wrong PN sequence for the local carrier cause the product detector output to look like this?**  



**Q6: Why doesn't the jamming signal interference with the recovery of the message ?**  



---

## CONCLUSIONS:
After analyzing the gathered data and observations about Undersampling in Software Define Radio, the following conclusions have been made:

