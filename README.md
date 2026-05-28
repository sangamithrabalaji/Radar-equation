# Radar-Range using scilab

**AIM:**

To calculate the maximum range of a radar system using the Radar Range Equation and verify the results through Python programming.

**Theory:**

The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum range at which a radar can detect a target. It is given by:

**Formula**

<img width="400" height="500" alt="image" src="https://github.com/user-attachments/assets/51129076-a796-4121-acad-0255c725b717" />

Procedure:

1.Start the program.

2.Define constants such as the speed of light and the value of pi.

3.Input all radar parameters — these include the transmitted power, antenna gain, wavelength, radar cross-section, and the minimum detectable power.

4.Assign a fixed wavelength value directly (do not calculate it).

5.Substitute all known values of transmitted power, antenna gain, wavelength, radar cross-section, and minimum detectable power into the radar range equation.

6.Perform the necessary mathematical operations in Scilab to compute the maximum radar detection range.

7.Display the computed range on the screen in meters.

8.End the program.

**program:**
```
clear;
clf();

c = 3e8;
f = 3e9;
lambda = c / f;
G_dB = 30;
G = 10^(G_dB / 10);
sigma = 1;
Pt_fixed = 100e3;
Pr_min = 1e-12;

R = 1000:500:100000;

num1 = Pt_fixed * (G^2) * (lambda^2) * sigma;
den1 = ((4 * %pi)^3) * (R.^4);
Pr = num1 ./ den1;
Pr_dBm = 10 * log10(Pr / 1e-3);

num2 = Pr_min * ((4 * %pi)^3) * (R.^4);
den2 = (G^2) * (lambda^2) * sigma;
Pt_req = num2 ./ den2;
Pt_req_dBW = 10 * log10(Pt_req);

subplot(2, 1, 1);
plot(R / 1000, Pr_dBm, "r-", "linewidth", 2);
xtitle("Received Power vs. Radar Range", "Range (km)", "Received Power (dBm)");
xgrid();

subplot(2, 1, 2);
plot(R / 1000, Pt_req_dBW, "b-", "linewidth", 2);
xtitle("Required Transmitted Power vs. Radar Range", "Range (km)", "Required Transmitted Power (dBW)");
xgrid();

```
**output:**

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/37ed1349-ba4d-437a-a2a2-29ebf69f9056" />

**Tabulation:**




**Result:**
Thus, the maximum range of a radar system using the Radar Range Equation is verified using scilab

