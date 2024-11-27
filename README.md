java cECE303: Real Time Digital Signal Processing Final Project: Cool Guitar Effects 
Special effects for guitars are a fun application of DSP. In this project, you would be creating three guitar effects using Real time DSP techniques learned in previous labs.  
1. Primary Reference 
(1) Primary reference for the project will be Chapter 10: Guitar Special Effects. Chapter covers relevant theory and provides few sample examples. It is highly recommended to understand the chapter before starting the project. Chapter 10.2 and Chapter 10.5 are very important for your understanding. Please make sure you read them and understand most of the contents in these two sections.
(2) This final project consists of three parts as described below
a. Creating Echo effect 
b. Creating Flanging effect 
c. Creating Chorus effect 
(3) WINDSK already has these audio effects implemented. Refer to Chapter 3, section 3.2.3 for more details. Check out these effects in WINDSK to get an understanding of how these effects sound. 
2. Assignment 1: Delay + Echo Effect 
(1) Theory
The delay effect is a very simple time-based guitar effect generated using the following FIR (finite impulse response) difference equation (Fig 10.1 in textbook)
y(n) = x(n) + x(n - D)
The direct signal x(n) is added to a single attenuated and delayed copy of itself α . x(n - D)   The delay D   represents the round-trip travel time from the source to a reflecting surface.   The coefficient α is a measure of the reflection and propagation losses, such that |α|   ≤ 1.
The echo effect is a multiple delay effect. The direct signal is now added to several attenuated and delayed copies of itself. For example, using three successive delays, the echo difference equation becomes

If an infinite number of successive delays are added, using z-transforms and a geometric series summation, the echo difference equation can be represented recursively as

This IIR (infinite impulse response) difference equation roughly imitates the reverberating nature of a room. (Fig 10.2 in textbook).
(2) Tasks
a. Implement multiple echo effect using IIR filters   as shown in Fig 10.2 in textbook. Feel free to use codec based ISR or EDMA based frame. approach, whichever you are more comfortable with.
b. Adjust the delay of echo so that it imitates the reverberating nature of a room. Set the gain value α for echoed sample as 0.75. Make one channel talk through and the other channel having echo effect to compare the two.
(3) Hints
a. Read Chapter 10.5 in the textbook, try to understand how the code works.
b. If you would like to use codec based ISR to implement multiple echo effect using IIR filters, feel free to use this code in Book3rdEdition\code\chapter10\ccs\Echo\ISRs_B.c (Implement IIR filter) in your CCS project.
c. Remember to include Echo.h, Echo.gel, as well as StartUp.c in this folder to your CCS project. 
(4) Assignment 1 Submission 
Save this project as “Echo Effect”, and you will need to submit it as one of the assignments. 
3. Assignment 2: Flanging Effect 
(1) Theory
The flanging effect is similar to the delay effect, except the amount of delay now varies dynamically with time (Fig 10.11). The basic FIR difference equation is

where is a periodically varying delay value between 0 and 2 msec, with a low frequency no greater than 1 Hz.   Flanging uses very short delays, while the previous delay and echo effects use much longer delays. The shorter delays of flanging give rise to comb filtering. It is the variance of the comb filter via the varying delay that gives flanging its sound. The flanging effect pr代 写ECE303: Real Time Digital Signal Processing Final Project: Cool Guitar EffectsR
代做程序编程语言oduces a pronounced whooshing sound, similar to a jet aircraft on taking off.
(2) Tasks
a. Implement flanging effect as shown in Fig 10.11. Feel free to use codec based ISR or EDMA based frame. approach, whichever you are more comfortable with.
b. You would need to generate a sinusoidal varying delay to achieve this effect. Make one channel talk through and other channel having flanging effect to compare the two.
(3) Hints
a. For creating sinusoidally varying delay times for effects such as a flanger or chorus, consider creating the sinusoidal values for  in the StartUp.c module. You don’t want to put something like that inside an ISRs.c which executes over and over again at the rate of the sample clock.

where:
is the maximum number of sample delays 
is some low frequency, no greater than 1 Hz 
b. If you would like to use codec based ISR to implement flanging effect, feel free to use this code in Book3rdEdition\code\chapter10\ccs\Echo\ISRs_B.c (Implement FIR filter) in your CCS project.
c. Remember to include Echo.h, Echo.gel, as well as StartUp.c in this folder to your CCS project.
d. Remember to modify the StartUp.c for creating the sinusoidal values for  
(4) Assignment 2 Submission 
Save this project as “Flanging Effect”, and you will need to submit it as one of the assignments. 
4. Assignment 3: Chorus Effect 
(1) Theory
Block diagram of Chorus effect is shown in Fig 10.12 in textbook. To generate a chorus effect that makes one musician sound similar to four musician playing the same notes, three separate chorus signals (identical to flanging except having longer delay times) are summed with the original signal.
(2) Tasks
a. Implement chorus effect as shown in Fig 10.12. Feel free to use codec based ISR or EDMA based frame. approach, whichever you are more comfortable with.
b. Make one channel talk through and other channel having chorus effect to compare the two.
(3) Hints
a. Remember to include Echo.h, Echo.gel, as well as StartUp.c in this folder to your CCS project.
b. Remember to modify the StartUp.c for creating the sinusoidal values for  
(4) Assignment 3 Submission 
Save this project as “Chorus Effect”, and you will need to submit it as one of the assignments. 
5. For your submission of the Final Project:  
(1) The entire completed CCS project for Section 2 
(2) The entire completed CCS project for Section 3 
(3) The entire completed CCS project for Section 4 
(4) A word document explaining the following:  
i. your procedure of implementing the Echo effect and how this effect sounds like 
ii. your procedure of implementing the Flanging effect and how this effect sounds like 
iii. your procedure of implementing the Chorus effect and how this effect sounds like 
(5) Compress all above into one single zip file and name it with your Full Name and your partner’s Full Name. Thanks! 
6. Grading Guide  
(1) Project forms 20% of the overall course grade. 80% of the grades would correspond to assignments.
(2) Project Grading is as follows
a. Echo effect - 20 % based on algorithm used, and the correctness of your code
b. Flanging effect - 40 % based on algorithm used, and the correctness of your code
c. Chorus effect - 30 % based on algorithm used, and the correctness of your code
d. Remaining 10 % of the grade will be based on how correct your effect sounds! If your effect sounds as expected, you will get full credit. (You can check out these effects in WINDSK to get an understanding of how these effects sound. Chapter 3.2.3) 







         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
