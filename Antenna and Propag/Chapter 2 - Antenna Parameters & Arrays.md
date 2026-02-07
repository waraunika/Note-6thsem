# Syllabus
## **Basic Antenna Parameters**
- Receiving Antenna Gain (Gr) (1.5)(3)
- Free Space Loss (LFS) (3)
- Directivity (1.5)(2)(3)(4)
- Polarization (2)(3)
    - Linear Polarization (3)
- Input Impedance (3)
- Radiation Pattern (2)(3)
    - Lobes (2)
- Beam Width (3)
    - +Eg (2)
- Antenna Efficiency (3)(4)
    - +Eg (2)
- Bandwidth (3)
- Half Power Bandwidth (2)
- Antenna Gain (2)
    - +Eg (2)(3)
- Power Flux Density +Eg (3)
---
## **Antenna (Simple Conductor)**
- Radiation Conditions (4)
---
## **Antenna Array**
- (I) (2)
- (I) Vs Single Antenna Length (2)
---
## **Center-Fed Dipole**
- Current Distribution & Radiation Pattern +Fig (4)(6)
    - λ/2
    - 3λ/2
    - 2λ
---
## **Dipole Lengths**
- λ/2 Vs λ Vs 3λ/2 (Radiation Pattern, Impedance, Directivity) (6)
---
## **Antenna Parameters**
- Gain, Efficiency, Directivity +Eg (6)
- Antenna Parameters (6)(5)(4)
---
## **Pattern Multiplication**
### **Linear & 2-D Arrays**
- Pattern Multiplication (2)
- Antenna Array (I) (2)
- Linear Array (1)
---
### **End Fire Array**
- Features (4)
- Principle Vs Broadside (6)
- Radiation Pattern +Fig (d=λ/2, α=π) (4)
---
### **Broadside Array**
- End Fire Vs Broadside (4)(6)
- Conditions +Fig (6)
---
---
# Theory
## **Basic Antenna Parameters**
1. Isotropic Radiation
	- ![[Pasted image 20260113122306.png]]
	- Isotropic Antenna : ![[Pasted image 20260113122309.png]]

2. Effective Isotropic Radiated Power (EIRP)
	- ![[Pasted image 20260113122338.png]]

3. Power Flux Density (PFD) / Radiation Power Density (RPD)+Eg (3)
	- ![[Pasted image 20260113123443.png]]
	- Always measured in transm side
	- Fxn of Radiation of Tx antenna
	- ![[Pasted image 20260113123544.png]]
	- ![[Pasted image 20260113123559.png]]

4. Antenna Gain +Eg (2)(3)
	`Receiving Antenna Gain (Gr) (1.5)(3)
	- Used only for Aperture antenna
	- Can be for both Tx & Tr antenna
	- Only change is wavelength
	- But, usually G is called Receiving Gain
	- Gr -> Receiving Gain
	- Gt -> Transmitting Gain
	- ![[Pasted image 20260113123853.png]]

5. Antenna Efficiency +Eg (2)(3)(4) 
	- Defined as 
		- Ratio of Power Radiated to Total Power (Supplied) in TX
		- Ratio of Power Received to Exposed Total signal Power (EMWs) in RX
	- Used to relate Effective Area and Physical Area
	- ![[Pasted image 20260113123932.png]]
	- ![[Pasted image 20260113124132.png]]
	- ![[Pasted image 20260113124209.png]]
	- All Signals exposed on Antenna could not be totally Recovered due to Antenna Efficiency
	- Total Eff, ƞ0 = Product of Various types of Efficiencies
	- Unit less or Dimensionless
	- In general, overall eff
		- ![[Pasted image 20260113124709.png]]
		- ![[Pasted image 20260113124728.png]]
		- ![[Pasted image 20260113124816.png]]

6. Receiving Power Intensity
	- ![[Pasted image 20260113124828.png]]
	- 11 & 12 -> Friis Transmission Eqn
	- ![[Pasted image 20260113124934.png]]

7. Antenna Aperture Area
	- Can be
		- Effective Area (Aeff) 
		- Physical Area (Aphy)
	- ![[Pasted image 20260113125011.png]]
	- Applied in length as well
		- ![[Pasted image 20260113125022.png]]

8. Free Space Loss (LFS) (3)
	- ![[Pasted image 20260113125031.png]]
	- Loss due to signal spreading over distance
	- Dir prop to Freq
	- Inv prop to sq of freq
	- ![[Pasted image 20260113125153.png]]

9. Antenna Noise Temp (To)
	- Included with system Noise Temp
		- ![[Pasted image 20260113125209.png]]
	- Always in Rx side

10. Receiving Noise Power (Pn)
	- Always measured in R side
	- Counted in C/N = Pr/Pn
	- Pn = Antenna Noise Temp = T0

11. Carrier to Noise Ratio (C/N)
	- Measured in I/P of Antenna
	- C/N = Pr/Pn
	- Antenna catches desired signal including noise power

12. Carrier to Noise Density (C/N$_0$)
	- Measured in after tuning ckt with antenna
	- Antenna itself resonant ckt equiv
	- ![[Pasted image 20260113125429.png]]

13. Gain-to-Noise Ratio (G/T)
	- AKA Figure of Merit
	- Ratio of R antenna gain to Antenna Temp
	- Always measured in Rx site
	- Det quality & signal Strength of Earth Station (ES)
	- Very imp factor in Link Design
		- Up Link or Down Link
	- Val maintains standard of ES

14. Bandwidth (3)
	`Half Power Bandwidth (2)
	- Range of freq within which perf of antenna wrt some char conforms to specific std
	- ![[Pasted image 20260113125638.png]]
	- ![[Pasted image 20260113125647.png]]
	- ![[Pasted image 20260113125651.png]]

15. Beam Width +Eg (2)(3)
    - First-null Beamwidth (FNBW)
    - Half-power Beamwidth (HPBW) 
	    - 3dB less from peak of major lobe
	    - (HPBW) = 70 λ/D  (Degree)
	    - Or,     BW = 21 X 10$^9$/Fd
	    - Normally, HPBW≈FNBW/2
    - Pencil Beamwidth
	    - Used for Space comm
	    - ![[Pasted image 20260113130212.png]]
	- Fig : Radiation lobes and beam widths of an antenna pattern\
		- ![[Pasted image 20260113125753.png]]
	- Fig : Radiation Patterns with BW
		- ![[Pasted image 20260113125806.png]]

16. Beam Efficiency (BE)
	- Use : Judge Quality of Transmitting and Receiving antennas 
	- For an antenna with its major lobe directed along z-axis (θ = 0)
		- BE = Power Transmitted (Received) within cone Angle θ1/Power Transmitted (Received) by the Antenna
	- Dimensionless (Unit less) 
	- Ratio of Main Beam area to Total Beam area
		- εM = ΩM/ ΩA = Beam Efficiency 
		Where, ΩA = ΩM + Ωm 
		ΩA is Total Beam Area (or Beam Solid Angle) 
		ΩM is Main Beam Area (or Solid Angle)
		Ωm is Minor-lobe area (or Solid Angle)
	- Ratio of Minor-lobe area to the Total Beam area 
		- εm = Ωm/ ΩA = Stray Factor 
	- It Follows That εM + εm = 1

17. Radiation Pattern Lobes (2)
	- Portion of Radiation Pattern bounded by regions of Relatively Weak Radiation Intensity
	- Sub-classified into
		1. Major or Main Lobe : Radiation lobe containing dir of Max Radiation
		2. Minor Lobe : 
			- Any lobe except Major Lobe
			- Includes side and back lobes
			- Usually repr radiation in undesired dir
			- Should be min
		3. Side Lobes : 
			- Radiation lobe in any dir other than intended lobe
			- Usually adjacent to Main lobe
			- Occupies Hemisphere in dir of main beam
			- Normally largest of minor lobes
		4. Back Lobes
			- Radiation lobe whose axis makes angle ~180◦ wrt Main Beam of an Antenna.
	- ![[Pasted image 20260113131520.png]]

18. Radiation Intensity
	- Power Radiated from an Antenna per Unit Solid Angle
	- Measured in Watts per Steradian or per Square Degree
	- Ratio of Radiation Intensity U(θ,ɸ), as a fxn of angle, to its Max value.
		- Pn(θ,ɸ) = U(θ,ɸ)/U(θ,ɸ)max = S(θ,ɸ)/S(θ,ɸ)max
		- Where
			- Poynting vector S depends on Distance from Antenna that is Varying Inversely as Square of Distance
			- Assuming in both cases, far field of antenna is applied
	- Indep of Dist

19. Input Impedance (3)
	- Z Presented by Antenna at its Terminals
	- Ratio of Voltage to Current at a Terminals
	- Ratio of Appropriate Components of Electric to Magnetic Fields at Point Impedance 
	- Measured at a pair of Terminals
	- ZA= RA + jXA
		- Where, 
			ZA is Antenna Imepedance at Terminals a-b 
			RA is Antenna Resistance at Terminals a-b 
			XA is Antenna Reactance at Terminals a-b 
		And, RA = Rr + RL
			Rr = Radiation Resistance of the Antenna 
			RL = Loss Resistance of the Antenna

20. Radiation Resistance
	- Fictitious Resistance
	- Equiv to Same amt of Power When actually Radiating
	- Not actually Measured Resistance from Antenna
	- Rr is Subject to power that it converts into EMW
	- Ratio of power radiated to square of current at feed point 
	- From Input Impedance: ZA= RA + jXA
		Where, 
			ZA is Antenna Imepedance at Terminals a-b 
			RA is Antenna Resistance at Terminals a-b 
			XA is Antenna Reactance at Terminals a-b 
		And, RA = Rr + RL
			Rr = Radiation Resistance of the Antenna 
			RL = Loss Resistance of the Antenna

21. Loss Resistance 
	- Ohmic or Load Resistance
	- For Efficient Radiation, Rr must be very Higher than RL 
	- Loss Resistance gives Rise to Power Loss 

22. Return Loss S11
	- Ratio of Reflected Power to Incident Power, S11
	- Insertion Loss: Ratio of Transmitted Power to Incident Power, S21
	- Transmitted Power: Power comes out of the Component
		- ![[Pasted image 20260113145223.png]]
	- Output Power: Power comes out of Transmitter
		- Less than Incident Power for 2 Reasons:
			1. Some Power Reflected and never got into the Component
			2. Some Power that Entered the Components was Absorbed Inside 
		- ![[Pasted image 20260113145348.png]]
	- S Parameters
		- ![[Pasted image 20260113145452.png]]

23. Transmission Coefficient t(S)
	- Used in Physics and Electronics Engg
	- When Wave Propagation in a Medium 
	- Medium containing Discontinuities is Considered
	- Describes
		- Amplitude
		- Intensity
		- Or total Power of a Transmitted Wave Relative to an Incident Wave
	- In Telecommunications, it is Ratio of Amp of Complex Transmitted Wave to Incident Wave at a Discontinuity
	- Reflection Coefficient, Γ
		- ![[Pasted image 20260113145647.png]]

24. Directivity (1.5)(2)(3)(4)
	- Ratio of Radiation Intensity in given Dir from Antenna to Radiation Intensity averaged over all dir
	- Avg Radiation Intensity = Total Power Radiated by Antenna divided by 4π
	- Ratio of Max. Radiation to Average Radiation Intensity 
		- D = Umax/Uav = Um/Uo
			= 4πUm/ 4πUo = 4πUm/P 
		Where, P is Total Power Radiated
		Since, UO = P/ 4π and P = UmΩA 
		So,    D = 4π/ΩA
		Where, ΩA =∫∫ (θ,ɸ)/∫ (θ,ɸ)max dΩ
		This is Beam solid angle or, Beam Area
	- Gain of Antenna (Lossless Isotropic source) depends on both Directivity and Efficiency. 
			G = ƞ D 
		Where, ƞ = Efficiency factor of Antenna (0 ≤ ƞ ≥1)
	- This Efficiency has to do only with Ohmic Losses in Antenna
	- In TX, these Losses involve Power fed to Antenna -> Not Radiated but heats Antenna Structure.

25. Polarization (2)(3)
	- Orientation of Electric Field in space Coords
	- Polarization Loss : Occurs when R Antenna alignment is not Properly aligned with received wave
	- Polarizer : 
		- Fitted inside Feed Horn
		- Polarizes RF Radiation 
	- Cross Polarization: Opposite Polarization occurs in Receiving Antenna.
	- Cross Polarized Wave reduced signal strength 
	- Polarized Wave is named as based on Electric Field in space
	- Polarization in Direction of Max gain
	- Frequency Diversity or, Frequency Reused Techniques based of Polarization for virtually Doubled Bandwidth
	
	- Classified mainly two Types:-
	1. Linear Polarization (3)
		- Sub-divided into 2 kinds
			1. Vertical Polarization
				- ![[Pasted image 20260113144709.png]]
			2. Horizontal Polarization
				- ![[Pasted image 20260113144722.png]]

	2. Circular Polarization
		- Sub-divided into 2 kinds:
			1. Right Hand Circular Polarization (RHCP)
			2. Left Hand Circular Polarization(LHCP)

![[Pasted image 20260113132226.png]]

---
## **Antenna (Simple Conductor)**
- Radiation Conditions (4)
---
## **Antenna Array**
- (I) (2)
- (I) Vs Single Antenna Length (2)
---
## **Center-Fed Dipole**
- Current Distribution & Radiation Pattern +Fig (4)(6)
    - λ/2
    - 3λ/2
    - 2λ
---
## **Dipole Lengths**
- λ/2 Vs λ Vs 3λ/2 (Radiation Pattern, Impedance, Directivity) (6)
---
## **Antenna Parameters**
- Gain, Efficiency, Directivity +Eg (6)
- Antenna Parameters (6)(5)(4)
---
## Pattern Multiplication (2)
### **Linear & 2-D Arrays**
	- Antenna Array (I) (2)
	- Linear Array (1)

#### Why Pattern Multiplication
- Single Radiator has wide directive gain
- Single antenna provides low val of directivity
- Low amp
- Broad radiation pattern
- Low Antenna Gain
#### Total Field = Element Factor x Space Factor
- ![[Pasted image 20260113145800.png]]
#### How to Overcome?
- Antenna formed by Multi-elements is called Array Antenna
- Identical Elements make either 
	- Broadside 
	- Or End-Fire Array
- Diff size of Elements -> Build Parasitic Array (e.g. Yagi-Uda Antenna)
- For Pattern Multiplication -> Diff Kinds of  Antennas can be Used as Array types
- Array is almost possible for Every types of Antennas
#### For Designing Array of Identical Elements: 
1. Geometrical Config (Dimensions) 
2. Equal Relative Displacement betw Elements( i.e. Spacing )
3. Excitation Amp of Indiv Elements
4. Excitation Ph of Indiv Elements
5. Excitation of Relative Pattern of Indiv Elements
#### Examples Fig
- ![[Pasted image 20260113150025.png]]
- ![[Pasted image 20260113150036.png]]
- ![[Pasted image 20260113150041.png]]
- ![[Pasted image 20260113150046.png]]
- ![[Pasted image 20260113150053.png]]
- Fig : Config of Dipole
	- ![[Pasted image 20260113150137.png]]
- Fig (a) Two Point Sources with origin of Coord System Coincident with one of the Sources. (b) Vector addition of Fields from two Point Sources of Equal Amplitude and Same Phase located as in (a)
	- ![[Pasted image 20260113150147.png]]
- Fig (a) Relation to Coordinate System of two Point Sources Separated by a Distance d. (b) Vector addition of Fields from two Point Sources of Equal Amplitude and Same Phase Located as in (a) 
	- ![[Pasted image 20260113150253.png]]
#### Diff cases of arrays of 2 point sources
1. Same amp and phase
	- ![[Pasted image 20260113150524.png]]
	- ![[Pasted image 20260113150531.png]]
	- ![[Pasted image 20260113150618.png]]
	- ![[Pasted image 20260113150704.png]]
	- ![[Pasted image 20260113150742.png]]
	- Where 
		- ψ = dr cos ϴ
		- Amp of field components at distance r is given by E0
		- First term in (1) is component of field due to source 1
		- Second term component due to source 2.
	- Suppose further that d is λ/2. 
		- Then dr = π.
		- Introducing these conditions into above Equation gives
			- ![[Pasted image 20260113150956.png]]
	- ![[Pasted image 20260113151043.png]]
	- ![[Pasted image 20260113151048.png]]

2. Same amp opp phase
	- ![[Pasted image 20260113151130.png]]
	- ![[Pasted image 20260113151107.png]]
	- ![[Pasted image 20260113151117.png]]
	- ![[Pasted image 20260113151120.png]]
	- ![[Pasted image 20260113151140.png]]
	- Where, 
		Emax= 2jE0 = 1 
		And, d = λ/2; β = 2π/ λ
	- ![[Pasted image 20260113151159.png]]
	- ![[Pasted image 20260113151205.png]]
	- Fig : Relative Field Pattern for 2 Point Sources of Same Amplitude but Opposite Phase, Spaced λ/2 Apart
		- ![[Pasted image 20260113151223.png]]
		- ![[Pasted image 20260113151301.png]]
	
3. Same amp and in phase quadrature
	- ![[Pasted image 20260113200540.png]]
	- ![[Pasted image 20260113200602.png]]
	- Fig : Field Pattern of two Point Sources of Equal Amplitude and Quadrature Phase in Case where the Separation d = λ/2
		- ![[Pasted image 20260113200722.png]]
	- ![[Pasted image 20260113200629.png]]
	- Fig : Field Pattern of 2 Point Sources of Equal Amplitude and Quadrature Phase in the Case where the Separation d = λ/4
		- ![[Pasted image 20260113200731.png]]

4. Equal amp and any ph diff δ
	- Total Ph Diff ψ betw Fields from Source 2 and Source 1 at Distant Point in dir ϴ
		- ψ = d cos ϴ + δ 
		- ![[Pasted image 20260113200850.png]]
	- Normalizing above eqn -> General Expression for Field Pattern of 2 Isotropic Sources of equal Amplitude and Arbitrary Phase,
		- E = cos ψ/2
		- And,  we have   ψ = d cos ϴ + δ 

5. Unequal amp and any ph diff
	- Let Field from Source 2 be of Amp aE0 (0 ≤ a ≤ 1) at Dist r
	- ![[Pasted image 20260113201058.png]]
	- (a) 2 Point Sources of Unequal Amplitude and Arbitrary Phase wrt Coordinate System (b) Vector Addition of Fields from Unequal Sources arranged as in (a). Amp of Source 2 Assumed < Source 1 by factor a.
		- ![[Pasted image 20260113201103.png]]
---
### **Broadside Array**
	- End Fire Vs Broadside (4)(6)
	- Conditions +Fig (6)

- Linear Array Antenna
- Same Geometrical Configurations
- Using a number of Identical Parallel Elements
- Usually Odd Number of Elements are Used
- Each Element is Equally spaced 
- Each Element is Exited with Equal Amplitude
- Each Element is Exited in same phase

- Radiation Pattern is Perpendicular to the Array Axis
- Radiation Pattern: Bidirectional
- Max. Radiation Equally in both Directions
- Usually, 6 side Lobes, 3 in each side
- Distance between Elements (d)= (0.1λ – 0.15λ)
- E = Cos (π/2Cosθ)$_{d=λ/2}$
- Fig : Broadside Array Arrangement
	- ![[Pasted image 20260113201411.png]]
- Fig : Radiation Patterns of Broadside Array
	- ![[Pasted image 20260113201424.png]]
---
### **End Fire Array**
	- Features (4)
	- Principle Vs Broadside (6)
	- Radiation Pattern +Fig (d=λ/2, α=π) (4)

- Linear Array Antenna
- Same Geometrical Configurations
- Using a Number of Identical Parallel Elements 
- Not significant Odd or Even No. of Elements used
- Radiation and Directivity are in the Array Axis
- Each Element is Equally spaced 
- Each Element is Excited with Equal Amplitude

- But Each Element is Exited in1800 out of Phase
- Exciting Phase Progressively Varies
- Single Main Lobe with Four Side Lobes 
- Unidirectional Radiation Pattern
- Radiation Pattern is in same Array Axis
	- (i.e. Parallel with antenna Axis)
	- ![[Pasted image 20260113201526.png]]

- Radiation Pattern is in same Array Axis
- Distance between Elements (d)=0.1λ – 0.15λ
- If only two elements are used, Radiation Patterns can be Bidirectional 
- E = Sin (π/2Cosθ)$_{d=λ/2}$
	- (i.e. Radiated Pattern Parallel with Array Axis)
	- ![[Pasted image 20260113201641.png]]
- Fig : End Fire Array Arrangement
	- ![[Pasted image 20260113201654.png]]
- Fig : Radiation Pattern of End Fire Array
	- ![[Pasted image 20260113201702.png]]
- Fig : Field patterns of end-fire arrays of 10 point sources of equal amp spaced λ/4 apart
	- ![[Pasted image 20260113201711.png]]
- Fig : Field Pattern of Array of 4 Point Sources of Equal Amp with Phasing Adjusted to give Max at φ = 60◦. The Spacing is λ/2
	- ![[Pasted image 20260113201744.png]]

---





slant range (R) = h sqrt(1 + 0.42 (1 - cosphi))
cosphi = f(h, l)
L$_{Fs}$ = 22 + 20log (F / lambda)
R^2 = (re + h)^2 + re^2 - 2re(re+h) cosphi


cband uplink = 6GHz
downlink = 4GHz

L$_{Fs}$ (sigma) ~= 200dB
L$_{Fs}$ (u) ~= 195dB



Beam Width (BW)
Band Width (BW) = del f = fmax - fmin
FBW = (fmax - fmin)/fc
	= (f2 - f1) / (f2 + f1) * 2
		
	Narrow Band < 1%
	Wide band 1% < WB < 20%
	Broad band 20% < BB < 50%
	Unltra wide  broad band > 50%
VSWR

HPBW ~= FNBW / 2

In array of identical elements
1. Similar geometrical config (dimensions) (linear, circular, rectangular, spherical)
2. Relative displacement (spacing) betw elements
3. Excitation amp
4. Excitation phase
5. Relative pattern of indiv elements
Arrays of 2 isotropic point soures
6. Case 1 : 2 Isotropic point sources of samp amp & ph
7. 