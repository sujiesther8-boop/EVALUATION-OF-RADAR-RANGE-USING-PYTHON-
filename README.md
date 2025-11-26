# EVALUATION-OF-RADAR-RANGE-USING-PYTHON-

__Aim__:

To calculate the maximum range of a radar system using the Radar Range Equation and verify the results 
through Python programming.

__Theory__:

The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum 
range at which a radar can detect a target. It is given by:

<img width="573" height="442" alt="image" src="https://github.com/user-attachments/assets/ba374d30-d11f-41e5-a4fc-a42dde71d8e7" />

__Procedure__:

1. Set Up the Python Environment: Ensure that Python is installed on your system. You can use 
Anaconda for managing Python packages and environments, or any other Python IDE of your choice. 
2. Import Necessary Libraries: Import the math library in Python. 
3. Define the Radar Range Equation Function: Create a function to calculate the maximum range using 
the Radar Range Equation. 
4. Input Parameters for the Radar System: Define the input parameters such as transmitted power, 
transmitter gain, receiver gain, radar frequency, radar cross section, and minimum detectable power. 
5. Calculate the Maximum Range: Use the function to calculate the maximum range of the radar. 
6. Execute the Program: Run the Python script to calculate and display the maximum range of the radar.


   # ALGORITHM
 1.Take input radar parameters.
 
 2.Convert all dB values to linear.
 
 3.Calculate wavelength ( \lambda = c/f ).
 
 4,Calculate minimum detectable power ( P_{min} ).
 
 5.Apply radar range equation.
 
 6.Compute and output maximum radar range ( R_{max} ).

# Program:
```
clc
clear;
close;

Pt = 1000;
G = 40;
lambda = 0.05;
sigma = 10;
pi4 = (4*%pi)^3;

R = linspace(1e3, 200e3, 500);
Pr_R = (Pt .* G^2 .* lambda^2 .* sigma) ./ (pi4 .* R.^4);
figure(1);
Pr_R_dB = 10 .* log10(Pr_R);
plot(R/1000, Pr_R_dB);
xlabel("Power Received");
ylabel("Range");

Pt_values = linspace(100, 10000, 500);
R_fixed = 50e3;
Pr_Pt = (Pt_values .* G^2 .* lambda^2 .* sigma) ./ (pi4 .* R_fixed.^4);
figure(2);
plot(Pt_values, Pr_Pt);
xlabel("Power Received");
ylabel("Power Transmitted");

G_values = linspace(5, 60, 500);
Pt_fixed = 3000;
Pr_G = (Pt_fixed .* G_values.^2 .* lambda^2 .* sigma) ./ (pi4 .* R_fixed.^4);
figure(3);
plot(G_values, Pr_G);
xlabel("Power Received");
ylabel("Gain");
```
# Tabulation:

![WhatsApp Image 2025-11-26 at 6 48 06 PM](https://github.com/user-attachments/assets/61d60484-5145-4da2-9d2e-37477c8da75f)

   __Output__:
   
<img width="764" height="597" alt="Screenshot 2025-11-16 234045" src="https://github.com/user-attachments/assets/69a6db4d-9dbb-4b4e-b083-6599e377c7fd" />

<img width="747" height="593" alt="image" src="https://github.com/user-attachments/assets/a468c088-2226-427a-8ffd-9e3da8063807" />

<img width="761" height="639" alt="image" src="https://github.com/user-attachments/assets/8a61794b-46ae-4b7a-a59d-460de3f2add6" />

   # RESULT 
![WhatsApp Image 2025-11-26 at 6 48 27 PM](https://github.com/user-attachments/assets/25e88248-67e0-4c11-9f3b-b05ebc476964)



