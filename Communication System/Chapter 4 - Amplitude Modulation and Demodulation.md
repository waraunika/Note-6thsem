# Syllabus
## 4.1 Fundamentals of AM
- AM Signal Characteristics (3)
- Time Domain Expression (3)
- Frequency Domain Representation (3)
- Modulation Index (1)(2)(4)(6)
	- Derivation
	- (+) Operation near 100%
- Signal Bandwidth (BW) (1)
## 4.2 AM System Characteristics
- Single Tone Message 
- Carrier & Sidebands 
- Power Distribution 
- Power & Bandwidth Efficiency (4)
	- Conventional AM wastefulness
	- AM Types Vs Power & BW (2)
## 4.3 Generation of AM Variants
- DSB-FC AM
	- Double Tone AM Expression (3)(6)
	- Single Tone DSB-FC (Time + Frequency + Spectrum) (9)
	- Square Law Modulator (+Fig)(5)(6)
	- Switching Modulator (+Fig)(6)(8)
	- Any One Method (4)
- DSB-SC AM
	- Balanced Modulator (+Fig)(5)(6)
	- Ring Modulator (+Fig)(6)(8)
	- Time & Frequency Domain (–)
	- Power, BW, Efficiency (–)
- SSB Modulation
	- DSB Vs SSB (2)(3)(4)(5)(8)
	- SSB Signal Derivation (Hilbert Transform) (4)(6)
	- Applications of SSB (2)
- Generation of SSB
	- SSB Generation Methods (4)
	- Phase Shift Method (+Fig)(6)
	- Low-Pass Signal Based Derivation (6)
	- Phase Shift Method (+) (2)
	- Phase Shift Method (-) (2)
## 4.4 Advanced AM Techniques
- VSB Modulation (2)
	- (I) VSB
	- Generation & Spectrum (+Fig)(4)
	- (+) TV Transmission (2)
- ISB (Intro) 
- QAM (Intro) 
## 4.5 Demodulation of AM Signals
- Synchronous Detection
	- DSB-SC Detection (+Fig)(3)(6)
	- (I) Synchronous Detection (3)
	- Phase & Frequency Error Effects (3)
	- Practical Synchronized Receiver (5)
	- DSB-AM Vs DSB-SC Vs SSB Vs VSB (2)
- Envelope & Square Law Detection
	- Square Law Detector Limitation (2)
	- Envelope Detector (+Fig)(4)(6)
	- Time Constant Conditions (2)
	- DSB-SC Using Envelope Detector (-) (2)
- SSB Demodulation
	- Carrier Reinsertion Method (8)
- Carrier Recovery Circuits
## 4.6 PLL in AM
- PLL (5)
- PLL Components (2)
- AM Demodulation Using PLL (4)(5)(6)
- Phase & Frequency Error Using PLL (3)(4)(8)
- Costas Loop (+Fig)(10)
---
---
# Theory
## 4.1 Fundamentals of AM
	- AM Signal Characteristics (3)
	- Time Domain Expression (3)
	- Frequency Domain Representation (3)
	- Signal Bandwidth (BW) (1)

- Modulation : Process in which some char of carrier signal is caried according to val of modulating signal
- Modulating signals / Baseband signal : Contain info needed to be transm
- Continuous wave (CW) modulation : Carrier waveform is cont in nature 
	- Amp Modulation (AM)
	- Angle Modulation
### AM
- Process in which amp of higher freq carrier signal c(t) is varied according to change in modulating signal m(t)
- ![[Pasted image 20260105134756.png]]
- For convenience, assume theta = 0
	- ![[Pasted image 20260105134810.png]]
- So for any arbitrary message signal m(t) & any carrier signal c(t), we can have 3 general types of amp modulation

1. Double sideband AM (DSB-AM) / Full Carrier (DSB-FC)

		Modulation Index (1)(2)(4)(6)
		(+) Operation near 100%
		
	- Standard form / eqn
		- ![[Pasted image 20260105135004.png]]
	- ![[Pasted image 20260105135036.png]]
	- Graphical repr
		- ![[Pasted image 20260105142409.png]]
	- ![[Pasted image 20260105142422.png]]
	- ![[Pasted image 20260105142508.png]]
	- ![[Pasted image 20260105142518.png]]
	- Efficiency of DSB-AM 
		- Ratio of useful power at O/P to total power consumed
		- Useful power is contained in sidebands only
		- ![[Pasted image 20260105142604.png]]
		- ![[Pasted image 20260105142611.png]]
	- Also envelope of s(t) has same shape as message m(t) provided that 2 conditions are satisfied
		1. | ka . m(t) | < 1
			or, | ka . Am | < 1
			or, u < 1
		2. Carrier freq (fc) >> Highest freq component of m(t) (fm)
	- Linear modulation : 
		- Under modulation : u <1
		- 100% modulation : u = 1 --> Envelope has same shape as message signal
	- Over modulation : 
		- u > 1 
		- Distortion in envelope
		- Phase reversal in envelope can be seen
	- ![[Pasted image 20260105143131.png]]
2. Double sideband suppressed carrier (DSB-SC)
3. Single sideband suppressed carrier (SSB-SC)
---
---
## 4.2 AM System Characteristics
- Single Tone Message 
- Carrier & Sidebands 
- Power Distribution 
- Power & Bandwidth Efficiency (4)
	- Conventional AM wastefulness
	- AM Types Vs Power & BW (2)
---
---
## 4.3 Generation of AM Variants
### Modulators
1. Multiplier modulators (Linear)
	- Modulation achieved directly by multiplying m(t) by a carrier cos2 pi fc t
	- Whose O/P is proportional to prod of 2 I/P signals
	- Expensive
	- Linearity difficult to maintain
2. Non Linear modulators
	- Diode / Transistors used
	- O/P is not dir prop to I/P throughout the operation
### DSB-FC AM
	- Double Tone AM Expression (3)(6)
	- Single Tone DSB-FC (Time + Frequency + Spectrum) (9)
	- Any One Method (4)
#### Direct Method
- Level shifted modulated signal (1 + ka m(t)) is multiplied by c(t)
- ![[Pasted image 20260105153146.png]]
- Simplest method
- Not suitable for high freq application
- Uses multiplier modulator --> Difficult to maintain linearity
#### Indirect Method
- Uses non linear dev 

1. Square Law Modulator (+Fig)(5)(6)
	- ![[Pasted image 20260105153323.png]]
	- Consists of
		- Modulating & Carrier signal
		- Non Linear dev
		- BP filter
	- I/P - O/P relation of non linear dev
		- ![[Pasted image 20260105153631.png]]
	- When I/P very small --> Higher power neglected
		- Considered only upto sq of I/P
		- Hence name
	- Neglecting DC components ao  --> Freq = 0,
		- ![[Pasted image 20260105153729.png]]
	- ![[Pasted image 20260105153737.png]]
	- ![[Pasted image 20260105153745.png]]
	- ![[Pasted image 20260105153751.png]]
2. Switching Modulator (+Fig)(6)(8)
	- ![[Pasted image 20260105153827.png]]
	- Following assumptions are made with analyzing the modulator
		- Diode : Assumed to be working as switch
			- Acts as closed switch when FB (V1(t) > 0)
			- Acts as open switch when RB (V1(t) < 0)
		- | m(t) | << | c(t) | 
			- Such that m(t) alone cant FB diode
		- +ve half cycle of c(t) can FB diode
	- ![[Pasted image 20260105154102.png]]
	- Periodic at rate equal to carrier freq
		- ![[Pasted image 20260105154130.png]]
		- ![[Pasted image 20260105154139.png]]
	- gp(t) is periodic --> Expressed in Fourier Series
		- ![[Pasted image 20260105154217.png]]
	- Thus O/P of diode : 
		- ![[Pasted image 20260105154229.png]]
		- ![[Pasted image 20260105154235.png]]
--- 
### DSB-SC AM
	- Time & Frequency Domain (–)
	- Power, BW, Efficiency (–)

- In DSB - FC
	- Carrier wave is transm along with Sidebands that contains the message
	- Represents waste of power 
	- We only need transmission of message
- Solution : Modulation scheme where carrier is suppressed & not transm along with SB
	- Increases eff
- General eqn
	- ![[Pasted image 20260105154419.png]]
- Freq domain repr
	- ![[Pasted image 20260105154425.png]]
- Graphical
	- ![[Pasted image 20260105154434.png]]
- Except for scaling factor, modulation process simply translates spectrum of message signal by +- fc
	- Clear that impulses at +- fc are missing --> indicates that carrier term is suppressed with 2 SB present
- Considering +ve time
	- ![[Pasted image 20260105154607.png]]
	- ![[Pasted image 20260105154611.png]]
#### Single Tone DSB - SC modulation
- ![[Pasted image 20260105154704.png]]
- ![[Pasted image 20260105154710.png]]
#### Generation of DSB-SC AM Wave
1. Balanced Modulator (5)(6)
	- ![[Pasted image 20260105154834.png]]
	- Consists of 2 DSB - FC modulators arranged in balanced config --> Suppress carrier completely
	- Message Signal applied to 2 modulators --> 180 phase shifted version of 1 another
	- Oscillator prod req carrier signal
	- O/P for 2 DSB - FC modulators : ![[Pasted image 20260105155029.png]]
	- Balanced modulator O/P : ![[Pasted image 20260105155039.png]]
	- Compared with std DSB - FC signal : ![[Pasted image 20260105155053.png]]
		- Scaling factor 2Ka

2. Ring Modulator (6)(8)
	- ![[Pasted image 20260105155119.png]]
	- Operation of diodes controlled by sq wave carrier with freq fc 
		- Applied by means of 2 centre tapped transformers T1 T2
	- Following assumptions are made while analysing op of ring modulator
		- Diodes are ideal
		- T are perfectly balanced & centre tapped
		- | m (t) | << | c(t) | and m(t) alone cant FB diodes
	- When c(t) is +ve
		- D1 D2 --> On
		- D3 D4 --> Off
	- When c(t) is -ve
		- D1 D2 --> Off
		- D3 D4 --> On
	- ![[Pasted image 20260105160357.png]]
	- ![[Pasted image 20260105160411.png]]
	- Now gp(t) represents periodic sq wave carrier signal, can be expressed in fourier series
	- ![[Pasted image 20260105160552.png]]
---
### SSB Modulation
	- DSB Vs SSB (2)(3)(4)(5)(8)
	- SSB Signal Derivation (Hilbert Transform) (4)(6)
	- Applications of SSB (2)

- For DSB-FC/SC modulation
	- Transmission BW req = 2 * Message BW
	- Upper side band & Lower side band --> Symmetric ppt & contain message in them
	- So even if we transmit either side band, info can be efficiently transmitted
- Transmission of 1 SB 
- Suppression of carrier & other sideband at transmission
- Results in better power eff & red transmission BW
- Freq domain anal
	- Consider m(t) with spectrum M(f) band limited to -B <= f <= B
	- Also spectrum for DSB-SC = Ac/2 (M(f - fc) + M(f + fc))
	- ![[Pasted image 20260106174317.png]]
	- Fig 2: Spectrum of DSB-SC
		- Contains both LSB & USB
	- Fig 3: Spectrum of SSB USB only
	- Fig 4: Spectrum of SSB LSB only
	- Resulting transmission BW
		- ![[Pasted image 20260106174417.png]]
- Time domain repr of SSB
	- ![[Pasted image 20260106174428.png]]
#### Single Tone SSB Modulation
- ![[Pasted image 20260106174503.png]]
#### Generation of SSB
	- SSB Generation Methods (4)
	- Low-Pass Signal Based Derivation (6)
	- Phase Shift Method (+) (2)
	- Phase Shift Method (-) (2)

1. Freq Discrimination Method (Filtering Method)
	- m(t) & c(t) are applied to product modulator  --> Generate DSB-SC wave
	- Passed through BP filter --> Only 1 SB filtered out
	- ![[Pasted image 20260106174605.png]]
	- Conditions to be satisfied
		- USB & LSB non overlapping
			- Separated by significant freq gap
			- Because BP filter need very sharp change over from attenuation to PB & vice versa
		- Baseband signal must be appropriately related to carrier freq
			- Design of BPF becomes quite difficult if carrier freq >> BW of baseband signal
	- Thus, SSB signals rarely used in video comm --> Baseband signal starts from DC
	- Used more in voice comm

2. Phase shift method (Hartley method) (6)
	- Consists of
		- 2 product modulators
		- 2 90 phase shift netw --> Suppress either of SB
	- Block diagram
		- ![[Pasted image 20260106180617.png]]
	- In fig
		- Impulse path consists of product modulator P1 such that its O/P is 
			- m(t) . cos2 pi fc t
		- Quadrature path consists of 
			- Hilbert transformer
			- Product modulator P2
		- Such that overall O/P is
			- ![[Pasted image 20260106180808.png]]
			- Where
				- If -ve sign --> gives SSB-USB
				- If +ve sign --> gives SSB-LSB
---
---
## 4.4 Advanced AM Techniques
#### VSB (Vestigial SB) Modulation (2)
	- (I) VSB
	- Generation & Spectrum (+Fig)(4)
	- (+) TV Transmission (2)

- SSB modulation --> Well suited for transmission of voice signal
				--> Most of info carried in freq 3400 Hz
				--> Energy gap betw 0 & 3400 Hz is quiet significant
- But in video signals --> Signals range from low freq approaching DC to high freq
	- So SSB modulation restricted --> Req sharp selective filters
- VSB : 1 SB completely passed & trace of other SB (vestige)
- Standard for transmission of TV & other similar signals
	- Where good ph chara & transm of low components are imp
- ![[Pasted image 20260106181220.png]]
- Fig 3 : Transmission BW = (B + fv) Hz
	- Or, for Single tone message signal with freq fm
		- BW = (fm + fv) Hz
	- fv = width of vestigial SB
- So BW req for transm of VSB > SSB (~25% more)
#### Generation of VSB wave
- ![[Pasted image 20260106181347.png]]
- ![[Pasted image 20260106181353.png]]
- Gen of VSB modulated wave can be achieved by producing DSB-SC wave first 
	- By using prod modulator to modulate m(t) & c(t)
- Then passed through SB shaping filter
	- Gen one of SB
	- And trace / vestive of other SB
#### ISB 
- ![[Pasted image 20260106181512.png]]
- ![[Pasted image 20260106181518.png]]
#### QAM 
- ![[Pasted image 20260106181530.png]]
- ![[Pasted image 20260106181536.png]]
---
---
## 4.5 Demodulation of AM Signals
- Synchronous Detection
	- DSB-SC Detection (+Fig)(3)(6)
	- (I) Synchronous Detection (3)
	- Phase & Frequency Error Effects (3)
	- Practical Synchronized Receiver (5)
	- DSB-AM Vs DSB-SC Vs SSB Vs VSB (2)
- Envelope & Square Law Detection
	- Square Law Detector Limitation (2)
	- Envelope Detector (+Fig)(4)(6)
	- Time Constant Conditions (2)
	- DSB-SC Using Envelope Detector (-) (2)
- SSB Demodulation
	- Carrier Reinsertion Method (8)
- Carrier Recovery Circuits
---
---
## 4.6 PLL in AM
- PLL (5)
- PLL Components (2)
- AM Demodulation Using PLL (4)(5)(6)
- Phase & Frequency Error Using PLL (3)(4)(8)
- Costas Loop (+Fig)(10)
---
---