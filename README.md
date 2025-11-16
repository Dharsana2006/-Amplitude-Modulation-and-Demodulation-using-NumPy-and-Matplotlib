# -Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib

__Aim__: 

To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries. 

__Apparatus Required__: 

Software: Python with NumPy and Matplotlib libraries 
Hardware: Personal Computer

__Theory__: 

Amplitude Modulation (AM) is a technique used in electronic communication, primarily for transmitting 
information via a radio carrier wave. In AM, the amplitude of the carrier wave is varied in proportion to that of 
the message signal. The general form of an AM signal is: 


__Algorithm__:
1. Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency. 
2. Generate Time Axis: Create a time vector for the signal duration. 
3. Generate Message Signal: Define the message signal as a cosine wave. 
4. Generate Carrier Signal: Define the carrier signal as a cosine wave. 
5. Modulate Signal: Apply the AM formula to obtain the modulated signal. 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

__Program__:
```
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import hilbert

# Parameters
A_c = 1.0  # Carrier amplitude
f_c = 100  # Carrier frequency in Hz
f_m = 5    # Message frequency in Hz
A_m = 0.5  # Message amplitude
sampling_frequency = 1000  # Sampling frequency in Hz
duration = 1  # Duration of the signal in seconds

# Time axis
t = np.linspace(0, duration, int(sampling_frequency * duration))

# Message Signal
m_t = A_m * np.cos(2 * np.pi * f_m * t)

# Carrier Signal
c_t = A_c * np.cos(2 * np.pi * f_c * t)

# Amplitude Modulation (AM) Signal
s_t = (1 + m_t) * c_t

# AM Demodulation using Hilbert Transform
analytic_signal = hilbert(s_t)
envelope = np.abs(analytic_signal)
demodulated_message = (envelope - A_c) / A_m

# Plotting the Results
plt.figure(figsize=(12, 10))

# Original Message Signal
plt.subplot(4, 1, 1)
plt.plot(t, m_t)
plt.title('Original Message Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)

# Carrier Signal
plt.subplot(4, 1, 2)
plt.plot(t, c_t)
plt.title('Carrier Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)

# Amplitude Modulated (AM) Signal
plt.subplot(4, 1, 3)
plt.plot(t, s_t)
plt.title('Amplitude Modulated (AM) Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)

# Demodulated Signal
plt.subplot(4, 1, 4)
plt.plot(t, demodulated_message)
plt.title('Demodulated Signal')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)

plt.tight_layout()
plt.show()
```
 __Output__:
<img width="1198" height="990" alt="image" src="https://github.com/user-attachments/assets/8dde20cf-30a3-4785-a4da-554a97ceba00" />

__Tabulation__:
![WhatsApp Image 2025-11-16 at 10 09 27_8ce46b82](https://github.com/user-attachments/assets/e74ba9c4-a8a8-4097-a0da-af33a3f848c3)

__Calculation__:
![WhatsApp Image 2025-11-16 at 10 10 41_97377f7e](https://github.com/user-attachments/assets/94d1b090-b327-4ff8-83dd-40568fd62842)


 __Result__:
<img width="1262" height="463" alt="image" src="https://github.com/user-attachments/assets/941ad854-58e0-4b17-b04b-1000c10e5e6b" />


 


