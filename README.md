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
