# Syllabus
## 3.1 Spectral Analysis
- Energy Spectral Density (ESD) (2)(4)  
- ESD of sinc Signal +Eg (3+2)
## 3.3 Signal Energy and Power
- Energy and Power Signal (2)  
- Bandwidth of System +Fig (2)  
- Properties of Energy Signal (3)  
- Rayleigh Energy Theorem (2)(4)(6)  
- Power from FS Coefficients (2)  
- Energy Vs Power Test +Eg (5)(6)(4)  
- AC Function Vs ESD (Fourier Pair) (4)  
- Energy & Power of Unit Step Signal (5)
## 3.4 Parseval’s Theorem  (2)(3)
## 3.5 Power Spectral Density Function  (2)(4)  
- ESD & PSDF (2)(4)  
- PSDF Derivation (4)(6)  
- Analog Spectrum Analyzer +Fig (6)(8)  
- PSD & Average Power of Periodic Signal +Eg (6)
## 3.6 Autocorrelation (AC) Function & Relation with PSDF  
- Autocorrelation Function (1)(3)  
	- Properties (3)(5)  
- White Noise (3)  
	- PSDF of White Noise (2)  
	- AC Function of White Noise (3)  
	- PSDF Vs AC Function +Eg (3)(4)(6)  
- AC Function of White Noise using PSD +Fig (4)  
-  PSD of Output of LTI System (I) (5)  
- Autocorrelation of Cosine Signal +Eg (3)  
- Autocorrelation, Cross-Correlation & Convolution (Graphical) (3+3)
# Theory
## 3.1 Review of Fourier Series & Transform
### Fourier Series
- Repr of periodic signal by linear combn of sines & cosines or complex exp
- Trigo FS : Sines & Cosines combined
- Cmpx Exp FS : Exp combined

 ![[Pasted image 20260101192036.png]]
 ![[Pasted image 20260101192046.png]]
 ![[Pasted image 20260101192058.png]]
 ![[Pasted image 20260101192106.png]]
 ![[Pasted image 20260101192118.png]]
### Fourier Transform
-  ![[Pasted image 20260101192147.png]]
- ![[Pasted image 20260101192153.png]]
- ![[Pasted image 20260101192159.png]]
### Fourier Transform Properties (4)(5)  
1. Time Scaling  
	![[Pasted image 20260101192459.png]]
2. Time Shifting
	![[Pasted image 20260101192824.png]]
3. Freq Shifting
	![[Pasted image 20260101192831.png]]
4. Linearity
	![[Pasted image 20260101192558.png]]
5. Duality / Symmetry
	![[Pasted image 20260101192719.png]]
6. Time differentiation
	![[Pasted image 20260101192842.png]]
7. Convolution
	![[Pasted image 20260101192850.png]]
8. Modulation  
## 3.2 Spectral Analysis
	- Energy Spectral Density (ESD) (2)(4)  
	- ESD of sinc Signal +Eg (3+2)

- Describes time series fxn by comparing them to sines & cosines
## 3.3 Energy Signals (2)
- Signal x(t) with finite E (0 < E < inf) & 0 Avg power (P = 0)
- For E to be finite
	- Singal amp x(t) --> 0 as | t | --> inf
- Almost all practical non periodic signals defined over finite time (limited time signals) 
- Expression
	- ![[Pasted image 20260101194624.png]]
### Parseval’s Theorem for energy signals (2)(3)
	- Rayleigh Energy Theorem (2)(4)(6)  
- Statement : 
	- E of a signal may be obtained with help of its FT
	- If we know X(w), we can det E of signal without knowing its T domain
- ![[Pasted image 20260101194726.png]]
- ![[Pasted image 20260101194735.png]]
### Energy Spectral Density (ESD)
	- Power from FS Coefficients (2)  
	- Energy Vs Power Test +Eg (5)(6)(4)  
	- Energy & Power of Unit Step Signal (5)
#### Bandwidth of System +Fig (2)  
- Let, Ideal LPF
	- ![[Pasted image 20260103124719.png]]
	- TF : ![[Pasted image 20260103124731.png]]
	- Freq response of sys : Y(w) = X(w) . H(w)
	- Eo of O/P signal y(t) represents contribution of E due to BW del w
		- ![[Pasted image 20260103124808.png]]
		- ![[Pasted image 20260103124821.png]]
	- ![[Pasted image 20260103124828.png]]
	- E contribution per unit BW
		- ![[Pasted image 20260103124932.png]]
		- | X(w) | ^2 --> E per unit BW  AKA ESD
		- Denoted by ![[Pasted image 20260103125032.png]]
	- ![[Pasted image 20260103125037.png]]
#### Properties of Energy Signal (3)  
1. Total area under ESD fxn = Total E of that Signal
	- ![[Pasted image 20260103125258.png]]
2. If x(t) is I/P to LTI sys with TF H(w) --> I/P & O/P ESD relation :
	- ![[Pasted image 20260103125344.png]]
3. ESD & Autocorrelation fxn R(z) form FT pair (4)
	- ![[Pasted image 20260103125407.png]]



	
	
## 3.4 Power Signals (2)
	- Analog Spectrum Analyzer +Fig (6)(8)  

- Signal x(t) with finite avg power (0 < P < inf) & inf E (E = inf)
- Almost all periodic signals
- Expression
	- ![[Pasted image 20260103125653.png]]
### Parseval's Theorem for power signals
- Statement : P of signal may be defined in terms of its fourier series coef
- Proof
	- ![[Pasted image 20260103125732.png]]
	- ![[Pasted image 20260103125738.png]]
	- ![[Pasted image 20260103125744.png]]
### Power Spectral Density (PSD) (2)(4)  
	- PSDF Derivation (4)(6)  

- Derived by assuming P signal as limiting case of an E signal
- Consider P x(t) which extends to inf
	- ![[Pasted image 20260103125907.png]]
- Terminate / Limit signal from +- z/2
	- Such that denoted by x$_z$ (t)
	- Expressed as ![[Pasted image 20260103125946.png]]
	- ![[Pasted image 20260103125953.png]]
- Now since x$_z$ (t) is of finite duration --> its an E signal
- Let its E be expressed as
	- ![[Pasted image 20260103130044.png]]
- ![[Pasted image 20260103130048.png]]
- ![[Pasted image 20260103130059.png]]
- From above eqn, Total power is obtained by multiplying s(w) with BW dw & integrating over entire BW
- Hence s(w) of s(f) may be treated as avg P per unit BW
- Periodogram of signal : ![[Pasted image 20260103130233.png]]
### ESD & PSDF (2)(4)  
![[Pasted image 20260103130255.png]]
![[Pasted image 20260103130308.png]]
### PSD & Average Power of Periodic Signal +Eg (6)
#### PSD of Harmonic Signal
- Consider
	- Periodic signal x(t)
	- Period T$_o$
	- Complex exp fourier series expression
		- ![[Pasted image 20260103130933.png]]
- ![[Pasted image 20260103130941.png]]
- Truncate signal by introducing gate fxn G$_T$(t) 
	- ![[Pasted image 20260103131003.png]]
- ![[Pasted image 20260103131024.png]]
- ![[Pasted image 20260103131307.png]]
- ![[Pasted image 20260103131321.png]]
### PSDF of white noise (2)
- White noise (3) : Idealised form of noise
- Presence of all freq
- Can be considered as random signal / process with flat PSD indep of freq
- PSDF of white noise
	- ![[Pasted image 20260103131409.png]]
	- Factor 1/2 indicates --> Half of power associated with +ve & half with -ve freq
	- ![[Pasted image 20260103131435.png]]
## 3.6 Autocorrelation (AC) (1)(3)  
	- AC Function of White Noise +Fig (4)(3)  
		- PSDF Vs AC Function +Eg (3)(4)(6)  
	- PSD of Output of LTI System (I) (5)  
	- Autocorrelation of Cosine Signal +Eg (3)  
	- Autocorrelation, Cross-Correlation & Convolution (Graphical) (3+3)

- Gives measure of similarity, match or coherence betw signal & its delayed replica
- AC betw 2 signals explains how much a signal is related to its time delayed version

- Consider signal x(t)
	- AC of this signal with its delayed version will be
		- ![[Pasted image 20260103131936.png]]
- AC can be taken as special case of cross correlation
### AC for E signals
- Let x(t) be an E signal
- AC obtained by integrating x(t) & delayed version of its complex conjugate
	- ![[Pasted image 20260103132045.png]]
	- Where complex valued signal x(t) is delayed in +ve time
- If x(t) is shifted z in -ve dir
	- ![[Pasted image 20260103132111.png]]
### AC for P signals
- Let x(t) be an P signal with period To
- AC fxn if for 1 period
	- ![[Pasted image 20260103132344.png]]
- If x(t) is shifted z in -ve dir
	- ![[Pasted image 20260103132357.png]]
- So for any period T, AC fxn is given as
	- ![[Pasted image 20260103132407.png]]
### Properties of AC (3)(5)  
#### For E signals
1. AC fxn exhibits conjugate symmetry
	- ![[Pasted image 20260103132150.png]]
2. Val of AC fxn at z = 0 (origin) = E of signal
	- ![[Pasted image 20260103132209.png]]
3. If z is increased in either dir, AC reduces. 
	- AC is max at z = 0
	- ![[Pasted image 20260103132234.png]]
4. AC fxn & ESDF of E signal form FT pair
	- ![[Pasted image 20260103132250.png]]
#### For P signals
1. Conjugate Symm
2. Val of AC fxn at z = 0 (origin) = Avg P of signal
	- ![[Pasted image 20260103132453.png]]
3. Max at origin
4. AC fxn & PSDF : FT pair
5. AC fxn is periodic with period same as that of periodic signal
	- ![[Pasted image 20260103132556.png]]

![[Pasted image 20260103132628.png]]

- Describes time series fxn --> Comparing to sines & cosines
##  Fourier Series
- Representation of period signal 
	- Combination of sines & cosines or complex exponentials
## Types
1. Trigonometric : Combination of sines & cosines
2. Complex Exponential : Combination with Complex exponentials 
3. Polar

### Conditions for FT (Dirichlets Theorems)
x(t) must be
- Well defined & single valued function
- Possess only finite no of discontinuities in period T
- Finite no of +ve & -ve maxima in period T
- Absolutely integrable 
	![[Pasted image 20251221120554.png]]
### Properties
1. T scaling ppt
	![[Pasted image 20251221120756.png]]
2. Linearity ppt
	![[Pasted image 20251221120847.png]]
3. Duality or symmetry ppt
	![[Pasted image 20251221120906.png]]
4. Time Shifting ppt
5. Freq Shifting ppt
6. Time differentiation ppt
7. Convolution
	1. Time Convolution Theorem
	2. Freq Convolution Theorem
## Energy Signals
- Finite E :  $$0 < E <\infty$$
- 0 Avg power : P = 0
- x(t) 
##  Frequency Spectrum or Line spectrum 
- Plots of Amplitude & Phase against freq
## Convention
- Real Valued : 
	- cos(nwt) Yes
	- sin(nwt) No --> cos(nwt - 90)
- No negative amp
	- x - An cos(nwt) --> +An cos(nwt + $\theta_n$  $\pm$ 180)

Plot the line signal of 
$6-20\cos(2\pi400t+60)+17\sin(200\pi t-100)\ -23\sin\left(400\pi t\ +\ 45\right)\ +\ 18\cos\left(150\pi t\ -\ 120\right)$$6+20\cos(2\pi400t+\left(60-180\right))+17\cos(200\pi t-\left(100+90\right))\ +23\cos\left(400\pi t\ +\ \left(45-90+180\right)\right)\ +\ 18\cos\left(150\pi t\ -\ 120\right)$
