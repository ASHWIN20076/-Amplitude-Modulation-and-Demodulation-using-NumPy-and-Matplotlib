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
ac = 5
am = 2
fc = 2300
fm = 140
fs = 30000

# Time vector
t = np.arange(0, 2/fm, 1/fs)

# Message signal
e1 = ac * np.sin(2 * np.pi * fm * t)

plt.subplot(4,1,1)
plt.plot(t, e1)
plt.title("Message Signal")

# Carrier signal
e2 = ac * np.sin(2 * np.pi * fc * t)

plt.subplot(4,1,2)
plt.plot(t, e2)
plt.title("Carrier Signal")

# AM modulated signal
e3 = (ac + (am * np.sin(2 * np.pi * fm * t))) * np.sin(2 * np.pi * fc * t)

plt.subplot(4,1,3)
plt.plot(t, e3)
plt.title("AM Modulated Signal")

# Demodulation using Hilbert transform
demodulated_signal = np.abs(hilbert(e3)) - ac

plt.subplot(4,1,4)
plt.plot(t, demodulated_signal)
plt.title("Demodulated Signal")

plt.tight_layout()
plt.show()
```
 __Tabulation__:

![6e5b0954-70a5-4dd9-9e38-3006b266d0d6](https://github.com/user-attachments/assets/601a3bd6-cee1-40e1-a8ad-145e114b0913)


 __Output__:

<img width="865" height="603" alt="Screenshot 2026-03-12 112014" src="https://github.com/user-attachments/assets/3af659ef-a11d-45a6-8672-28770540ba93" />

 __Result__:

Thus Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib is experimentally done and the output is verified
