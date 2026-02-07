# Syllabus
## 2.1 Review of Signals and Systems
Review of Signals  
• Unit Step Signal Representation (4)  
• Signum Signal (2)  
• Bandpass Vs Band-Limited Signal +Eg (4)  
• Periodic Vs Non-Periodic Signals +Eg (4)

Types of Systems  
• Linear, Non-Linear, Causal, Time-Invariant (4)  
• System Classification by Properties (4)

Impulse Response & Transfer Function (2)(4)  
• (I) (2)(3)  
• Output via Convolution (4)(6)  
• Impulse Response of Ideal LPF (1)(4)(6)

LTI Systems  (2)  
• Properties (4)  
• (I) (3)  
• Output Expression of LTI (Time Domain) (5)  
• Linearity Test +Eg (4+4)(3+3)  
• Causality & Time-Invariance Test +Eg (4+4)(3+3)

## 2.2 System Transformations and Properties

Lowpass / Bandpass Signals & Systems  

Bandwidth of Systems  

Distortionless Transmission  (5)
• (I) of Distortionless Transmission +Derivation (5)  
• Transfer Function +Fig (Amplitude Response) (3)(6)  
• Distortionless Transmission Line +Freq Response (3)(4)  
• Conditions for Distortionless Transmission +Fig (6)  

## 2.3 Special Transforms and Signal Representations

Hilbert Transform  (2)(4)(5)
• Properties (2)(3)(4)  
• Description +Math Expression (2)(3)(4)  
• Hilbert Transform Vs Fourier Transform (2)

Band-Pass / Band-Limited Signal Representation  

Complex Envelope Representation  

Polar Representation  


# Theory
## 2.1 Signals 
- Fxn of 1(+) indep var  -> Convey info about behaviour & nature of some phenomena
### Types of Signals

1. Continuous & Discrete Time signal
	- CTS : Can be defined for all possible real no values of its indep var (eg t)
		- x(t) is cont signal if t is a cont var
		- AKA analog signal
	- DTS : Can be defined for only set of discrete (or int) val of indep var
		- May arise in 2 ways
			- Selecting val of analog signal at discrete T instants --> Sampling
			- Accumulating a var over a T period
				- Eg, counting no of cars using every hour
		- When quantized & encoded --> We get digital signal

2. Deterministic & Random Signal
	- Deterministic : 
		- Signals which can be completely specified in time
		- Regular patterns
		- Can be characterized mathematically
		- Nature : Can be predicted at any time
	- Random
		- Unpredictable
		- Uncertainty before actual occurance of signal
		- Cant predict val of signal at any particular instant
		- Need to go for some probable val
		- Better suited for probability theory

3. Causal & Non causal signal
	- Causal
		- Val at -ve time = 0
		- x(t) = 0 for t < 0
	- Anti causal
		- Signal reading is = 0 for all +ve time
		- x(t) = 0 for t > 0
	- Non causal
		- Non 0 val in both +ve & -ve t
		- x(t) != 0 for -t to t

4. Energy & Power Signal
	- Energy signal
		- Finite energy
		- 0 Avg power
	- Power signal
		- Finite val of avg power
		- Infinite energy
	- ![[Pasted image 20251231150038.png]]
	- There are some signals that are neither

5. Periodic & Non periodic Signal (4)
	- PS 
		- Exhibits definite pattern
		- Repeats itself over & over again at certain interval of T
		- x(t) = x(t+T) for -inf < t < inf
			- T = Period of signal
			- Smallest val of T that satisfies above eqn --> Fundamental period & +ve constant
	- NPS 
		- Doesnt repeat itself at regular interval of T

6. Even & Odd Signal
	- Even
		- Exhibits symmetry in T domain about vertical axis
		- x(t) = x(-t) for all t
	- Odd
		- Shows anti symmetric behaviour
		- Mirror image to their negative
		- x(t) = -x(-t) for all t
---
### Special Types of Signals
1. Harmonic Signal
	- Periodic Signal expressed in terms of sinusoidal fxn
	- Defined for -inf <= t <= inf
	- ![[Pasted image 20251231151534.png]]

2. Unit Step (4)
	- Exists only for +ve side of T domain
	- Has Amp of 1
	- Repr by u(t)
	- ![[Pasted image 20251231151604.png]]

3. Rectangular / Unit Pulse
	- ![[Pasted image 20251231151622.png]]

4. Triangular Pulse Function
	- ![[Pasted image 20251231151632.png]]

5. Sinc
	- ![[Pasted image 20251231151642.png]]
	- Has Max val signal = 1 at t = 0
	- Gradually & alternatively --> 0 as t --> inf
	- ![[Pasted image 20251231151722.png]]

6. Signum (2)
	- Used to define polarity of signal as per T axis
	- ![[Pasted image 20251231151738.png]]

7. Delta / Unit Impulse Function
	- Mathematical model to repr physical phenomenon that takes place in very short period of T
	- Most widely used elementary signal for analysis of comm sys
	- ![[Pasted image 20251231151821.png]]
	- Convolution of any fxn with delta fxn gives val of that fxn
	- ![[Pasted image 20251231151855.png]]
	- ![[Pasted image 20251231151907.png]]
---
### Representation of Signals
1. Time Domain
	- Signal is a T varying qtt
	- ![[Pasted image 20251231153115.png]]

2. Freq Domain
	- More preferred
	- Signal repr by its freq spectrum
	- ![[Pasted image 20251231153140.png]]
---
---
## 2.2 Systems  
	• Linear, Non-Linear, Causal, Time-Invariant (4)  
	• System Classification by Properties (4)

- Set of elements or function blocks connected together which produces desired O/P in response to an I/P signal
- Response / O/P of sys depends on TF of sys
- ![[Pasted image 20251231153203.png]]
### Impulse Response
	- (I) (2)(3)  
	- Output via Convolution (4)(6)  
	- Impulse Response of Ideal LPF (1)(4)(6)

- O/P of system when I/P is impulse or delta fxn
- ![[Pasted image 20251231153823.png]]
####  Transfer Function (2)(4)  
- Fourier transform of impulse response h(t)
- ![[Pasted image 20251231153902.png]]
---
### Types
1. Linear system
	- Principle of superposition can be applied
	- Let
		- I/P : x1(t) & x2(t)
		- Operator : phi
		- Corresponding O/P : 
			- y1(t) = alpha phi x1(t)
			- y2(t) = beta phi x2(t)
		- O/P for combination must yield
			- y(t) = phi (alpha x1(t) + beta x2(t))
			Where alpha, beta are scaling factors
	- ![[Pasted image 20251231154132.png]]

2. Non Linear 
	- Not satisfy superposition principle

3. Time Invariant 
	- Response of the sys doesnt depend on any shift in T for I/P signal x(t)
		- ![[Pasted image 20251231155407.png]]

4. Time Variant 
	- Response of sys varies with shift in T at I/P signal 
### Linear Time Invariant system (LTI) (2)  
- 2 basic ppt play a vital role in analysis of signals & systems
	- Linearity
	- Time Invariance
- Characterized by its impulse response
	- Performed by 
		- Convolution integral in continuous time case
		- Convolution sum in discrete time case
- ![[Pasted image 20260101170236.png]]
- By definition
	- Impulse response h(t) = O/P of sys for del(t) as I/P
		- h(t) = phi del(t)
	- ![[Pasted image 20260101170410.png]]
- Cross convolution x(lambda) * x(t - lambda)
#### Properties (4)  
1. Commutative 
2. Distributive
3. Associative
4. Static & Dynamic
5. Invertibility
6. Stability
7. Causality
8. Unit step repsponse
• (I) (3)  
• Output Expression of LTI (Time Domain) (5)  
• Linearity Test +Eg (4+4)(3+3)  
• Causality & Time-Invariance Test +Eg (4+4)(3+3)


Continuous Time Signal / Analog system
	- Physical dev 
	- Operates on cont T signal --> Input or excitation x(t)
		- According to some well defined rule
	- To prod another cont T signal --> Output or response y(t)

---
---
## 2.3 Low Pass & Band Pass Signals / Systems
	- Bandpass Vs Band-Limited Signal +Eg (4)  
### LPS
- Signal that has its significant spectral content centered around origin
- BW is defined as 1 half of total width of main spectral lobe
- Basically A/V signals in unmodulated form
- ![[Pasted image 20260101170821.png]]
### BPS 
- Significant spectral content lies around freq fc (non zero freq)
- BW is defined as width of main lobe for +ve freq
### System BW
- System that processes on
	- LPS -> LP sys
		- 3db BW defined as diff betw (B)
			- 0 freq when amp is highest : (H(0))
			- Freq when amp drops by 1/sqrt(2) : (H(0))/sqrt(2)
			- ![[Pasted image 20260101171053.png]]
	- HPS -> HP sys
	- BPS -> BP sys
		- 3db BW defined as diff betw (B)
			- Freq when amp drops by 1/sqrt(2) times peak amp centered around any freq fc other than 0 : (fc + B) & (fc - B)
			- BW = fc + B - fc + B = 2B
			- ![[Pasted image 20260101171242.png]]
---
---
## 2.4 System Transformations and Properties
### Transformations on Transfer Function  
• Fourier Transform Properties (4)(5)  
○ Modulation  
○ Duality  
○ Time Shifting  
○ Scaling  
○ Convolution

---
### Distortionless Transmission  (5)
	• (I) of Distortionless Transmission +Derivation (5)  
	• Transfer Function +Fig (Amplitude Response) (3)(6)  
	• Distortionless Transmission Line +Freq Response (3)(4)  
	• Conditions for Distortionless Transmission +Fig (6)  
- O/P signal y(t) is exact replica of I/P signal x(t)
- ![[Pasted image 20260101171406.png]]
- ![[Pasted image 20260101171433.png]]
- In order to achieve distortionless transmission through a sys, TF of sys must satisfy 2 conditions
	- Amp response of H(f) is constant for all freq
		- | H(f) | = k
	- Phase of H(f) is linear with freq passing through origin
		- ![[Pasted image 20260101171543.png]]
	- ![[Pasted image 20260101171549.png]]

---
---
## 2.4 Special Transforms and Signal Representations
### Hilbert Transform  (2)(4)(5)
	• Hilbert Transform Vs Fourier Transform (2)

- Operator which adds phase shift to input signal
	- -90 to all +ve freq
	- +90 to all -ve freq
- But amp response of sys is constant for entire freq range of interest
- HT of signal x(t) -> ![[Pasted image 20260101172003.png]]
- Hilbert Transformer : Device that performes HT
#### Math Expression (2)(3)(4)  
- Impulse response of Hilbert Transformer
	- ![[Pasted image 20260101172032.png]]
	- ![[Pasted image 20260101172042.png]]
---
#### Properties (2)(3)(4)  
1. Energy content in both x(t) & ![[Pasted image 20260101172153.png]] are same
	- ![[Pasted image 20260101172200.png]]
2. ![[Pasted image 20260101172207.png]] are orthogonal
	- Cross correlation betw them is 0
	- ![[Pasted image 20260101172233.png]]
3. If 
	- x(t) is a High freq sinusoidal signal
	- m(t) is a Low Freq sinusoidal signal
	- Then, ![[Pasted image 20260101172324.png]]
---
#### Uses
1. Gen of SSB signals
2. Designing min phase type filters
3. Repr of BP signals
