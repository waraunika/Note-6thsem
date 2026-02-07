# 2.1 Basic Antenna Parameters
## A. Radiation pattern
- graphical representation of the time average power density of the electric or magnetic field strength of an antenna as a function of space coordinate is known as radiation pattern.
- if power taken for plotting -> power pattern
- electric field -> electric field pattern
- same for mag field
- 3 patterns
### A.1 Isotropic Radiation
- hypothetical, equal radiation in all direction 
- independent of $\theta$, $\phi$,
- no antenna is isotropic
- 0 db antenna (no gain)
- can be produced with combination of dipole antenna placed perpendicular to each other.
### A.2 Omnidirectional Radiation
- antenna having the property of radiating or receiving EM waves as a function of elevation angle ($\theta$) is called omnidirectional pattern.
### A.3 Directional Radiation
- antenna having the property of radiating more efficiently in some direction than in other direction
- its radiation pattern -> directional radiation pattern
- function of $\theta$ and/or $\phi$ 
- figure:
  ![[Pasted image 20260126203218.png | 600]]
## B. BeamWidth
![[Pasted image 20260126203533.png | 600]]
- Major lobe:
	- the portion of the radiation pattern containing the direction of maximum radiation
	- is the largest lobe
- minor lobe:
	- any lobe except for the major lobe
- side lobe:
	- the minor lobe located in the hemisphere that contains main lobe
	- side lobe ratio (SLR) = $\dfrac{max\ P_{av}\ in\ side\ lobe}{max\ P_{av}\ in\ main\ lobe}$
	- SLR of 20 db or less is usually harmful in most application.
	- front to back ratio (FBR) = $\dfrac{max\ P_{av}\ in\ back\ lobe}{max\ P_{av}\ in\ main\ lobe}$
	- minimum value is used
## C. Antenna Gain
- this antenna gain is used for only aperture antenna
- can be for both, Tx or Rx
- only depends on $\lambda$
- G is usually receiving gain
- G$_r$ = $$\dfrac{4\pi}{\lambda^2} * A_{eff} = \dfrac{4\pi}{\lambda^2} * \eta\ * \dfrac{\pi D^2}{4} = \eta\left(\dfrac{\pi D}{\lambda}\right)^2$$
- 4 $\pi$ / $\lambda$^2 is universal constant
- $\eta$ is antenna efficiency where
- $\eta$ = $$G \left( \dfrac{\lambda}{\pi D}\right)^2$$
## D. Free space loss
- L$_{free}$ = $$\left( \dfrac{4\pi r}{\lambda} \right)^2 $$
- loss due to signal spreading over distance
- loss is directly proportional to square of freuency, 
	- or inversely proportional to square of wavelength
- in db, $$ [L_{free}] = 10\ \log\left(\dfrac{4\pi R}{\lambda}\right)^2$$
- so, $$[L_{free}] = 20\log(4\pi) + 20\log\left(\frac{R}{\lambda}\right)$$
- here, 20 log(4$\pi$) = 22
## E. Antenna Noise Temperature
- included with system noise temperature
- T$_0$ = k T$_s$ * B
	- where k = Boltzmann's constant = 1.381 * 10$^{-23}$ J/K
	- T$_s$ = system noise temperature
	- B = bandwidth of frequency being used.
- measured in Rx side
- also called power of noise P$_n$
## F. Efficiency
- figure:
![[Pasted image 20260126205302.png | 500]]
- defined as the ratio of power radiated to the total power supplied in Tx
- defined as the ratio of power received to the exposed total signal power (EMWs) in Rx
- used to relate the effective area and physical area
- $\eta$ = $\dfrac{G(\theta, \phi)}{D(\theta, \phi)} = \dfrac{P_t}{P_0}$
- all signals expsed on the antenna coul dnot be totally recoered to antenna efficiency
- total efficiency $\eta_0$ is the product of various types of efficiencies
- in general,
- $\eta_0 = \eta_r * \eta_c * \eta_d * \eta_{sp} * \eta_{sm} * \eta_b * \eta_{sc} * \eta_i$
	- where, 
	- n0 = total
	- nr = reflection (mismatch)
	- nc = conduction
	- nd = dielectric
	- sp = spillover efficiency from primary reflector
	- sm = ..... main reflector
	- b = blockage
	- sc = scattering
	- i = illumination
- reflection mismatch
	- nr = $\left( 1 - \left| \Gamma \right|^2 \right)$ 
		- where,
		- gamma is voltage reflection coefficient, at the input terminals of antenna
		- gamma = $\dfrac{Z_{in}\ -\ Z_0}{Z_{in}\ +\ Z_0}$,
			- where,
			- Zin = antenna input impedance
			- Z0 = characteristic imepdance of the transmission line
	- voltage standing wave ratio: $$\text{VSWR} = \dfrac{1 + \Gamma}{1 -\ \Gamma}$$
## G. Effective Isotropic Radiated Power
- EIRP = $$\dfrac{P_t\ *\ G_t}{L_{wg}}$$
- where, 
	- Pt = transmitting power
	- Gt = transmitting gain
	- Lwg = waveguide (cable loss)
- EIRP = \[P$_t$] + \[G$_t$] - \[L$_{wg}$] dB W
- it is always measured in Tx terminal
## H. Power Flux Density
- aka radiation power density
- short term PFD = $$\dfrac{\text{EIRP}}{4\pi R^2}$$
- in log term: $$[PFD] = [P_t] + [G_t] - [L_{wg}] - [4\pi R^2]\ \text{dB w/m}^2 $$
- where R is the distance between Tx and Rx
- PFD = EIRP reduced by 4$\pi$ times square of R
- it is function of radiation Tx antenna, measured in Tx antenna
## I. Receiving Power
- Main formula : $$P_{r}=A_{r}PFD$$
- Solving further, $$P_{r}=A_{R}\cdot\frac{P_{t}G_{t}}{4\pi r^{2}\cdot L_{wg}}$$
	- this is called Friis formula
- replace Gt by its equivalent formula: $$G_{t}=4\pi\cdot\frac{A_{t}}{\lambda^{2}}$$
- so next step is: $$ A_{R}\cdot\frac{P_{t}}{4\pi r^{2}\cdot L_{wg}}4\pi\cdot\frac{A_{t}}{\lambda^{2}}$$
- next step: $$P_{r}=A_{R}\cdot\frac{P_{t}}{r^{2}\cdot L_{wg}}\cdot\frac{A_{t}}{\lambda^{2}}$$
- next step: replace: Ar by its formula: $$P_{r}=P_{t}\cdot A_{t}\cdot G_{r}\cdot\frac{1}{\dfrac{4\pi r^{2}}{\lambda^{2}}}\cdot\frac{1}{L_{wg}}\cdot\frac{1}{\lambda^{2}}$$
- next step, replace everything and start with L$_f$: $$P_{t}\cdot A_{t}\cdot G_{r}\cdot\frac{1}{\left(\frac{4\pi r}{\lambda}\right)^{2}}\cdot\frac{1}{L_{wg}}\cdot\frac{4\pi}{\lambda^{2}} $$
- next step, simplify: $$P_r = \frac{P_{t}\cdot A_{t}\cdot G_{r}}{L_{f}}\cdot\frac{1}{L_{wg}}\cdot\frac{4\pi}{\lambda^{2}}$$
- ignore $\dfrac{4\pi}{\lambda^2}$ as it is universal constant, finally in log form:
- final expression: $$[P_r] = [P_t] + [A_t] + [G_r] - [L_f] - [L_{wg}]$$
## J. Receiving Power Intensity
- here, $$P_{r}=PDF\cdot A_{eff}$$
- we have for A effective: $$\frac{P_{t}G_{t}}{L_{wg}\cdot4\pi r^{2}}\cdot\eta\cdot A_{phy}$$
- replacing for each formula for eta and A physical: $$\frac{P_{t}G_{t}}{L_{wg}\cdot4\pi r^{2}}\cdot G_{r}\left(\frac{\lambda}{\pi D}\right)^{2}\cdot\frac{\pi D^{2}}{4}$$
- simplifying: $$\frac{P_{t}G_{t}G_{r}}{L_{wg}}\cdot\left(\frac{\lambda}{4\pi R}\right)^{2}$$
- final result: $$P_{r}=\frac{P_{t}G_{t}G_{r}}{L_{wg}\cdot L_{f}}$$
## K. Carrier to noise Ratio (C/N R)
- it is measured in receiving side at the input of antenna
- C/N R = $\dfrac{P_r}{P_n}$ = $$\frac{P_{t}G_{t}G_{r}}{L_{f}}\cdot\left(\frac{\lambda}{4\pi r}\right)^{2}\cdot\frac{1}{kT_{s}B}$$
- P$_r$ is receiving power intensity
- antenna catches desired signal including noise power
- CNR must be high so that more desired signal is received than noise
## L. Carrier to Noise density (C/T)
- It is measured, after Tuning circuit of Rx antenna
- C/T ratio = C/N$_0$ = $$\frac{C}{N_{0}}=\frac{C}{N}\cdot B=\frac{P_{r}}{P_{n}}\cdot B=\frac{P_{r}}{kT_{s}B}\cdot B=\frac{P_{r}}{kT_{s}}$$
- then, C  = $P_{r}=P_{t}G_{t}G_{r}\cdot\left(\frac{\lambda}{4\pi r}\right)^{2}\ \text{in\ J/K}$  
- then, $N_{0}=kT_{s}$
## M. Antenna Aperture
- antenna aperture area can be effective or physical
- A$_{eff}$ is always $\eta$ times smaller than A$_{phy}$
- then, A$_{eff}$ = $\eta$  A$_{phy}$
- similarly, it is applied for both in antenna length as well
- L$_{eff}$ = $\eta$  L$_{phy}$
## N. Gain to Noise Ratio G/T
- aka figure of merit
- ratio of receiving antenna gain to antenna temperature
- it is measured in Rx side
- G/T determines the quality and signal strength  and standard of earth station (ES)
- imp factor in link design
- link could be up/down link
## O. Bandwidth
- the range of frequency within the performance of the antenna
	- with respect to some characteristics, conforms to a specific standard.
- BW = $\Delta$ f = f$_2$ - f$_1$ 
- f$_c$ = $\dfrac{f_{2}+f_{1}}{2}$
- then, fractional bandwidth (FBW) = $$\dfrac{f_{2}-f_{1}}{\dfrac{f_{2}+f_{1}}{2}}=2\ \frac{f_{2}-f_{1}}{f_{2}+f_{1}}$$
- measured in percentage
- FBW < 1%: Narrow BW
- 1 < FBW < 20: broadband
- 20 < FBW < 50: wide band
- 50 < FBW: ultra wide band
## P. Beam Efficiency
- maybe called radiation efficiency
- used to judge quality of Tx and Rx antennas
- for an antenna with its major lob directed along the z axis ($\theta$ = 0), the beam efficiency (BE) is described by: $BE=\dfrac{\text{Power\ transmitted\ with\ cone\ angle}\theta_{1}}{\text{Power\ transmitted\ by\ the\ antenna}}$ 
- power could be transmitted or received in the formula
- BE is dimensional
- ratio of main beam area to total beam area:
- $\epsilon_M$  = $\dfrac{\Omega_M}{\Omega_A}$ = BE
	- where
	- $\Omega_A$ = $\Omega_M$ + $\Omega_m$
		- where
		- $\Omega_M$ = main beam area
		- $\Omega_m$ = minor beam area
	- where,
	-  $\Omega_A$ = total beam area
- ratio of main lobe to the total beam area $\dfrac{\Omega_m}{\Omega_A}$ = stray factor = $\epsilon_m$
- and  $\epsilon_M$ + $\epsilon_m$ = 1
## Q. Radiation Intensity
- power radiated from an antenna per unit solid angle
- measured in watts per steradian or per square degree
- ratio of radiation intensity U($\theta, \phi$ ) as a function of angle to its maximum value.
- Thus, P$_n$($\theta, \phi$) = $$\frac{U\left(\theta,\ \phi\right)}{U\left(\theta,\ \phi\right)_{max}}$$ = $$\frac{S\left(\theta,\ \phi\right)}{S\left(\theta,\ \phi\right)_{max}}$$
- where as the poynting vector S depends on the distance from the antenna
	- that is varying inversely as the square of distance
- radiation intensity is independent of distance
## R. Input Impedance
- aka Zin
- impedance presented by antenna at its terminals
- ratio of voltage to current at a terminals
- ratio of appropriate components of electric to magnetic fields at a point impedance
- input impedance is measured at a pair of terminals
- that is I/P terminals of the antenna
- formula:
	- Z$_{in}$ = R$_A$ + j X$_A$
		- where,
		- R$_A$ = R$_r$ + R$_L$
		- Rr:
			- fictitious resistance 
			- equivalent to some amount of power when actually radiating
			- not actually measured the resistance from antenna
			- Rr is subject to the power that it converts into EMW
			- Ratio of power radiated to the square of current at the feed point
		- R L
			- ohmic or load resistance
			- for efficient radation, Rr must be very higher than R L
			- loss resistance gives rise to power loss
## S. Polarization
- the orientation of electric field in the space coordinates
- when receiving antenna alignment is not properly aligned with received wave, then polarization loss occurs
- polarizer: it is fitted inside feed horn
	- it polarizes the RF radiation
- cross polarization: the opposite polarization occurs in the receiving antenna
- it reduces signal to strength
- mainly two types:
	1. Linear
		- of two types: Horizontal and Vertical
	2. Circular:
		- of two types: Right handed Circular Polarization (RHCP) and Left handed Circular Polarization (LHCP)
- Figure:
  ![[Pasted image 20260126220213.png | 450]]
- polarized wave is named as based on electric field in the space.
- polarization in the direction of maximum gain
- frequency diversity or frequency reused techniques based on polarization
	- for virtually doubled bandwidth
## T. Directivity
- ratio of radiation intensity in a given direction from the antenna to the radiation intensity averaged overall direction
- the average radiation intensity is equal to the total power radiated by the antenna divided by 4$\pi$
- D = $$=\ \frac{U_{max}}{U_{av}}=\frac{U_{m}}{U_{0}}=\frac{4\pi U_{m}}{4\pi U_{0}}=\frac{4\pi U_{m}}{P_{0}}$$
- where P is the total power radiated
- since, $U_{0}=\dfrac{P_{0}}{4\pi}$, & $P_0=U_{m}\Omega_{A}$ 
- so, $D=\dfrac{4\pi}{\Omega_{A}}$
- where, $$\Omega_{A}=\int\frac{S\left(\theta,\phi\right)}{S\left(\theta,\phi\right)_{max}}d\Omega$$
- this is the beam solid angle or beam area
- gain of an antenna, referred to as lossless isotropic sources, depends on both directivity and its efficiency
- G = $\eta$ D
- this $\eta$ has to do only with ohmic losses in the antenna
- in Tx, these losses involve power fed to the antenna which is radiated but heats the antenna structure.
# 2.2 Pattern Multiplication
## 2.2.A Concept
- Definition:
	- pattern multiplication states that the total far-field radiation pattern of any array is the product of the element pattern (single antenna) and the array factor (pattern due to array configuration).
	- it assumes identical, similarly oriented elements.
	- this principle allows separate analysis of element radiation and array interference effects
- Importance of Antenna array
	- array provide directional control without physically moving antennas
	- they enable beam steering (phased array), high gain, and null placement for interference rejection
	- arrays achieve performance unattainable with single elements, crucial for radar, 5G and satellite systems.
- Principle of Pattern Multiplication
	- The principle states: Total array pattern = Element pattern x Array factor.
	- The element pattern depends on individual antenna geometry.
	- the array factor depends on element spacing, excitation amplitudes and phases.
	- this separation simplifies array design and analysis significantly.
- Linear Array
	- A linear array is an arrangement of antenna elements along a straight line.
	- elements are equally spaced with progressive phase shifts.
	- it produces a fan-shaped beam that can be electronically steered in one plane.
	- common configurations include broadside and endfire arrays.
- 2D antanna array
	- a 2D array places elements in a plane (rectangular or circular grid).
	- it enables beam steering in both azimuth and elevation.
	- provides higher gain, narrower beams and better sidelobe control than linear arrays
	- used in advanced radar, MIMO systems, and satellite communications.
## 2.2.B End Fire and Broadside Array
| Parameter                    | End Fire                                                                                                                    | Broadside Array                                                                                                               |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Direction of max radiation   | Along the axis of the array (parallel to the line of elements)                                                              | Perpendicular (broadside) to the axis of the array                                                                            |
| Phase requirement ($\alpha$) | Requires a progressive phase shift between elements<br>$\alpha$ = $\pm\ \beta$d <br>($\beta$ = phase constant, d = spacing) | elements are fed in phase<br>$\alpha$ = 0                                                                                     |
| Typical element spacing      | often d = $\lambda$/4, or smaller                                                                                           | typically d = $\lambda$/2 to avoid grating lobes                                                                              |
| Beamwidth                    | Narrower beamwidth along the array axis.                                                                                    | Broader beamwidth in the plane perpendicular to the axis                                                                      |
| directivity                  | high directivity along a single end fire direction.                                                                         | high directivity in a plane perpendicular to the array, <br>but radiates in 2 opposite broadside direction for a linear array |
| 3D radiation pattern         | produces a pencil beam along the array's axis                                                                               | produces a fan shaped beam                                                                                                    |
| application example          | used where radiation is to be concentrated along the line of the array                                                      | used where coverage is needed perpendicular to the array                                                                      |
| multiplying of main lobe     | typically one main lobe (unidirectional)                                                                                    | typically 2 main lobes                                                                                                        |
| no. of element               | not significant if odd/even                                                                                                 | usually odd number.                                                                                                           |
| figure:                      | ![[b.jpg]]                                                                                                                  | ![[a.jpg]]                                                                                                                    |
## 2.2.C Various Radiation Patterns
![[Pasted image 20260126223238.png]]
![[2l.png]]
![[3l2.jpg]]
![[3l22.png]]
## 2.2.D Array of two element isotropic radiation
![[Pasted image 20260126223826.png]]
![[Pasted image 20260126223838.png]]
- +ve term will produce retardation
- -ve term will advance phase
	- of what the phase would be if the source was at origin
- field intensity at P due to antenna 1:
- E1 $$E_{1}=E_{0}e^{-j\ \dfrac{\alpha}{2}}e^{-j\left(\dfrac{2\pi}{\lambda}\right)\left(\dfrac{d}{2}\cos\left(\theta\right)\right)}$$
- E2 $$E_{2}=E_{0}e^{j\ \dfrac{\alpha}{2}}e^{j\left(\dfrac{2\pi}{\lambda}\right)\left(\dfrac{d}{2}\cos\left(\theta\right)\right)}$$
- The resultant field intensity at P due to 1 and 2 is: $$E=E_{1}+E_{2}$$
- then,
  $$E_{0}\left(e^{-j\ \dfrac{\alpha}{2}}e^{-j\left(\dfrac{2\pi}{\lambda}\right)\left(\frac{d}{2}\cos\left(\theta\right)\right)}+e^{j\ \dfrac{\alpha}{2}}e^{j\left(\dfrac{2\pi}{\lambda}\right)\left(\dfrac{d}{2}\cos\left(\theta\right)\right)}\right)$$
- $$2E_{0}\left(\frac{e^{-j\left(\frac{\alpha}{2}+\frac{2\pi}{\lambda}\cdot d\cos\left(\theta\right)\right)}+e^{j\left(\frac{\alpha}{2}+\frac{2\pi}{\lambda}\cdot d\cos\left(\theta\right)\right)}}{2}\right)$$
- $$E=2E_{0}\cos\left(\frac{\alpha}{2}+\frac{2\pi}{\lambda}\cdot d\cos\left(\theta\right)\right)$$
- $$E_{n}=\frac{E}{2E_{0}}=\cos\left(\frac{\alpha}{2}+\frac{2\pi}{\lambda}\cdot d\cos\left(\theta\right)\right)$$
### D.i Conditions
#### D.i.a  Broadside
condition: d = $\lambda$/2, $\alpha$ = 0
En = cos$\left(\dfrac{\pi}{2}\cos(\theta)\right)$
figure:
![[1.jpg | 400]]
#### D.i.a  Endfire - 1
condition: d = d = $\lambda$/2, $\alpha$ = $\pi$
En = - sin$\left(\dfrac{\pi}{2}\cos(\theta)\right)$
figure:
![[2.jpg | 440]]
#### D.i.a  Endfire - 2
condition: d = d = $\lambda$/2, $\alpha$ = $\pi$/2
En = cos$\left(\dfrac{\pi}{4} + \dfrac{\pi}{2}\cos(\theta)\right)$
figure:
![[3.jpg | 480]]
