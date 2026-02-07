# Syllabus
(CS)
- Channel Classification +Eg (10)
- Major Elements (4)
Analog Communication System
- Block Diagram +Fig (2)(4)
  - Working / Block Functions (6)(8)
- Main Components (7)
Digital Communication System (DCS)
- Block Diagram +Fig (2)(5)(6)
- Basic Components & Functions (5)
- Working (5)
- Full Duplex Mode +Fig (5)
Analog Vs Digital CS (5)
- (+) Digital over Analog (3)
- (+) Analog over Digital (4)
- Analog Source Vs Digital Source (2)
Distortion (4)
- Types (3)
	- Linear Vs Non-Linear Distortion (2)
Noise (2)
- Types (3)(4)
	- Internal Vs External Noise (2)
	- Sources of External Noise (2)
	- Thermal & High Frequency Noise (3)
- Effects / Limitations due to Noise (2)(3)
- Atmospheric Noise Effects (Analog CS) (2)
Interference (2)(4)
- Sources (2)
- Effects on CS Performance (1)(3)
- Minimization Techniques (2)
- Impairments & Performance Parameters (3)
Noise Vs Distortion Vs Interference +Eg (4)(5)(6)
Modulation (1)(2)(4)
- (I) (1)(2)(4)
- Justification of Modulation Need (4)
Channel Modulation Method (4)
# Theory
## 1. Communication System
- Process of sending info from src --> Receiver
- Interconnected system designed to carry info from 1 place to another
	- Performing necessary OP on signal to facilitate optimum transfer

- Channel Classification +Eg (10)
- Major Elements (4)
### 1.1 Analog Comm system
- Block Diagram +Fig (2)(4)
  - Working / Block Functions (6)(8)
- Main Components (7)
![[Pasted image 20251223175937.png]]
1. Information Source
	- Gen info to be transm
	- Message signal
	- Analog : Speech, Video
	- Digital : Text, multimedia
2. Input Transducer
	- Convert non electrical signal --> electrical signal
3. Transmitter
	- Modifies M signal --> Suitable form for transmission over channel
	- Modulation
	- M signal superimposed upon high freq carrier signal
4. Communication Channel
	- Provide phy conn betw T & R
	- Noise signal always added --> Distorts info carried by channel
	- Point to point : Wirelines, Microwave links, optical
	- Broadcast : Satellite, FM broadcasting
5. Receiver
	- Function opposite to transducer
	- Extracts M/info from received signal
	- Demodulation
6. Destination
	- M/Info received to desired dest in original form
7. Output Transducer
### 1.2 Digital Comm system
- Block Diagram +Fig (2)(5)(6)
- Basic Components & Functions (5)
- Working (5)
- Full Duplex Mode +Fig (5)

- Discrete signal
- Max possible rate & accuracy
![[Pasted image 20251223181826.png]]
1. Source encoder
	- Seq of symbols occurring at fixed interval of time --> Binary seq of 0/1s
	- Assigning code word to each symbol
2. Channel encoder
	- Adds some error control bits to O/P of src encoder
	- Dont carry info
	- Makes R detect error & correct them
3. Channel modulator & Demodulator
	- Bit streams from ch encoder --> Electrical form for transm over comm channel
	- In mod : Some param of carrier wave is varied with message signal
		- Basic techniques : ASK, PSK, FSK
	- In demod : Electrical signal into seq of bits
4. Channel decoder
	- Recovers info bearing bit stream from coded bit stream
	- Min error 
	- Max eff
5. Src decoder
	- Performs reverse OP of src encoder
	- Converts bin O/P of ch decoder into seq of symbols
### 1.3 Analog Vs Digital CS (5)
#### (+) Digital over Analog (3)
- Long dist tranms + Greater acc
- Increased immunity to ch noise & ext interf
- Common format for transm of diff kinds of M signals
- Err at R may be detected & corrected by ch mathematically
	- By linear time variant filter with impulse response c($\tau$, t)
	- For an I/P signal S(t) 
		![[Pasted image 20251223182546.png]]

- (+) Analog over Digital (4)
- Analog Source Vs Digital Source (2)
### 1.4 Shannon Hartley channel capacity
- SNR = Signal Noise Ratio
- Channel Capacity ~ BW
- For a given channel BW B & req level of SNR : Max speed of data transm c
	(Signals power density)
			$$CC = BW log _2 (SNR + 1)$$
				
- For given B & SNR : Channel cap is fixed/constant
- To increase ch cap
	- Increase SNR
		- High transm req
		- Limited by sys power handling cap
	- Increase BW
		- Increase noise power
		- Decreases SNR

Shannon Hartley Theorem    : SNR (Signal to Noise Ratio)              
$$CC = BW log _2 (S/N + 1) Linear$$

	10 log 10 (S/N) = x  db
	Let x = 0            ~ S = N
	X = 10               ~ S = 10N
	X = 20               ~ S = 100N
	X = -10              ~ S = N/10

Higher SNR = Better

64kbps, Calc CC for 0 DB                   ~ 64k * log2 (1 + 1) 

Coder decoder = Codec

System : Input Output Interface

Signal (time, Amp, Freq, Phase)

Fourier transform : Cycles count

---
---
## 2. Noise, distortion and interference

### Distortion (4)
- Unwanted Changes in O/P waveform of dev in comparison to I/P Waveform
- ![[Pasted image 20251230151930.png]]
- Nature in audio & video signals --> Human ear 
	- Sensitive to phase distortion
	- Insensitive to amp distortion
#### Types of Distortion (3)
	Linear Vs Non-Linear Distortion (2)
1. Linear distortion
	- Prod by : Non uniform Freq & Ph responses
	- Diff freq components of I/P signal experience diff gain
	- Linear dev is distortion less if
		- Mag response TF / Impulse response = Constant
		- Phase = Linearly proportional to freq for f <= fmax
	- ![[Pasted image 20251230152231.png]]
2. Non Linear distortion
	- Prod by : Non linear I/P char of sys / dev (eg diodes)
	- Produces new freq component at O/P not present at I/P
	- I/P char of system approximated as
		![[Pasted image 20251230152614.png]]
	- Gen of Harmonics of Fundamental freq of I/P signal due to non linearity of dev
		- Evaluated in terms of harmonic distortion
		- ![[Pasted image 20251230152816.png]]
		- ![[Pasted image 20251230152828.png]]

3. Crosstalk / Intermodulation distortion
	- Overlap of original spectrum due to interference with other signals caused by spectral dispersion

---
### Noise (2)
- Unwanted signal added to received signal
- Degrades perf of comm sys
#### Types (3)(4)
	Internal Vs External Noise (2)
##### Internal Noise
- Gen within sys

1. Thermal / White / Johnson Noise (1.5)
	- Due to random movement of free electrons within the system
	- Temp up --> Int KE up --> E of e$^-$ up --> Randomness up
	- Thermal noise power
		- $P_n = KTB$
			K = Boltzman Constant
			T = Temp of conductor
			B = BW of noise spectrun H2
	- ![[Pasted image 20251230153508.png]]
2. Shot noise
	- Due to random fluctuation in electron emission from cathode in vacuum tube
	- e emission variation -> Change in current
	- In S/C due to var in no of e crossing potential barrier
3. Partition Noise
	- Due to random fluctuation in division of current into 2(+) paths
	- In S/C transistor, due to emitter current div into base & collector currents
	- Less in diode than transistor
4. Flicker / Low Freq noise
	- Due to fluctuation in carrier density
	- N(f) = 1/f
	- Non uniform dist of carrier psdf of flicker noise is inversely prop to freq
5. Transit Time / High freq noise (1.5)
	- In S/C at high freq, some carriers may diffuse back to src before crossing jxn 
	- PSDF of such noise increases with freq
6. Gen-recombination noise
	- Due to random process of recombination & gen of charge carriers
##### External Noise
	- Sources of External Noise (2)
- Noise gen ext to comm sys
- Can be min / elim when proper care is taken
- Eg : 
	- Human made noise
		- Interference from signals transm or nearby channels
		- Fluorescent light
		- Industrial noise by motors
		- Smoke of automobiles
	- Natural noise
		- Lightning
		- Solar radiation
		- Cosmic noise
#### Effects / Limitations due to Noise (2)(3)
#### Atmospheric Noise Effects (Analog CS) (2)
---
### Interference (2)(4)
- Non uniform distrib of received signal
- Contamination of received signal by unwanted signals
- Due to 
	- Manmade : Various broadcasting & comm sys
	- Natural disturbances : Lightning

- Sources (2)
- Effects on CS Performance (1)(3)
- Minimization Techniques (2)
- Impairments & Performance Parameters (3)
1.     Amplitude vary randomly        ~ Noisy signal            ~ S(A)

2.     Phase change                           ~ Distortion                ~ S(phi)

3.     Delay / Latency / Jitter             ~ Propagation/Transmission, Nodal Processing

URLC   : Ultra Reliable Low Latency

4.     Data Rate                                   ~ bps or bHz (Bit/Baud)       

5.     Throughput                                ~ bps               (Successful Received)

6.     BW                                              ~ Analog (Hz) [f max – f min]             / Digital (bps)

7. Transmission Efficiency : Power efficiency
8. Spectral Efficiency :  Frequency term, side band remove
9. P2PR : Peak to peak power ratio
10. Entropy : 
11. Spectral Power density
12. Spectral Noise density
---
### Noise Vs Distortion Vs Interference +Eg (4)(5)(6)
---
### Modulation (1)(2)(4)
#### Need for modulation (1)(2)(4)
1. Long Range Transmission
	- To transmit audio signal (Relatively short range of transmission) over longer dist --> Modulation necessary before transm
	- F increase --> E increase --> Long range transm
2. Practical Antenna Size
	- For wireless comm -> Size of receiving & trans antenna dep on freq of transmitting signal
	- If low freq to be transm -> Size of antenna very large
	- Use of modulation technique -> Antenna size red
	- Eg
		- Freq of audio signal (f) = 1kHz 
		- For eff radiation of signal, ln of antenna ~= 1 quarter of its wavelength
		- ![[Pasted image 20251230161720.png]]
3. Reduction of noise & interference
	- Noise effect cant be completely elim 
	- With help of several modulation schemes --> Minimized
	- After modulation freq of modulated wave is 100Mhz
		- ![[Pasted image 20251230161802.png]]
4. Multiplexing
	- Broadcasting of audio baseband signals dir without modulation 
		--> Interfere with each other
		--> Spectra of all signals more or less occupy same BW
	- Multiplexing : Technique where several message signals combined to composite signal for transmission over common channel
	- In order to transmit no of signals over same channel --> Signals kept apart so that they dont interfere with each other & can be sep easily by receiver end
#### Types of modulation
	Channel Modulation Method (4)
1. Continuous / Analog modulation
	- Carrier wave is continuous in nature
	1. Amplitude Modulation : Amp of carrier wave varied in accordance with message / baseband signal
	2. Angle modulation : Angle of carrier wave (freq ph) varied in accordance with modulating signal
		1. Freq Modulation
		2. Phase Modulation

2. Pulse Modulation (Analog / Digital)
	- Carrier wave is pulse type waveform
	- Periodic seq of rectangular / digital pulses











## Mathematical operation on Continuous Time Signals
### Scaling of Continuous Time Signals
#### 1. Amplitude Scaling
- Multiplying amp of signal by a constant
#### 2. Time Scaling

### Folding (Reflection or Transpose) of continuous time signals
- Changing sign of time base t in signal x(t)
- Produces signal x(-t)
	- Mirror image of original signal x(t) wrt time origin t = 0
### Time shifting of Continuous T Signals
- Replace independent var t by t - m
- Shifted signal x(t-m)
- m = Time shift in seconds
	- Positive : Delay to right
	- Negative : Advance to left

### Delayed Unit Impulse Signal

### Multiplication of Continuous Time Signals


---




