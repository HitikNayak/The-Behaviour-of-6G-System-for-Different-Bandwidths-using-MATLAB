# The-Behaviour-of-6G-System-for-Different-Bandwidths-using-MATLAB

# Shannon Capacity MATLAB Project

## Overview

This project demonstrates the implementation of the Shannon-Hartley Capacity Theorem in MATLAB. The channel capacity is plotted against Signal-to-Noise Ratio (SNR) for different bandwidth values.

## Formula

The Shannon Capacity formula is:

C = B log2(1 + SNR)

Where:

- C = Channel Capacity (bps)
- B = Bandwidth (Hz)
- SNR = Signal-to-Noise Ratio (Linear Scale)


## Sub-Tera Hertz System

The SINR (Signal-to-Interference-plus-Noise Ratio) of the 6G Sub-Tera Hertz system is defined as:

$$
S(y)=\frac{P_A G_A G_U S_F U_F}
{(N_0W+I)L(y)}
$$

The Spectral Efficiency is given by:

$$
R=\log_2\left(1+S(y)\right)
$$

### Parameters

| Symbol | Description |
|----------|----------|
| S(y) | SINR for user y |
| Pₐ | Transmitted Power |
| Gₐ | Antenna Gain at Base Station |
| Gᵤ | Antenna Gain at User End |
| Sᶠ | Shadow Fading |
| Uᶠ | User Fraction |
| N₀ | Noise Power Spectral Density |
| W | Channel Bandwidth |
| I | Interference |
| L(y) | Channel Loss |

### Frequency Range

**100 GHz – 300 GHz (Sub-THz Band)**

The Sub-Tera Hertz spectrum is considered one of the key technologies for future 6G systems due to its capability to support ultra-high data rates, low latency, and massive connectivity.



---

## MATLAB Code

```matlab
clc;
clear;
close all;

B = [20e3 25e3 30e3];
SNR_dB = 2:30;

C = zeros(length(B), length(SNR_dB));

for j = 1:length(B)
    for i = 1:length(SNR_dB)
        SNR_lin = 10^(SNR_dB(i)/10);
        C(j,i) = B(j) * log2(1 + SNR_lin);
    end
end

figure;
hold on;

plot(SNR_dB,C(1,:),'-o','LineWidth',1.5,...
    'DisplayName','B = 20 kHz');

plot(SNR_dB,C(2,:),'-d','LineWidth',1.5,...
    'DisplayName','B = 25 kHz');

plot(SNR_dB,C(3,:),'-h','LineWidth',1.5,...
    'DisplayName','B = 30 kHz');

hold off;

xlabel('SNR (dB)');
ylabel('Shannon Capacity (bps)');
title('Shannon Capacity vs SNR for Different B.W');
legend('show');
grid on;
```

---

## Output Graph

The following graph shows the variation of Shannon Capacity with SNR for different bandwidth values (20 kHz, 25 kHz, and 30 kHz).

![Shannon Capacity Graph](Shannon%20Fano%20Graph.png)


## 📊 Spectral Efficiency for Different Bandwidths

The following figure illustrates the variation of **Spectral Efficiency (R)** with **User Fraction (UF)** for different bandwidths and scaling factors in a 6G Sub-Tera Hertz communication system.

### Mathematical Model

The Signal-to-Interference-plus-Noise Ratio (SINR) for user \(y\) is defined as:

$$
S(y)=\frac{P_A G_A G_U S_F U_F}
{(N_0W+I)L(y)}
$$

where:

| Parameter | Description |
|------------|------------|
| $P_A$ | Transmitted Power |
| $G_A$ | Antenna Gain at Base Station |
| $G_U$ | Antenna Gain at User End |
| $S_F$ | Shadow Fading |
| $U_F$ | User Fraction |
| $N_0$ | Noise Power Spectral Density |
| $W$ | Channel Bandwidth |
| $I$ | Interference |
| $L(y)$ | Channel Loss |

The Spectral Efficiency is calculated as:

$$
R=\log_2(1+S(y))
$$

### Simulation Parameters

- **Frequency Range:** 100 GHz – 300 GHz (Sub-THz)
- **Bandwidths:** 10 MHz and 20 MHz
- **Scaling Factors:** 0.20, 0.22, 0.24

### Output Graph

![Spectral Efficiency for Different Bandwidths](Spectral%20Efficiency%20for%20different%20Bandwidths.png)

### Key Observations

✅ Spectral efficiency increases with increasing **User Fraction (UF)**.

✅ Higher **Scaling Factors** provide better spectral efficiency.

✅ For a constant user fraction, spectral efficiency is higher for larger scaling factors.

✅ The graph demonstrates how bandwidth allocation and user density affect the performance of future **6G Sub-Tera Hertz communication systems**.

### Conclusion

The simulation highlights the relationship between user fraction, scaling factor, and bandwidth in determining spectral efficiency. These results are useful for designing high-capacity and energy-efficient 6G wireless networks operating in the Sub-THz spectrum.


## Results

- Channel Capacity increases with increasing SNR.
- Higher bandwidth provides greater channel capacity.
- The relationship follows Shannon's theorem accurately.

---

## Applications

- Wireless Communication
- Mobile Networks
- Satellite Communication
- Optical Communication
- Information Theory

---

## Author

**Hitik Kumar Nayak**

B.Tech Electronics & Communication Engineering (ECE)

MATLAB | VLSI | Web Development | GATE ECE
