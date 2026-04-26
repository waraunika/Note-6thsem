# 1 Free Space Propagation: PDF of receiving antenna, path loss
## 1.1 Concept
- Definition:
	- The ideal condition where a radio wave travels 
	- from a transmitting antenna to a receiving antenna 
	- in a perfect vacuum (or homogeneous, lossless dielectric)
	- with no obstructions, reflections, diffraction and atmospheric effects
- Nature:
	- A theoretical model (never perfectly achieved in practice)
	- Serves as the fundamental baseline for all real-world propagation calculations.
	- Assumes the Earth and all other obstacles are infinitely far away or absent.
- Figure:
	- ![[Pasted image 20260426092759.png]]
- Line of Sight
	- LOS = $\large X_1 + \large X_2$
		- x = $\large \sqrt{(R+h)^2 - R^2}$
		- x = $\large \sqrt{2Rh + h^2}$
		- for h $\large \ll$ R
		- x = $\large \sqrt{2Rh}$
		- for R = 6378 km = 6,370,000 m (Earth's radius)
		- x = $\large \sqrt{ 2 \cdot 6,378,000 \cdot h}$ m
		- x = 3571.55 $\large \sqrt{h}$ m = 3.571 $\large \sqrt{h}$ km
	- So finally, for two antennas at height $\large h_t$ and $\large h_r$
		- d = $\large X_1 + X_2 = 3.571 ($$\large \sqrt{h_t} + \sqrt{h_r}$) km
		- $\large h_t$ and $\large h_r$ are in meters
	- if accounted for earth's atmospheric refraction (4/3 times)
		- d = $\large X_1 + X_2 = 4.12 ($$\large \sqrt{h_t} + \sqrt{h_r}$) km
## 1.2 Power Density of Receiving Antenna
### 1.2.1 Power Density at a Distance
Consider an isotropic transmitting antenna radiating total power $\large P_t$ watts
- Power Density (power per unit area) at distance $\large R$ from the transmitter
$$\large
S = \dfrac{P_t}{4\pi R^2}\ \text{W/m}^2
$$
- For a directional transmitting antenna with gain $\large G_t$, the power density is increased in the direction of maximum radiation:
$$\large
S = \dfrac{P_t G_t}{4\pi R^2}\ \text{W/m}^2
$$
### 1.2.2 Received Power and Effective Aperture
- A receiving antenna captures power from the incident wave using its effective aperture $\large A_{eff}$.
- The received power is:
$$\large
P_r = S \times A_{eff}
$$
- The relationship between gain and effective aperture for any antenna is:
$$\large
G = \dfrac{4\pi A_{eff}}{\L^2}\ \Rightarrow\ A_{eff} = \dfrac{G\L^2}{4\pi}
$$
### 1.2.3 Friis Transmission Equation
- Substituting power density and effective aperture:
$$\large
\begin{align}
P_r &= \left( \dfrac{P_t G_t}{4\pi R^2} \right) \times \left( \dfrac{G_r \L^2}{4\pi} \right)\\
\text{or, } P_r &= P_t G_t G_r \left( \dfrac{\L}{4\pi R} \right)^2\\
\therefore\ \dfrac{P_r}{P_t} &= G_t G_r \left( \dfrac{\L}{4\pi R} \right)^2
\end{align}
$$
$$\large

$$
- Alternative forms:
	- In terms of effective apertures:
$$\large P_r = P_t \left( \dfrac{\L}{4\pi R} \right)^2 \cdot \dfrac{4\pi A_{\text{eff, t}}}{\L^2} \cdot \dfrac{4\pi A_{\text{eff, r}}}{\L^2}\ =\ P_t \dfrac{A_{\text{eff, t}} \cdot A_{\text{eff, r}}}{\L^2 R^2} $$
	- In terms of antenna areas
$$\large \dfrac{P_t}{P_r} = \left( \dfrac{4\pi R}{\L} \right)^2 \cdot \dfrac{1}{G_t G_r}\ =\ \dfrac{(\L R)^2}{A_{\text{eff, t}} \cdot A_{\text{eff, t}}} $$
	- in dB form
$$\large
[P_r] = [P_t] + [G_t] - [G_r] - [L_{\text{free}}]\ (\text{dB})
$$
## 1.3 Path Loss
### 1.3.1 Definition
- the ratio of
- transmitted power to received power
- in free space
- assuming isotropic antenna
	- ($\large G_t = G_r = 1$)
- which is equal to:
$$\large
L_{\text{free}} = \dfrac{P_t}{P_r} = \left( \dfrac{4\pi R}{\L} \right)^2
$$
- With antenna gains included
$$\large
\dfrac{P_t}{P_r} = \dfrac{1}{G_t G_r} \left( \dfrac{4\pi R}{\L} \right)^2
$$
### 1.3.2 FSL in dB
$$\large
\begin{align}
[L_{\text{free}}] &= 10 \log_{10} \left( \dfrac{4\pi R}{\L} \right)^2\\
&= 20 \log_{10} \left( \dfrac{4\pi R}{\L} \right)\\
&= 20 \log_{10}(4\pi) + 20\log_{10}  \left( \dfrac{R}{\L} \right)\\
&\approx 22 + 20\log_{10}  \left( \dfrac{R}{\L} \right)
\end{align}
$$
### 1.3.3 Key Observations about FSPL
| Property                  | Behavior                                  |
| ------------------------- | ----------------------------------------- |
| **Frequency dependence**  | Doubling $f$ → +6 dB loss                 |
| **Distance dependence**   | Doubling $R$ → +6 dB loss                 |
| **Wavelength dependence** | Shorter $\lambda$ → higher loss           |
| **Physical meaning**      | Loss due to spherical spreading of energy |

# 2 Plane earth propagation: ground reflection, effective antenna height, the two ray
## 2.1 Concept of Plane Earth Propagation
- Definition:
	- A propagation model that 
	- considers the Earth as a 
		- perfectly flat, conducting plane,
	- reflecting radio waves
- pplicability:
	- Primarily for VHF/UHF terrestrial communication where the Earth's curvature is negligible over the path length.
- Key phenomenon:
	- the receiving antenna captures two signals:
	- Direct wave (LOS path)
	- Ground-reflected wave (via reflection from Earth's surface)
- Figure:
	- ![[Pasted image 20260426102340.png]]
## 2.2 Ground Reflection
### 2.2.1 Geometry
Let:
- $\large h_t$ = height of transmitting antenna (metre)
- $\large h_r$ = height of receiving antenna (m)
- $\large d$ = horizontal distance between antennas (m)
- $\large \lambda$ = wavelength (m)
Path Lengths:
- Direct path length: $\large l = \sqrt{(h_t - h_r)^2 + d^2}$
- Reflected path length: $\large x + x' = \sqrt{(h_t + h_r)^2 + d^2}$
### 2.2.2 Path Length Difference
$$\large
\begin{align}
\Delta d &= (x + x') - l\\
&= \sqrt{(h_t + h_r)^2 + d^2} - \sqrt{(h_t - h_r)^2 + d^2}\\
\end{align}
$$
For $\large d \gg (h_t + h_r)$  (far-field approximation), using Taylor series expansion:
$$\large
\begin{align}
\Delta d &= d \left( \sqrt{\dfrac{(h_t + h_r)^2}{d^2}+1}\ + \sqrt{\dfrac{(h_t - h_r)^2}{d^2}+1} \right)\\
\text{in the form of root}&\text{ of (1+x) = 1 + 0.5 x - 0.125 x}^2+ ...,\\
\text{taking only the fir}&\text{st two terms, we have:}\\
\Delta d &\approx \dfrac{d}{2} \left( \dfrac{(h_t+h_r)^2}{d^2} - \dfrac{(h_t-h_r)^2}{d^2} \right)\\

\therefore\ \Delta d &\approx \dfrac{2h_t h_r}{d}
\end{align}
$$
The phase difference due to path length difference is:
$$\large
\Delta \phi = \dfrac{2\pi\Delta d}{\L} ​\approx \dfrac{4\pi h_t h_r}{\L d}​​
$$
### 2.2.3 Reflection Coefficient
- When a wave reflects off the Earth's surface:
	- Amplitude is reduced by the coefficient $\large \Gamma$
	- Phase may change (typically $\large 180\D$ for horizontal polarization near grazing incidence)
- For a perfectly conducting ground (ideal case)
	- $\large \Gamma = 1$ (no amplitude loss)
	- Phase shift = $\large 180\D\ (\pi$ radians) -> effective negative amplitude
- For real ground $\large \Gamma < 1$, depends on:
	- Surface conductivity
	- Permittivity (dielectric constant)
	- Polarization (vertical/hoizontal)
	- Incident angle
	- Frequency
## 2.3 Effective Antenna Height
- Definition:
	- For a non-resonant (travelling wave) antenna, the effective height
	- $\large h_{\text{eff}}$ is the height of an equivalent vertical dipole that produces the same electric field strength at a given distance.
	- Formula:
$$\large
\large h_{\text{eff}} = \dfrac{1}{I_\text{in}}\int_0^H I(z) dz
$$
	- where
	- $\large I_\text{in}$ = input current at base
	- $\large I(z)$ = current distribution along antenna
	- $\large H$ = physical height
### 2.3.1 Specific cases
|Antenna Type|Current Distribution|Effective Height|
|---|---|---|
|Short monopole ($H \ll \lambda$)|Triangular (linear taper)|$h_{eff} = H/2$|
|$\lambda/4$ monopole|Sinusoidal|$h_{eff} = 2H/\pi \approx 0.64H$|
|Resonant half-wave dipole (center-fed)|Sinusoidal|$h_{eff} = \lambda/\pi$|
### 2.3.2 Importance in Propagation
- effective height appears in the received voltage equation:
	- $\large V_r = E \cdot h_\text{eff}$
- Directly affects the gain of vertical antenna: $\large G \propto h_\text{eff}^2$
- Used in determining antenna factor for EMC (Electromagnetic Compatibility) measurements
## 2.4 The Two Ray Model
### 2.4.1 Concept
- The two-ray model considers both the direct wave and the ground-reflected wave arriving at the receiver.
- These two signal interfere constructively or destructively depending on their phase difference
-  Figure:
	- ![[Pasted image 20260426105734.png]]
### 2.4.2 Total Received field
Let 
- $E_d$ be the direct wave field
- $E_r$ be reflected wave field
Assuming
- a reflection coefficient $\Gamma$ = -1
- perfect ground with 180$\D$ phase shift
$$\large
E_\text{total} = E_d + E_r = E_0 \left( \dfrac{e^{-jkl}}{l} - \dfrac{e^{-jk(x+x')}}{x+x'} \right)
$$
For $\large d \gg h_t, h_r$,the path lengths are approximately equal in amplitude but differ in phase
$$\large
E_\text{total} \approx \dfrac{E_0}{d} \left( e^{-jkl} - e^{-jk(x+x')} \right)
$$
### 2.4.3 Received Power
The magnitude of the total field is:
$$\large
|E_\text{total}| \approx \dfrac{2E_0}{d} \left| \sin\left( \dfrac{k\Delta d}{2} \right) \right|
$$
Where $\large \Delta d \approx \frac{2h_t h_r}{d}$ and $\large k = \frac{2\pi}{\lambda}$.
Substituting:
$$\large
|E_\text{total}| \approx \dfrac{2E_0}{d} \left| \sin\left( \dfrac{2\pi h_t h_r}{\lambda d} \right) \right|
$$
For small angles (when $\large \dfrac{2\pi h_t h_r}{\L d} \ll 1$), $\large \sin(x) \approx x$:
$$\large
|E_\text{total}| \approx \dfrac{4\pi E_0 h_t h_r}{\L d^2}
$$
Since power is proportional to $\large |E|^2$, the received power decays as $\large 1/d^4$ in this region:
$$\large
P_r \propto \dfrac{1}{d^4}
$$
### 2.4.4 Summary
| Region                         | Condition                            | Path Loss Exponent    |
| ------------------------------ | ------------------------------------ | --------------------- |
| **Near** (interference region) | $d$ small                            | Complex (oscillatory) |
| **Far** (far-field)            | $d \gg \frac{4\pi h_t h_r}{\lambda}$ | $d^4$ (40 dB/decade)  |
| **Extremely far**              | Signal becomes very weak             | $d^4$ continues       |
### 2.4.5 Graph of Power vs Distance
![[Pasted image 20260426110749.png | 600]]
### 2.4.6 Applications
 - Terrestrial microwave links
 - Cellular base station coverage
 - FM/TV broadcast planning (over flat terrain)
 - Radar ground clutter modeling
 - Vehicle-to-vehicle communication (low antenna heights)
### 2.4.7 Limitations
- Assumes flat, smooth Earth (no terrain variations)
- Neglects Earth's curvature, valid only for short-to-moderate distances
- - Simple reflection coefficient, real ground is complex
- no atmospheric effects accounted
# 3 Propagation model, Path loss
## 3.1 Need of models
- Purpose:
	- Predict the received signal strength (path loss) between transmitter and receiver given that:
		- frequency, distance, antenna heights, environmental factors
- Importance:
	- link budget calculation
	- cell planning (coverage prediction)
	- interference analysis
	- system optimization
## 3.2 Classification of Propagation Models
### 3.2.1 By Mechanism
|Model Type|Mechanisms Included|Frequency Range|Environment|
|---|---|---|---|
|**Free Space**|LOS only|Any (theoretical)|Vacuum|
|**Two-Ray**|LOS + Ground reflection|VHF/UHF (30-3000 MHz)|Flat terrain|
|**Plane Earth**|Ground reflection (simplified)|LF/MF/HF|Over Earth|
|**Multipath**|Reflection, diffraction, scattering|VHF/UHF/SHF|Urban, indoor|
|**Empirical**|Statistical fits to measurements|Varies|Specific environments|
### 3.2.2 By Derivation method
1. **Theoretical (Deterministic):** Based on physics (Maxwell's equations, ray tracing)
    - Free space, two-ray, knife-edge diffraction
2. **Empirical:** Based on measurements (curve-fitting)
    - Hata-Okumura, COST-231, ITU models
3. **Semi-empirical:** Hybrid approach
    - Longley-Rice, Walfisch-Ikegam
## 3.3 Multipath
### 3.3.1 Concept
- Mutlipath occurs when the transmitted signal reaches the receiver via multiple paths
- due to reflection, diffraction, and scattering from objects in the environment
- like buildings, terrain, vegetation
- Figure:
	- ![[Pasted image 20260426111351.png]]
### 3.3.2 Effects
|Effect|Description|Consequence|
|---|---|---|
|**Constructive interference**|Paths add in phase|Signal enhancement|
|**Destructive interference**|Paths add out of phase|Signal fade (deep nulls)|
|**Frequency-selective fading**|Different frequencies fade differently|Distortion in wideband signals|
|**Intersymbol interference (ISI)**|Delayed copies of symbol overlap next symbol|Data errors, need equalization|
|**Delay spread**|Spread in arrival times|Limits data rate|
|**Doppler spread**|Frequency shift due to motion|Time-varying fading|
# 4 Fresnel zones and Knife edge diffraction
## 4.1 Radiation Field Regions
![[Pasted image 20260426111539.png]]
### 4.1.1 Reactive Near-Field Region
- Definition:
	- Region immediately surrounding the antenna 
	- where reactive (stored) fields dominate over radiating fields.
- Boundary:
	- $\large R < 0.62 \sqrt{D^3 \L}$ for large antenna
	- $\large R < \dfrac{\L}{2\pi}$ for very short dipole.
- Characteristics:
	- Energy oscillates between electric and magnetic storage
	- not useful for communication (no wave propagation)
	- antenna impedance sensitive to objects that are nearby
### 4.1.2 Radiating Near-Field (Fresnel) Region
- Definition:
	- Region betwene reactive near-field and far-field where
	- radiating fields dominate
	- but the angular field distribution is still distance-dependent
- Boundary:
	- $\large 0.62 \sqrt{D^3 \L} \le R < 2D^2 \L$ 
- Characteristics:
	- Fresnel zones concept applies here
	- Phase variation across antenna aperture is significant ($\large < \pi/8$ phase error criterion)
	- Used for fresnel zone clearance analysis
	- Antenna pattern is not fully formed (Distance dependent)
### 4.1.3 Far-Field (Fraunhofer) Region
- Definition:
	- Region where angular field distribution is independent of distance from the antenna
- Boundary:
	- $\large R \ge 2D^2/\L$ (minimum)
- Characteristics
	- Waves appear as plane waves locally
	- antenna pattern is fully developed
	- Friis transmission equation applies
	- Power decays as $\large 1/R^2$ 
### 4.1.4 Summary
|Region|Distance Range|Field Type|Pattern|Phase Error Criterion|
|---|---|---|---|---|
|Reactive Near-Field|$R < 0.62\sqrt{D^3/\lambda}$|Reactive dominated|Not applicable|N/A|
|Fresnel (Radiating Near-Field)|$0.62\sqrt{D^3/\lambda} \le R < 2D^2/\lambda$|Radiating|Distance-dependent|$<\pi/8$|
|Fraunhofer (Far-Field)|$R \ge 2D^2/\lambda$|Plane wave|Fixed|$<\pi/16$|
## 4.2 Fresnel Zones
### 4.2.1 Concept
- Fresnel zones are ellipsoidal regions between a transmitter and receiver that describe the phase relationship of different propagation paths.
- They are used to determine the clearance required around the LOS to avoid significant diffraction loss.
- Figure:
	- ![[Pasted image 20260426112448.png]]
### 4.2.2 Nth Fresnel Zone
- The nth fresnel zone consists of all points $P$ such that the path length difference between
	- the direct path (Tx -> Rx)
	- the reflected/diffracted path (Tx -> P -> Rx)
- is exactly $\large n\ \L/2$ (i.e. n * half wavelengths)
- mathematically:
$$\large
(Tx \rightarrow P \rightarrow Rx) - (Tx \rightarrow Rx) = \dfrac{n\L}{2}
$$
where $n = 1, 2, 3 \ldots$
### 4.2.3 Radiation of nth Fresnel Zone
- For a point at a distance $\large d_1$ from Tx and $\large d_2$ from Rx
	- (with $\large d = d_1 + d_2$),
- the radius of the nth Fresnel zone perpendicular to the LOS path is:
$$\large
r_n = \sqrt{\dfrac{n\L d_1 d_2}{d_1 + d_2}}
$$
For the first Fresnel Zone (n = 1):
$$\large
r_1 = \sqrt{\dfrac{\L d_1 d_2}{d_1 + d_2}}
$$
If $\large d_1 = d_2 = d/2$:
$$\large
r_n = \sqrt{\dfrac{n \L (d/2) \cdot (d/2)}{d}} = \sqrt{\dfrac{n\L d}{4}}
$$
Figure:
![[Pasted image 20260426113140.png]]
### 4.2.4 Importance of First Fresnel Zone
- 60-80% of transmitted power is contained within the first Fresnel zone
- if the first Fresnel Zone is 50% or more blocked, significant diffraction loss occurs
	- typically > 6 dB
- Rule of thumb:
	- for diffraction loss < 0.5 dB, the first Fresnel Zone must be atleast 60% clear.
	- i.e. clearance criterion: Clearance >= 0.6 x r$\large _1$
### 4.2.5 Shadow Region
- Definition:
	- The shadow region is the area behind an obstacle
	- hill, building, etc.
	- where the direct LOS wave
		- is completely blocked
	- and only diffracted and scattered field exist.
- Nature:
	- Field strength decays rapidly with distance into the shadow
	- diffraction is the primary propagation mechanism
	- the field is not zero (unlike optical shadow) due to wave nature
- Geometrical shadow:
	- region where straight-line ray theory predicts no signal
- Radio Shadow:
	- Region where signal is significantly reduced but still present due to diffraction
![[Pasted image 20260426114121.png | 600]]
## 4.3 Knife Edge Diffraction
### 4.3.1 Concept
- Knife edge diffraction is a simplified model
	- for diffraction over a thin, sharp obstance
	- like a mountain ridge, building edge or rooftop
	- whose thickness is negligible compared to its height
- The obstacle is assumed to be perfectly absorbing
	- i.e. no reflection
- Figure same as above
### 4.3.2 Huygens' Principle
Diffraction can be explained as:
- Every point on a wavefront acts as a source of secondary wavelets
- the new wavefront is envelope of these wavelets
- when an obstacle blocks part of the wavefront, the remaining wavelets "bend" into the shadow region.
### 4.3.3 Diffraction Parameter
The Fresnel-Kirchoff diffraction parameter $\large \nu$ characterizes thee diffraction geometry:
$$\large
\nu = h \sqrt{\dfrac{2(d_1 + d_2)}{\L d_1 d_2}}
$$
where:
- h -> obstacle height above (positive) or below (negative) the LOS path
- $\large d_1$ -> distance from Tx to obstacle
- $\large d_2$ -> distance from obstacle to Rx
- $\large \L$ -> wavelength
Alternative forms:
$$\large
\nu = \theta \sqrt{\dfrac{2(d_1 + d_2)}{\L d_1 d_2}} = \sqrt{ \dfrac{2h\theta}{\L}} = \sqrt{\dfrac{2d}{\L}}\cdot \alpha_1 \alpha_2
$$
where:
- $\large \theta$ is the diffraction angle in radians
Figure:
![[Pasted image 20260426115243.png | 700]]
### 4.3.4 Diffraction Loss as a function
The diffraction loss relative to free space is given as:
$$\large
L_d(\nu) = -20\log_{10} \left(\left| \int_v^\infty \dfrac{e^{-j\pi\ t^2/2}}{\int_0^\infty e^{-j\pi\ t^2/2} dt} dt \right|\right)
$$
#### 4.3.4.1 Approximations
| $\nu$ Range       | Diffraction Loss $L_d$ (dB)                           |
| ----------------- | ----------------------------------------------------- |
| $\nu \le -1$      | $L_d \approx 0$ (LOS, negligible loss)                |
| $-1 < \nu < 0$    | $L_d \approx 6 + 20\log_{10}(\sqrt{1 - \nu^2} - \nu)$ |
| $0 \le \nu \le 1$ | $L_d \approx 6 + 20\log_{10}(\sqrt{1 + \nu^2} - \nu)$ |
| $1 < \nu \le 2.4$ | $L_d \approx 13 + 20\log_{10}(\nu)$                   |
| $\nu > 2.4$       | $L_d \approx 20\log_{10}(\nu)$ (approx)               |
Simplified emperical formula:
$$\large
L_d(\nu) = \left\{
\begin{matrix}
	0 & \nu \le -0.7\\
	6 + 20\log_{10}(\nu+\sqrt{\nu^2+1}) & v > -0.7
\end{matrix}
\right.
$$

### 4.3.5 Special Cases
| Case                     | $\nu$       | Diffraction Loss                | Description               |
| ------------------------ | ----------- | ------------------------------- | ------------------------- |
| LOS, obstacle below path | $\nu < 0$   | $0$ to $6$ dB                   | Partial blockage          |
| Knife edge at LOS        | $\nu = 0$   | $6$ dB                          | Obstacle just touches LOS |
| Obstacle above LOS       | $\nu > 0$   | $>6$ dB                         | Significant blockage      |
| Deep shadow              | $\nu \gg 1$ | Increases as $20\log_{10}(\nu)$ | Very high loss            |
### 4.3.6 Rounded Surface Diffraction
- For rounded obstacle (hills, mountains) rather than sharp knife-edges:
	- Effect: Diffraction loss is greater than for a knife-edge of the same height
	- Reason: The rounded surface causes additional spreading of the diffracted wave
	- modeling: often approximated by an equivalent knife-edge with an effective height or by more complex modeels.
- Key differences from knife-edge:
	- Smoother transition into shadow
	- Higher loss for same obstacle height
	- Frequency dependence is more complex
### 4.3.7 Practical Application of KED
- **Terrestrial microwave link design**: clearance over ridges
- **Cellular network planning**: coverage behind buildings
- **TV and FM Broadcast**: propagation over hills
- **Radar Shadowing**: target detection behind terrain
- **Air-Ground communication**: over mountain ranges
- **EMC analysis**: interference paths
### 4.3.8 Diffraction vs Fresnel Zones
- When an obstacle **penetrates the first Fresnel zone**, diffraction loss begins.
- At $\nu = 0$ (obstacle exactly at LOS), the first Fresnel zone is **50% blocked**, causing ~6 dB loss.
- For $\nu = -1$ (obstacle below LOS), the first Fresnel zone is essentially clear → negligible loss.