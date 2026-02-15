# Antenna Parameters
1. Isotropic radiator
2. Effective aperture
	- aka Effective area
	- aka Effective length
	- A$_{eff}$ = $\eta\ \cdot$A$_{physical}$
3. Effective (Equivalent) Isotropic radiated power (EIRP)
	- function of $\dfrac{P_t\ \cdot\ G_t}{L_{wg}}$ in watts Pt is power, Gt is gain, L$_{wg}$ is wave guide loss
	- in dB, \[EIRP] = \[P$_T$] + \[G$_T$] - \[L$_{wg}$]
	- measured in dBm (not for watt, but for milliwatt)
	- for dish antenna, we have LNB (Low noise block), that includes LNA (Low noise amplifier)
4. Power flux density (PFD)
	- distance between transmitting and receiving antenna is called:
		- R (slanted range)
		- or L
	- link budget
	- PFD = $\dfrac{\text{EIRP}}{4\pi R^2}$ W/m^2
5. Antenna Gain (G) and antenna efficiency
	- G$_t$ = $\eta \cdot \left( \dfrac{\pi\ D}{\lambda} \right)^2$  
	- G = $\left(\dfrac{4\pi}{\lambda^2}\right) A_{eff}$ 
		- 4pi/lambda^2 is universal constant
	- $\left(\dfrac{4\pi}{\lambda^2}\right) \cdot\ \eta\ \cdot\ \dfrac{\pi\ D^2}{4}$
	- $\eta \left(\dfrac{\pi\ D}{\lambda}\right)^2$
6. Receiving power density (Pr)
	- density or intensity
	- $\dfrac{\text{EIRP}}{4\pi R^2}\cdot A_{eff_{R}}$
	- $\dfrac{P_t \cdot G_t}{L_{wg}\ 4\ \pi\ R^2}\cdot \eta \dfrac{\pi D^2}{4}$
	- $\dfrac{P_t \cdot G_t}{L_{wg}\ 4\ \pi\ R^2}\cdot G_r \left(\dfrac{\lambda}{\pi D}\right)^2 \cdot \dfrac{\pi D^2}{4}$
	- $P_t \cdot G_t \cdot G_r \left(\dfrac{\lambda}{4\pi R}\right)^2$ is the Friis transmission equation
	- free space loss or spreading loss = $[P_t] + [G_t] + [G_r] - \left[\left(\dfrac{4\pi R}{\lambda} \right)^2\right]$
	- P$_\eta$ = K T B
7. Noise power density (Pn)
	- \[C/No] = \[EIRP] + \[G/T] - \[L$_{FS}$] - \[K] + \[L$_{margin}$] - \[L$_{other}$]
	- up link = 6 GHz
	- down link = 4 GHz
8. Carrier-to-noise ratio (C/N)
9. Carrier-to-noise density (C/No)
10. Directivity
	- Gain (G) = $\eta \cdot D$, where D is Directivity
11. Polarization
	- orientation of electric field in space
12. Slant Range
	- R = $h\ \sqrt{1+0.42(1-\cos(\phi))}$
	- $\cos(\phi)\ =\ f(L, l)$
		- L = Longitude
		- l = latitude
	- figure:
	  ![[Pasted image 20260106103628.png | 600]]
13. Beam width (BW)
	- figure:
	  ![[Pasted image 20260106104900.png]]
	 -  required: major/main lobe
	- main goal: to reduce side lobes
	- figure:
	  ![[Pasted image 20260106105309.png]]
	- called First node beam width
	- half power beam width
	- approximately, HPBW = $\dfrac{\sqrt{\text{FNBW}}}{2}$, across the center z axis
14. Band width (BW)
	- Bandwidth (BW) = $\Delta$f =  f$_2$  - f$_1$ = f$_{max}$ - f$_{min}$
	- fractional bandwidth in percentage
	- FBW = $\dfrac{f_2\ -\ f_1}{f_c}$ = $2 \cdot\ \dfrac{f_2 - f_1}{f_2 + f_1}$ 
	- if < 1%, narrow band
	- 1 < FBW < 20, broad
	- wide band: 20 < FBW < 50,
	- ultra wide band: FBW > 50
15. VSWR
	-  Reflection Coefficient:
		- mismatch coefficient
		- $\Gamma$
	- VSWR = $\dfrac{1\ -\ \left|\Gamma\right|}{1\ +\ \left|\Gamma\right|}$
	- Voltage standing wave ratio