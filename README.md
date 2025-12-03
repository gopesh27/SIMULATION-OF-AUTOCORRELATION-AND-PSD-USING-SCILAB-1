# SIMULATION-OF-AUTOCORRELATION-AND-PSD-USING-SCILAB-1

__AIM:__

Write a program for Autocorrelation and PSD of signals in SCILAB and verify Wiener-Khinchin relation. 


__EQUIPMENTS Needed:__

.Computer with i3 Processor 

.SCI LAB


__THEORY:__

The Wiener-Khinchin theorem states that the power spectral density of a wide sense stationary random process is the 
Fourier transform of the corresponding autocorrelation function.

__Algorithm:__

 1.Load or Define the Signal: Input your time-domain signal. 

 2.Compute Autocorrelation: Calculate the autocorrelation function of the signal.

3.Compute Power Spectral Density (PSD): Estimate the PSD of the signal, either directly using a method like
Welch’s periodogram or by using the Fourier transform of the autocorrelation.

4.Plot Results: Visualize the autocorrelation function and PSD. 

__PROCEDURE:__


Refer Algorithms and write code for the experiment. 

Open SCILAB in System 

Type your code in New Editor 

Save the file 

Execute the code 

If any Error, correct it in code and execute again 

Verify the generated waveform using Tabulation and Model Waveform 

__PROGRAM:__
~~~
iSmport numpy as np 
import matplotlib.pyplot as plt 
from scipy.signal import hilbert 
# Parameters 
A_c = 1.0 # Carrier amplitude 
f_c = 100 # Carrier frequency in Hz 
f_m = 5 # Message frequency in Hz 
A_m = 0.5 # Message amplitude 
sampling_frequency = 1000 # Sampling frequency in Hz 
duraƟon = 1 # DuraƟon of the signal in seconds
# Time axis 
t = np.linspace(0, duraƟon, int(sampling_frequency * duraƟon))
# Message Signal 
m_t = A_m * np.cos(2 * np.pi * f_m * t) 
# Carrier Signal 
c_t = A_c * np.cos(2 * np.pi * f_c * t) 
# Amplitude ModulaƟon (AM) Signal
s_t = (1 + m_t) * c_t 
# AM DemodulaƟon
# 1. Compute the analyƟc signal using the Hilbert transform
analyƟc_signal = hilbert(s_t)
# 2. Extract the envelope of the analyƟc signal
envelope = np.abs(analyƟc_signal)
# 3. Demodulate the signal by removing the DC offset and dividing by the carrier amplitude 
demodulated_message = (envelope - A_c) / A_m 
# Ploƫng the Results
plt.figure(figsize=(12, 10)) 
# Original Message Signal 
plt.subplot(4, 1, 1) 
plt.plot(t, m_t) 
plt.Ɵtle('Original Message Signal') 
plt.xlabel('Time [s]') 
plt.ylabel('Amplitude') 
plt.grid(True) 
# Carrier Signal 
plt.subplot(4, 1, 2) 
plt.plot(t, c_t) 
plt.Ɵtle('Carrier Signal') 
plt.xlabel('Time [s]') 
plt.ylabel('Amplitude') 
plt.grid(True) 
# Amplitude Modulated (AM) Signal 
plt.subplot(4, 1, 3) 
plt.plot(t, s_t) 
plt.Ɵtle('Amplitude Modulated (AM) Signal') 
plt.xlabel('Time [s]') 
plt.ylabel('Amplitude') 
plt.grid(True) 
# Demodulated Signal
plt.subplot(4, 1, 4) 
plt.plot(t, demodulated_message) 
plt.Ɵtle('Demodulated Signal') 
plt.xlabel('Time [s]') 
plt.ylabel('Amplitude') 
plt.grid(True) 
plt.Ɵght_layout()
plt.show()
~~~
__OUTPUT:__

![WhatsApp Image 2025-12-03 at 16 36 44_fb7f76af](https://github.com/user-attachments/assets/81b9da69-4f8e-4e5a-996c-10c6f033a328)

__RESULT:__

Thus,the Autocorrelation of X and Y is verified.
