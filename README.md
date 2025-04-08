# Ideal-Sampling
# Aim

The aim of this program is to demonstrate the concept of ideal sampling by discretizing a continuous signal at
regular intervals. It visualizes both the continuous signal and its corresponding discrete samples to illustrate the sampling process in signal processing.

# Tools required

Python: A versatile programming language used for scientific computing and signal processing. NumPy: A powerful numerical library in Python for performing array-based operations and mathematical computations. Matplotlib: A plotting library for generating high-quality graphs and visualizations of data, essentialfor demonstrating the sampling process.

# Program
```
import numpy as np

import matplotlib.pyplot as plt

fs = 100  # Sampling frequency (samples per second)

f = 5  # Frequency of the sine wave (in Hz)

T = 1 / f  # Period of the sine wave

t_continuous = np.linspace(0, 1, 1000)  # High-resolution time array for continuous signal

t_sampled = np.arange(0, 1, 1/fs)  # Time points for ideal sampling

continuous_signal = np.sin(2 * np.pi * f * t_continuous)

sampled_signal = np.sin(2 * np.pi * f * t_sampled)

fig, axs = plt.subplots(2, 1, figsize=(12, 8))

axs[0].plot(t_continuous, continuous_signal, label="Continuous Signal (Sine Wave)", color='b', linewidth=2)

axs[0].set_title("Continuous Sine Wave")

axs[0].set_xlabel("Time [s]")

axs[0].set_ylabel("Amplitude")

axs[0].grid(True)

axs[0].legend(loc="best")

axs[1].plot(t_continuous, continuous_signal, label="Continuous Signal", color='b', alpha=0.7)

axs[1].stem(t_sampled, sampled_signal, 'r', markerfmt='ro', basefmt=" ", linefmt='r-', label="Ideal Samples")

axs[1].set_title("Ideal Sampling of the Sine Wave")

axs[1].set_xlabel("Time [s]")

axs[1].set_ylabel("Amplitude")

axs[1].grid(True)

axs[1].legend(loc="best")

plt.tight_layout()

plt.show()
```
# Output Waveform
![image](https://github.com/user-attachments/assets/c8e3466f-ac5b-4588-94a1-4fb32c34b55c)

![image](https://github.com/user-attachments/assets/ab795b79-dac8-4cf0-8aac-02fd2c2eb0c3)

# Results

The results show two plots: the first displays a continuous sine wave with a 5 Hz frequency. The second plot illustrates the ideal sampling of the sine wave, where the samples (red dots) are taken at regular intervals (100 Hz sampling rate). The ideal samples perfectly match the continuous signal, with no distortion or aliasing, as the sampling rate is sufficiently high.

