# 1 Broad Classification
## 1.1 Isotropic Antenna
### 1.1.1 Concept
- definition:
	- a hypothetical lossless antenna that radiates power equally in all directions.
	- conceptual model used as a fundamental reference in antenna theory and radio engineering
- nature:
	- idealized and does not exist in physical world
	- serves as a standard baseline for comparing real-world antenna
### 1.1.2 Features
- radiates uniformly in all directions (spherical radiation pattern)
- if a fictitious or imaginary antenna, an ideal case scenario
- is considered lossless (no energy loss in the antenna itself)
- has a directivity and gain of 1 (or 0 dB), making it the standard reference
- also referred to as unipole antenna
- the beam solid angle ($\Omega_A$) is equal to 4$\pi$ steradians
- key formulas derived from it:
	- Power density at a distance r: P = $\dfrac{P_t}{4\pi r^2}$ 
	- electric field intensity: E = $\sqrt{\dfrac{30 P_t}{r^2}}$ 
	- magnetic field intensity: H = $\dfrac{1}{4\pi r} \sqrt{\dfrac{P_t}{30}}$
	- more derivation for this below, not necessary
### 1.1.3 Specifications
- Gain: 1 (0 dBi). the i denotes gain relative to an isotropic radiation
- directivity: 1
- radiation pattern: perfect spher
- polarization: not defined, as it is a conceptual model
- impedance: not typically specified
- bandwidth: 360$^0$ in both azimuth and elevation planes
- efficiency: Assumed to be 100% (lossless)
### 1.1.4 Adv/Disadv
- Adv:
	- Non-existent: cannot be physically constructed
	- Simplifies Analysis: Makes fundamental equations for power density and field strength straightforward and easy to derive
	- foundation for theory: essential for understanding more complex antenna concepts and communication formula
- Diasdv:
	- non-existent: cannot be physically constructed
	- No Practical Use: Cannot be used for any real communication, sensing or broadcasting application due to its lack of directionality.
	- Inefficient for Communication: Real systems require directionality (gain) to focus energy for efficient point-to-point links or to avoid interference
### 1.1.5 Application
- exclusively theoretical and analytical reference standard.
### 1.1.6 Unnecessary Derivation
- power uniformly distributed over the surface of sphere of radius r,
	- P = $\dfrac{P_t}{4\pi r^2}$
		- where,
		- P is power received at a distance r from isotropic antenna
		- Pt is the total power transmitted
- field intensity at a point P as for electromagnetic waves
	- $\eta = \dfrac{E}{H}$
- since, P  = E H, thus,
	- P = $\dfrac{E^2}{\eta}$ 
- Hence, P =  $\dfrac{E^2}{\eta}$ = $\dfrac{P_t}{4\pi r^2}$
- we have $\eta$ = 120$\pi$
- $$E^2 = \eta \dfrac{P_t}{4\pi r^2} = 120\pi \dfrac{P_t}{4\pi r^2} = 30 \dfrac{P_t}{r^2}$$
- E = $$\sqrt{30 \dfrac{P_t}{r^2}}$$
- H = $$\dfrac{E}{\eta} = \dfrac{\sqrt{30 \dfrac{P_t}{r^2}}}{120\pi} = \sqrt{\dfrac{30 P_t}{120^2\ \pi^2\ r^2}} = \dfrac{\sqrt{P_t}}{4\pi r \sqrt{30}} = \dfrac{1}{4\pi r} \sqrt{\dfrac{P_t}{30}}$$
- Directivity:
	- D = $\dfrac{U_{max}}{U_{av}}$ = $\dfrac{U_{m}}{U_{0}}$ = $\dfrac{4\pi U_m}{4\pi U_0}$ = $\dfrac{4\pi U_m}{P}$ 
		- where,
		- P is total power radiated
	- since, U$_0$ = P / 4$\pi$, and P = U$_m$ $\Omega_A$
	- so, D = $\dfrac{4\pi}{\Omega_A}$
		- where, $$\Omega_A = \int \dfrac{S(\theta, \phi)}{S(\theta, \phi)_{max}} d\Omega$$
	 - This is beam solid angle or Beam Area
	- for isotropic radiator, the beam solid angle or, beam area, $\Omega_A$ = 4$\pi$
	- then, D$_{Isot}$ = 1
---
## 1.2 Omni Directional Antenna
### 1.2.1 Concept
- Definition:
	- antenna that radiates power uniformly in all directions in one plane, usually azimuth/horizontal while having a directional pattern in the perpendicular plane (usually elevation/vertical)
	- non-directional in azimuth, but has gain and directivity in elevation.
	- often visualized as a doughnut shaped or apple shaped radiation pattern
	- example: quarter wave vertical antenna mounted over a ground plane.
### 1.2.2 Features
- Radiates equally in all horizontal directions (360$^0$ azimuth)
- has a directional pattern in the vertical plane (not isotropic)
- also called a non-directional antenna in the context of horizontal coverage.
- Physically realizable and widely used (unlike n isotropic antenna)
- often a vertically polarized antenna
- for a $\lambda$/4 monopole, an electrical image in the ground plane creates the equivalent of a half have dipole radiation pattern in the upper hemisphere
- commonly used in MW broadcasting, where it is known as Marconi antenna
- primary propagation waves are ground wave and ground-reflected wave.
- sky wave propagation occurs at night when the ionosphere's D layer disappears.
### 1.2.3 Specifications
- typical types:
	- monopole ($\lambda$/4), Whip, Marconi, Telescopic
- Common gain:
	- ~2.15 dBi (relative to isotropic) or 0 dBd (relative to dipole)
- Radiation resistance: 36 $\Omega$ for a thin $\lambda/4$ monopole over perfect ground
- Polarization: Typically vertical
- Beamwidth: 360 in azimuth ($\phi$), ~45 to 90 in elevation ($\theta$), depending on design
- HPBW: approximately 90 in the elevation plane for an ideal monopole
- bandwidth: typically narrowband, 10% fractional bandwidth, for simple designs.
- frequency bands: LW, MW, VHF. common for 500 kHz to 150 MHz
- power handling: from a few kW for local broadcasting upto ~ 5 MW for high-power AM stations
### 1.2.4 Working
- vertical conductor (monopole) is fed against a ground plane (earth or vehicle body)
- the ground plane acts as a reflector, creating an image antenna that forms the lower half of the equivalent radiation pattern
- at MF, HF (e.g., AM broadcast), it primarily launches a ground wave that follows the earth's curvature via diffraction, providing regional coverage.
- sky wave propagation occurs at night, when ionospheric absorption decreases allowing for longer-distance communication
- loading can be applied to reduce physical size:
	- adding a series inductor (coil) makes the antenna electrically longer allowing a physically shorter whip.
	- adding a series capacitor has the opposite effect.
### 1.2.5 Adv / Disadv
1. Adv:
	- Provides uniform 360 degree coverage in the horizontal plane, ideal for broadcasting to multiple receivers in all directions
	- simple and inexpensive to construct
	- vertically polarized radiation couples well with ground wave propagation
	- easy to install
	- low profile versions (whip antenna) are suitable for mobile applications
2. Disadv
	- Lower gain compared to directional antennas, as energy is spread over a wide area
	- susceptible to noise:
	- limited range
	- skywave fading
	- large size at low frequencies
### 1.2.6 Applications
- AM Medium wave broadcasting
- FM Radio and TV broadcasting
- Mobile communications: Whip antenna on car, handheld radio (walkie-talkie)
- base stations
- consumer electronics
- GPS receiver
- RFID readers (to detect tags from any direction within a plane)
### 1.2.7 Figure
- omni directional antennas are fed unbalanced withh respect to ground
- ![[Pasted image 20260126135836.png]]
---
# 2 Linear Dipole/Monopole
Formally, not been asked in exam in detail, so just bits and pieces for concept without much formatting upto Folded Dipole Antenna.
## 2.1 Short and Very Short Dipole
- infinitesimal (very short) dipole
	- omnidirectional
	- L $\le$ $\lambda/50$ (i.e. L << $\lambda$) not very practical antenna 
- short dipole
	- aka small dipole
	- $\dfrac{\lambda}{50}< l < \lambda/10$ or, $l \le \lambda/10$ 
## 2.2 Half-wave Dipole
- Dipole Antenna aka Doublet
- aka Hertz antenna
- $l = \lambda/2$
- if long dipole then $l \ge \lambda/2$
- having distributed R, L, C
- the electrical dimensions of the two are the same
- symmetrical antenna in which two ends are at equal potential relative to the midpoint.
- figure:
	- ![[Pasted image 20260310195049.png]]
- current and voltage distribution on a half wave dipole, I is maximum at the midpoint and minimum at theends
- whereas v is maximum at the ends and minmum at the mid point
- a half wave dipole is physically 5% shorter than the free space wavelength, because of propagation of the wave along each arm is 5% is slower thahn C.
- figure for current/voltage distribution across a half wave dipole:
	- ![[Pasted image 20260310195314.png]]
- figure for comparison of radiation pattern with short dipole
	- ![[Pasted image 20260310195409.png]]
- may be present in the form of slotted sheet, curved sheet cylinder
- figure for comparison of $\lambda/2$, resonant $\lambda/2$ and full $\lambda$ structure:
	- ![[Pasted image 20260310195613.png]]
- Applications:
	- VHD and UHF bands
	- Driven element for Yagi Antenna
	- concept used in log periodic antennas
	- TV channel receiving
## 2.3 Folded Dipole
- figure:
	- ![[Pasted image 20260310195655.png]]
## 2.4 Monopole
### 2.4.1 Concept
- Definition:
	- A monopole antenna consists of a single conducting rod or element mounted perpendicularly over a ground plane (which can be natural; earth or artificial sheet, car roof)
	- It is effectively one half of a dipole antenna, with the ground plane acting a mirror to create the missing half electrically.
- Nature:
	- Category of Long Wire Antenna
	- The most common and practical vertical antenna, especially for mobile and broadcasting
	- physically realizable, simple and extremely rugged
	- often called **Marconi Antenna** in AM broadcasting
	- often called **Whip Antenna** in mobile/VHF.
### 2.4.2 Features
- Vertical orientation over a conducting ground plane.
- Omnidirectional in azimuth (horizontal plane)
	- radiates equally in all 360$\D$ horizontally.
- Direction in elevation (vertical plane)
	- maximum radiation is along the horizon (low angle)
	- ideal for ground wave and short-range communication
- The ground plane can be real earth (with radial wires)
	- or an artificial metallic sheet.
- for a perfect quarter-wavelength $\large \lambda/4$ monopole,
	- the ground plane creates an image antenna that,
	- together with the real element,
	- behaves like a half-wave dipole in the upper hemisphere.
- Vertically polarized
	- electric field is vertical, which couples well with ground wave propagation
	- and vertical whip antenna on vehicles
- simple impedance matching 
	- can be fed directly with 50$\large \Omega$ if properly tuned
- can be electrically lengthened via loading coils (inductors) when physically height is limited
- can be electrically shortened using capacitive hats (not common).
### 2.4.3 Antenna Specification
| Parameter             | Typical Value / Description                                    |
| --------------------- | -------------------------------------------------------------- |
| Common Length         | $\lambda/4$ (most common), also $\lambda/8$, $3\lambda/8$, etc |
| Radiation resistance  | ~36 $\Omega$, half of dipole's 72 $\Omega$                     |
| Directivity           | ~3.2 (5 dBi) for $\lambda/4$ monopole                          |
| Gain                  | ~2.5 dBi relative to isotropic                                 |
| Polarization          | Vertical (linear)                                              |
| Impedance (practical) | 30-50 $\Omega$                                                 |
| BW                    | Narrow to moderate, typically 5-10% FBW                        |
| Efficiency            | 50-95% depending on ground conductivity                        |
| Frequency range       | From LF (100 kHz) to VHF (300 MHz)                             |
| Power handling        | Milliwatts to megawatts (AM broadcast: 50-100 kW)              |
### 2.4.4 Working Principle
- The monopole is fed between its base and the ground plane.
- The ground plane reflects the signal, creating an image of the monopole on the opposite sides
- The combination of the real monopole and its image behave like a vertical dipole of length 2h where $h$ is the physical height
- For a $\lambda/4$ monopole, the image creates a virtual $\lambda/2$ dipole
- Radiation pattern is the upper half of a dipole's donut shape, giving maximum radiation along horizon
- The ground plane eliminates radiation downward,
	- doubling gain in the upper hemisphere compared to isotropic radiation
- at medium frequencies (AM), the antenna launches a ground wave that follows the Earth's curvature via diffraction
- at High Frequencies (HF) and at night on MF, skywave propagation occurs when the signal bounce off the ionosphere.
### 2.4.5 Adv/Disadv
- **ADV**
	- simple, ruggeed, and low-cost to construct
	- omnidirectional coverage in horizontal plane
	- vertically polarized matches common mobile whip antennas
	- low angle radiation good for local ground wave
	- easy to feed with coaxial cable
	- small footprint/size
	- can be made physically shorter/longer
- **DISADV**
	- requires a ground plane
	- lower gain than directional antennas
	- susceptible to noise
	- limited range
	- large physical size at low frequencies
	- narrow bandwidth
### 2.4.6 Application
- AM Medium wave broadcasting (500 kHz to 1.7 MHz)
- FM Radio and TV Broadcasting (VHF)
- Mobile communications (whip antenna/walkie-talkie)
- Base stations for cellular/police
- consumer electronics (wifi routers, gps receivers)
- aerospace and marine for VHF communication
- Military for manpack radios (whip)
- ground wave communication (short range HF communication 2-10MHz over land or sea)
### 2.4.7 Figure
![[Pasted image 20260425082432.png]]


---
# 3 Travelling Wave Antennas
## 3.1 Description
### 3.1.1 Concept
- definition:
	- antennas that operate with a predominantly travelling wave of current along their structure, as opposed to standing waves in resonant antennas.
- a continuous conductor is terminated with a matched load resistor at its end to absorb the travelling wave, preventing reflections and standing waves.
- non-resonant antennas, characterized by progressive wave propagation and resistive termination
### 3.1.2 Features
- Non-resonant operation: no standing waves, operates over a wide frequency range
- terminated design: ends in a matched resistor to absorb forward energy, minimizing reflections
- unidirectional radiations: typically produces a single major lobe in the direction of wave travel.
- frequency insensitivity: input impedance is predominantly resistive and varies little with frequency
- continuous source radiation: radiation occurs along the entire length of the antenna not just at discontinuities
- propagation method: primarily designed for skywave (ionospheric) propagation
- no reflected wave components: virtually all incident energy is either radiated or absorbed by the termiantion.
### 3.1.3 Specification
- BW: very wide (multiple octaves possible)
- efficiency: ~50% theoretical maximum (half the power absorbed by termination resistor)
- radiation pattern: unidirectional main lobe with minor side lobes.
- input impedance: primarily resistive, typically 600 - 800 $\Omega$ for common types
- polarization: Generally horizontal linear polarization
- directivity: moderate to high, depending on length and configuration
- power handling: high (termination resistor must dissipate significant power)
### 3.1.4 Working
- RF energy travels along the antenna wire as a traveling wave.
- As the wave propagates, it continuously radiates energy along its length.
- The remaining energy reaches the termination resistor, where it is absorbed as heat rather than reflected.
- This absence of reflected waves eliminates standing wave patterns, making the antenna non-resonant.
- The cumulative radiation from all points along the wire creates a directional pattern with maximum radiation in the forward direction.
### 3.1.5 Adv / Disadv
1. Adv
	- Very wide BW
	- stable impedance
	- unidirectional pattern
	- no tuning required
	- good for HF/skywave
2. Disadv
	- low efficiency
	- large physically size
	- complex construction
	- high power consumption, lost in resistor
	- fixed direction
### 3.1.6 Applications
- HF point-to-point communication: long distance skywave links
- shortwave broadcasting
- military communication
- direction-finding array
- receiving antenna where wide bandwidth is prioritized over efficiency
### 3.1.7 Figure:
1. Antenna
   ![[Pasted image 20260126141408.png | 600]]
2. Radiation Pattern for travelling/standing wave
   ![[Pasted image 20260126141935.png | 600]]
---
## 3.2 Single/Long Wire Antenna
### 3.2.1 Concept
- definition:
	- straight conductor that is long compared to the wavelength (typically 2$\lambda$ to 8$\lambda$), operating either as a resonant (unterminated) or non-resonant (terminated) antenna
- aka Beverage antenna, wave antenna, or harmonic antenna
- functions as a lossy transmission line where radiation occurs continuously along its length rather than at specific points
### 3.2.2 Features
- length is 2$\lambda$ to 8 $\lambda$ long
- can be configured for unidirectional (terminated) or bidirectional (unterminated) radiation
- polarization: horizontal if wire is horizontal to ground, vertical if wire is vertical
- radiation angle is approximately 45 degree above horizon when wire is parallel to ground
- harmonic operation: can operate on multiple harmonics of its fundamental frequency
- gain increases directly with number of half wavelengths (N)
- directivity increases and radiation angle ($\theta$) decreases as antenna length increases
### 3.2.3 Antenna Specification
- length formula:
	- physical length (in feet) = 429 $\dfrac{N - 0.05}{f}$ , f in MHz
	- feed point impedance of about 500 to 600 Ohm
	- radiation resistance Rr ~ 138 $\log_{10} (4h/d)$, where h = height above ground, d = wire diameter
	- BW: wide
	- polarization: horizontal or vertical, depending on orientation
	- efficiency ~ 50%
	- frequency range: suitable for amateur bands (144 - 148 MHz), LF and HF bands
	- Apex angle, varies from ~ 35 degree for 8 $\lambda$ to ~ 70 for 2$\lambda$ length
### 3.2.4 Working
- when antenna length accommodates multiple half-wavelengths at the operating frequency, it becomes more effective with higher gain and better directivity
- for the terminated version, the travelling wave propagates along the wire, radiates continuously and remaining energy is absorbed by the termination resistor
- for the unterminated version, standing waves form, creating a bidirectional pattern
- the feed point location determines the direction of main lobe(s)
- wire orientation determines polarization (horizontal wire -> horizontal polarization)
- radiation angle decreases as wire length increases
- primarily used in HF bands, suitable for both transmission and reception
### 3.2.5 Adv / Disadv
- adv
	- simple construction
	- low cost
	- wide bandwidth
	- high input impedance
	- flexible installation (can be installed vertically, horizontally or sloped)
	- good for HF/Skywave
- disadv:
	- strong minor lobes
	- low efficiency
	- large space requirement
	- directional limitations
	- susceptible to noise
### 3.2.6 application
- commercial, military
- amateur radio
- receiving antenna
- tunnel/enclosed space communication
- shortwave listening
### 3.2.7 Figure:
1. general working of long wire
   ![[Pasted image 20260126150126.png | 600]]
2. gain comparison with length
   ![[Pasted image 20260126150410.png | 600]]
---
---
## 3.3 V Antenna
### 3.3.1 Concept
- Definition:
	- an antenna formed by two long wire antennas arranged in V shape, either terinated (non resonant) or unterminated (resonant)
- combines radiation from two long wire elements to create a more directional pattern than a single long wire.
- The phase relationship and physical configuration determine radiation characteristics.
### 3.3.2 Features
- shape is of V letter
- two configuration:
	- terminated V: non resonant, unidirectional, end-fire radiation, wideband
	- unterminated V: Resonant, bidirectional (broadside radiation), narrowband
- Phase excitation: the two wires are fed 180 degree out of phase
- apex angle optimization: critical parameter 35 - 75 that, along with leg length, determines radiation pattern shape and direction
- radiation pattern relationship: beam characteristics depend on the relationship between beam angle (theta) and V angle (beta)
	- θ = β: Beam along antenna axis (optimal)
	- θ > β: Beam tilted upward from axis
	- θ < β: Beam splits into multiple lobes
- gain enhancement: approximately double that of a single long wire antenna
### 3.3.3 Specifications
- frequency range: 3- 30 MHz (HF band)
- Gain of 7-12 dBi (higher than single long wire)
- apex angle 35 degree for 8$\lambda$ legs to 75 degree for 2$\lambda$ legs, optimal around 72
- radiation angle: upto 45 degree above horizon
- termination resistnace: 400 to 800 $\Omega$
- bandwidth:
	- terminated: wideband
	- unterminated: narrowband
- Polarization: typically horizontal
- beamwidth: typically horizontal
- feed point impedance: varies with configuration, fed at apex
- requires large ground area but low supporting structures.
### 3.3.4 Working
- two long wire elements are arranged at an angle (apex angle)
- they are fed 180 degree out of phase
- radiation from the two wires combines constructively along the axis of V, creating a directional pattern
- for the terminated version, travelling waves propagate along each leg and are absorbed at the ends, producing a unidirectional end-fire pattern
- for the unterminated version, standing waves form, creating a bidirectional broadside pattern.
- The beam elevation and horizontal pattern are interdependent, determined by leg length, apex angle and height above ground.
- the tilt of the horizontally polarized beam is controlled by these geometric parameters.
### 3.3.5 Adv / Disadv
- adv
	- high gain
	- simple construction and easy installation
	- low cost
	- low profile
	- wideband operation
	- effective for HF
- disadv:
	- large area required
	- strong minor lobes
	- frequency limitations
	- standing waves
	- interdependent parameters
	- pattern sensitivity
### 3.3.6 Applications
- shortwave communication
- commercial radio
- military communication
- amateur radio
- receiving arrays
### 3.3.7 Figure
1. general introduction to V antenna:
   ![[Pasted image 20260126152937.png | 600]]
2. apex angle figure
   ![[Pasted image 20260126153314.png | 600]]
3. Terminated Vee Antenna:
   ![[Pasted image 20260126153620.png | 600]]
4. terminated vee antenna, that should have had resistance at its terminals
   ![[Pasted image 20260126155048.png | 600]]

---
## 3.4 Rhombic Antenna
### 3.4.1 Concept
- definition:
	- a travelling wave antenna formed by four long wires arranged in a diamond (rhombus) shape, typically horizontally mounted above ground
- can be visualized as 2 V-antennas connected at their ends, creating a more directive unidirectional pattern through constructive interference of travelling waves along all four legs
### 3.4.2 Features
- structure of 4 equal length wires on diamond shape in 2 Vee antenna configuration. opposite acute angles of the rhombus are equal
- utilizes travelling wave propagation along its legs
- typically terminated with a resistor to absorb remaining energy and prevent reflections
- feed point and terminating point must be properly aligned along the main axis
- primarily HF: 3 - 30 MHz, but can be designed for VHF: 30 - 300 MHz
### 3.4.3 Specification
- frequency range: 3-300 MHz (common: 3 - 30 MHz)
- leg length: typically 2 - 8 $\lambda$
- termination resistance of 600 - 800 $\Omega$
- apex angle 20 - 40 degree at feet end, with wider angle at termination end
- Gain of 10 to 20 dBi (significantly higher than Vee antenna)
- bandwidth is very wide
- polarization is horizontal linear
- radiation pattern is highly directional unidirectional lobe along main axis
- front to back ratio is 20-30 dB (which is very good)
- efficiency of 50 - 70 %
### 3.4.4 Working:
- antenna is fed at one acute angle via a balanced transmission line (twin-lead or through balun)
- RF energy travels as a wave along all four legs simultaneously
- radiation occurs progressively along each leg, with waves combining constructively in the forward direction.
- the travelling wave is absorbed by the termination resistor at the end, preventing reflections and standing wave
- this creates a unidirectional radiation pattern with maximum gain along the antenna's main axis
- the termination resistor dissipates 30-50% of input power as heat
- if left unterminated, the antenna becomes bidirectional but with standing wave and narrower bandwidth
### 3.4.5 Adv / Disadv
1. Adv
	- very high directivity
	- extremely wide bandwidth
	- simple construction
	- stable impedance
	- excellent FTB ratio
	- good for skywave propagation
	- low maintenance
	- high power handling
2. Disadv
	- large physical size
	- low efficiency
	- fixed direction
	- high termination power
	- complex design optimization
	- multiple supports requred
	- land intensive
### 3.4.6 Application
- long distance HF communication
- shortwave broadcasting
- military communication
- telemetry links
- receiving arrays
- VHF/UHF links
- backbone communication links
### 3.4.7 Figure:
1. General structure:
   ![[Pasted image 20260126160647.png | 600]]
2. Radiation pattern of rhombic antenna:
   ![[Pasted image 20260126162156.png | 600]]
---
# 4 Aperture Antenna
## 4.1 Description
### 4.1.1 Concept
- definition:
	- a type of antenna that consist of a flaring metal waveguide shaped like a horn to direct radio waves in a beam.
- serves as a transition between a waveguide and freespace
- basic principle:
	- the flared opening (i.e. aperture) acts as an impedance transformer, gradually matching the impedance of the waveguide to that of free space, while also directing and shaping the radiation pattern
### 4.1.2 Features
- flared structure
- broadband operation
	- wide bandwidth of 10-20% of center frequency
- low VSWR:
	- generally good impedance matching reduces reflections
- linear polarization:
	- genearlly linear, but circular can be acheived
- high power handling
- dimensional precision
- no resonant elements
- radiation pattern can be accurately calculated form physical dimensions
### 4.1.3 Specification
- frequency range: Microwave frequencies (300 MHz to 30 + GHz)
- gain of 10 - 25 dBi, depending on size and flare
- FBW of 10-20%
- 50$\Omega$ coaxial or waveguide feed is used as impedance
- linearly polarized usually
- beamwidth of 10 to 60 degree in principal planes, but depends on flare dimension
- VSWR typically 1.1 : 1 t o 1.5 : 1 over operational bandwidth
- efficiency: 50 - 80 %
- side lobes: 20 to 30 db below main lobe for standard horns
### 4.1.4 Working
- RF energy enters through the waveguide feed (rectangular, circular, or coaxial)
- as the wave propagates through the flaring section, the expanding cross section gradually transforms the waveguide mode to a free space plane wave.
- the flare controls the phase distribution acorss the aperture, determining the radiation pattern.
- the aperture size, shape determines the beamwidth, gain, side lobe
- the smooth transition minimizes reflections resulting in good impedance matching over a broad frequency range
### 4.1.5 Adv / Disadv
1. Adv
	- simple construction
	- wide bandwidth
	- good directivity
	- low VSWR
	- high power handling
	- predictable characteristics from dimensions
	- good isolation between transmitter and free space
2. Disadv
	- bulky size: physical size becomes large at lower microwave frequencies
	- moderate gain, is lower than parabolic for its size
	- manufacturing precision must be high
	- can be heavy compared to others
### 4.1.6 Application
- Microwave point to point links comunication
- radar systems' primary radiator
- satllite communication
- radio astronomy
- broadcasting microwave relay links
---
## 4.2 Horn Antenna
- useful and simple radiator excited by waveguide
- popular in microwave band (above 1 GHz)
	- large waveguides are required for low frequencies
- similar to opened out waveguide
- the function of horn is to produce a uniform phase font with a larger aperture than that of the waveguide and hence greater directvity
- very practical for space applications because they can be flush-mounted on the surface of spacecraft/aircraft
- radiation pattern of horn antenna depends on the dimensions of horn at the opening and the length of horn
- uses:
	- generally used at microwave frequencies for moderate power gains
	- used as a feed element for reflector (dishes) & lens antennas.
	- used in satellite tracking and in short range radar systems.
- two basic types:
### 4.2.1 Rectangular Horn
- a horn obtained by flaring of rectangular waveguide
- can be further subclassified as sectoral and pyramidal horn
	1. Sectorial Horn
		- Rectangular Horn flaared in E-Plane is Sectorial E Horn
		- Rectangulaar Horn flared in H-Plane is Sectorial H Horn
	2. Pyramidal Horn
		- A horn with flaring in both E and H planes is Pyramidal
### 4.2.2 Conical Horn
- a horn obtaianed by flaring of circular waveguide is conical horn
### 4.2.3 Figure:
- Some types:
	- ![[Pasted image 20260310213605.png]]
- Radiation Pattern:
	- ![[Pasted image 20260310213736.png]]
### 4.2.4 Derivation for flare angle & length of horn
- consider a cross section of horn:
	- ![[Pasted image 20260310213950.png]]
	- L = horn length in meters
	- $\theta$ = flre angle in degree ($\theta_E$ & $\theta_H$)
	- a = aperture in meters (a$_E$ & a$_H$)
	- $\delta$ = path length difference in meters ($\delta_E$ & $\delta_H$)
- from figure's geometry:
	- 1: $$\cos\left(\dfrac\theta2\right) = \dfrac{L}{L+\delta}\ ;\ \sin\left(\dfrac\theta2\right) = \dfrac{a}{2(L+\delta)}\ ;\ \tan\left(\dfrac\theta2\right)=\dfrac{a}{2L}$$
	- 2: $$\theta=\ 2\tan^{-1}\left(\dfrac{a}{2L}\right)\ =\ 2\cos^{-1}\left(\dfrac{L}{L+\delta}\right)$$
	- 3: also using Pythagoras theorem $$L^{2}+ \left( \dfrac{a}{2} \right)^{2} = (L+\delta)^2$$
	- 4: $$L^{2}+ \left( \dfrac{a}{2} \right)^{2} = L^{2} + 2L\delta +\delta^2$$
	- 5: since $\delta$ << L, we can neglect $\delta^2$
	- 6: $$L = \dfrac{a^2}{8\delta}$$
	- 7: conclusion: $$L\ =\ \dfrac{a_E^2}{8\delta_E}\ =\ \dfrac{a_E^2}{8\delta_H}$$
- for a constant length L, the directivity of horn increases aas the 'a' and '$\theta$' are increased
- however, if the aperture and flare angle becomes so large that '$\delta$' is equivalent to 180$^0$, the phase reversal at the edges of aperture reduces the directivity.
- therefore optimum horn dimensions are: $$\delta_{0}\ =\ \dfrac{L}{\cos\left(\dfrac\theta2\right)}\ -\ L$$ $$L\ =\ \dfrac{\delta_{0} \cdot \cos\left(\dfrac\theta2\right)}{1 - \cos\left(\dfrac\theta2\right)}$$
- Directivity:
	- A$_e$ = effective aperture,
	- A$_p$ = physical aperture
	- $\epsilon_{ap}$ = aperture efficiency
	- D = $$\dfrac{4\pi}{\lambda^{2}A_{e}}\ =\ \dfrac{4\pi}{\lambda^{2}}\epsilon_{ap}A_p$$
	- Typical value of $\epsilon_{ap}$ = 0.6
	- D $$\approx \dfrac{7.5}{\lambda^{2}}A_{p}= \dfrac{7.5}{\lambda^2}a_Ea_H$$
		- for conical, A$_p$ = $\pi\cdot r^2$
- and power gain, G$_p$ $$=\ \dfrac{4.5}{\lambda^{2}}A_{p}\ =\ \dfrac{4.5}{\lambda^2}a_Ea_H$$
- Half power bandwidth
	- E-plane horn: $\dfrac{56^{0}\times \lambda}{a_E}$
	- H-plane horn: $\dfrac{67^{0}\times \lambda}{a_H}$
	- Circular horn: $\dfrac{58^{0}\times \lambda}{D}$
---
## 4.3 Reflector Antenna
- widely used to modify the radiation pattern of a radiating element
- reflector antenna -- secondary antenna
- can be of any geometrical configuration but the most common are 
	- plane reflector, corner reflector and curved reflector (parabolic)
- most important in microwave radiation application
- figure:
	- ![[Pasted image 20260310204522.png]]
### 4.3.1 Flat Sheet Reflectors
- using image theory, below structure (large flat sheet reflector behind a dipole) is equivalent to two element array with an out of phase excitation and spacing equal to twice the distance 'S'
- finite reflector produces some back radiation due to the diffraction at the edge of the reflector.
- figure:
	- ![[Pasted image 20260310210712.png]]
- field pattern will depend on the value of 'S'.
- the distance S = $\lambda/8$ gives gain of 2.2 (6.7 dB)
- for example, figure:
	- ![[Pasted image 20260310210819.png]]
- advantages
	- large flat sheets are easy to analyze using the method of images
	- increased directivity and insensitive to small frequency changes
- disadvantages
	- installation of large reflector is difficult due to weight and wind position
		- can be solved using grid wires with loss in efficiency
	- small flat sheets can be used but they are sensitive to small frequency changes.
### 4.3.2 Parabolic Reflector
- If the primary antenna (feed) is non directional then the paraboloid will produce a beam of radiation whose Beamwidth is given by $$\Phi \cong\ \dfrac{70\lambda}{D}$$
- the maximum power gain of an antenna using an uniformly illuminated paraboloid reflector is given by $$A_{p} = 6\ \left(\dfrac{D}{\lambda}\right)^2 $$
- If the intensity of illumination falls off at the edges then the power gain will be $$A_{p} \approx\ 4.2\ \left( \dfrac{D}{\lambda} \right)^2$$
### 4.3.3 Feed mechanisms for a paraboloid
#### 4.3.3.1 Dipole Feed
- simplest feed
- suffers from spillover loss
- side lobes results due to edge diffraction
- can't use large sheets - obstruction will be more
- improved but causes considerable aperature blocking
- figure:
	- ![[Pasted image 20260310212201.png]]
#### 4.3.3.2 Feed mechanism for a paraboloid
- horn antenna pointing at the main reflector
- the small obstruction is negligible
- ![[Pasted image 20260310212448.png | 150]] ![[Pasted image 20260310212459.png | 270]] ![[Pasted image 20260310212508.png|245]]
#### 4.3.3.3 Cassegrain feed
- an important feeding method based on astronomical reflecting telescopes
- used when it is desired to place the primary antenna in a convenient position to shorten the length of transmission line or wave guide.
- Figure:
	- ![[Pasted image 20260310212822.png | 400]]
- Construction
	- dual reflector system
	- horn antenna (primary antenna): used for feeding
	- parabolic antenna (primary reflector): a large paraboloidal shape dish made up of metal or screen mesh
	- hyperbolic antenna (sub/secondary reflector): hyperboloid placed at the focus of main paraboloid reflector.
- Working:
	- rays emitted from horn are first reflected by hyperboloid reflector and then undergo a second reflection by paraboloid reflector.
- Advantage:
	- it reduces the length of feeding waveguide, as a result noise & losses are minimized.
	- which in turn achieves more gain
- Disadvantage
	- it reduces the length of feeding waveguide, as a result noise & losses are minimized..
	- which in turn achieves more gain
- Uses:
	- radar
---
# 5 Array Antenna
## 5.1 Yagi Uda
- directional antena
- wide range of applications from short, medium to long range due to its directional characteristics
- comprises of two types of elements
	- active element
		- aka driven element
		- where power supply is connected
	- parasitic element
		- reflector element 
		- and director element
### 5.1.1 Components
1. Driven Element:
	- It is an active element that is connected to the supply
	- it can be dipole or folded dipole in most yagi uda antenna
2. Reflector Element
	- It is passive element that is not connected to the supply
	- used to reflect the back-lobe of the driven element
3. Director Element
	- passive element that is not connected to the supply
	- it is used to direct the major lobe of the driven element.
#### 5.1.1.1 Components Figure:
![[Pasted image 20260126174042.png | 600]]
### 5.1.2 Adv/Disadv
1. Advantage
	- High gain
	- high front to back lobe ratio
	- cost effective
	- light weight
2. Disadvantage
- for high gain, it becomes very long
### 5.1.3 Design
##### 5.1.3.1.1 Question:
1. five element
2. 100 MHz\
3. effective length = 0.48 $\lambda$
4. spacing = 0.15 $\lambda$
##### 5.1.3.1.2 Solution:
1. f = 100 MHz
2. $\lambda_c$ = $$\dfrac{c}{f}\ =\ =\ \dfrac{3\cdot10^8}{100*10^6} = 3m$$
3. for 5 element yagi uda antenna we have:
	- reflector
	- driver
	- director 1
	- director 2
	- director 3
4. length of driver = 0.48 $\lambda$ = 0.48 * 3 = 1.44 m
5. length of reflector = 1.44 + 0.5 * 1.44 = 1.512 m
6. length of directors
	1. director 1 = 1.44 - 0.05 * 1.44 = 1.368 m
	2. director 2 = 1.44 - 0.1 * 1.44 = 1.296 m
	3. director 3 = 1.44 - 0.15 * 1.44 = 1.224 m
7. spacing between elements
	1. between reflector and driver: S$_{R-D}$ = 0.15 $\lambda$ = 0.45 m
	2. between driver and director1: S$_{D-D1}$ = 0.25 $\lambda$ = 0.25 * 3 = 0.75 
	3. between director 1 and director 2: S$_{D1-D2}$ = 0.15 $\lambda$ = 0.45m 
	4. between director 2 and director 3: S$_{D2-D3}$ = 0.15 $\lambda$ = 0.45m
8. total length = 0.45 + 0.75 + 0.45 = 2.1 m
9. space at end points = 1.224 / 2 = 0.612 m
	- i.e. 0.306 m at reflector side & 0.306 m at director 1 side.
	- total boom length = 0.306 + 2.1 + 0.306 = 2.712 m
10. Final figure:
    ![[Pasted image 20260126181121.png | 600]]
---
---
## 5.2 Log Periodic Antenna
### 5.2.1 Context
- A broadband antenna that is designed to provide such electrical characteristics that may vary repeatedly in periodic manner with logarithmic of the frequency of operation is known as log-periodic antenna
- this mean, impedance and radiation pattern are the factors that are logarithmic function of the frequency.
- frequency range of 30 MHz to 3 GHz
### 5.2.2 Construction
- constructed using several half wave dipole elements of different lengths and spacing,
	- arranged along a common axis
- the length and spacing of dipoles increase gradually from the narrow end
	- to wider end of the array
- all elements are mounted on a support boom, and are fed by a balanced transmission line
	- which is transposed between adjacent dipoles.
- the feed is usually connected at the apex (narrow end).
- this construction allows the antenna to operate over a wide range of frequencies
### 5.2.3 Figure
![[Pasted image 20260126181855.png | 600]]
### 5.2.4 Characteristics
- excitation to the antenna is provided at the shorter length side in case of single active region,
	- while at the center in case of two inactive regions
- to have unidirectional radiation pattern,
	- the structure must radiate towards the shorter element (i.e. left direction)
	- and negligible towards right
- the transmission line inactive region must possess desired characteristics impedance with very small or negligible radiation
- in the active region to have strong radiation, magnitude and phase of the currents must be proper
### 5.2.5 Advantages
- it offers a compact structure
- it provides adjustable gain according to the requirement.
- these offer negligible loss of power when terminated.
### 5.2.6 Disadvantages
- the mounting platform must be sufficient strength to elements
- it is quite expensive than other antennas.
---
# 6 Broadband & Special Elements
## 6.1 Helical Antenna
### 6.1.1 Concept
- Definition:
	- A helical antenna consists of a conducting wire wound in the form of a helix (screw thread) above a ground plane.
	- It is fed by a coaxial cable:
		- the center conductor connects to the helix and
		- outer conductor connects to the ground plane.
- Nature:
	- A specialized antenna that provides circular polarization and directional gain in its most common mode.
	- Extremely popular in VHF and UHF bands for satellite and space communication
	- Can operate in two distinct modes depending on the helix dimensions relative to wavelength.
### 6.1.2 Features
- Helical geometry: wire wound around an imaginary cylinder.
- Ground plane required: typically a circular a square metallic plate
- Two operating modes:
	- Normal Mode (Broadside) - helix electrically small, omnidirectional pattern.
	- Axial Mode (End-fire) - helix dimensions comparable to wavelength, highly directional with circular polarization
- Circular Polarization Capability : a major advantage over dipoles and monopoles
- Broadband: (in axial mode) can achieve 2:1 bandwidth ratio
- Moderate to high gain in axial mode (upto 15-20 dBi) with many turns
- Simple feed - directly connected to 50$\Omega$ or 75$\Omega$ coaxial cable.
- Self-matching in axial mode - input impedance around 100-200$\Omega$, easily matched.
- can be enclosed in a radome (radar dome) for outdoor/space use
### 6.1.3 Antenna Specifications
#### 6.1.3.1 Geometric Parameters
| Parameter             | Symbol            | Formula/Description                                    |
| --------------------- | ----------------- | ------------------------------------------------------ |
| Diameter of helix     | D                 | Distance between opposite points of one turn           |
| Circumference         | C                 | C = $\large \pi D$                                     |
| turn spacing          | S                 | Distance between adjacent turns (center to center)     |
| Pitch angle           | $\large \alpha$   | $\alpha = \tan^{-1}\left(\dfrac{S}{\pi\cdot D}\right)$ |
| Length of one turn    | $\large L_{turn}$ | $\large \sqrt{S^2 + (\pi \cdot D)^2}$                  |
| Number of turns       | N                 | Typically 5 to 20 for axial mode                       |
| Total helix length    | A                 | $A = N \times S$                                       |
| Ground plane diameter | $\large D_g$      | $\large \ge 3\lambda/4$ recommended                    |
| Ground-helix distance | L                 | distance between helix and ground plane                |
#### 6.1.3.2 Electrical Specification
| Parameter               | Normal Mode                              | Axial Mode                                               |
| ----------------------- | ---------------------------------------- | -------------------------------------------------------- |
| Condition               | $\large D \ll \lambda$, $NL \ll \lambda$ | $\large C \approx \lambda$, $\large S \approx \lambda/4$ |
| C                       | Very small ($\large \ll \lambda$)        | $\large 0.75\lambda$ to $\large 1.33\lambda$             |
| S                       | Very small                               | $\large 0.2\lambda$ to $\large 0.35\lambda$              |
| $\large \alpha$         | very small ($\large < 5$$\D$)            | $\large 0.2\lambda$ to $\large 0.35\lambda$              |
| Gain                    | ~1.5 to 3 dBi                            | ~ 10 to 20 dBi                                           |
| Polarization            | Linear (same as small loop/dipole)       | Circular (RHCP or LHCP)                                  |
| Radiation pattern       | Omnidirectional (broadside)              | Unidirectional (end fire)                                |
| Input impedance         | high capacitive                          | ~ 100 to 200$\O$                                         |
| Beamwidth               | 90$\D$ to 180$\D$                        | 30$\D$ to 80$\D$                                         |
| Axial Ratio             | N/A                                      | < 3 dB                                                   |
| Typical frequency range | 100 MHz - 1 GHz                          | 200 MHz - 5 GHz                                          |
### 6.1.4 Working Principle
#### 6.1.4.1 Common to Both Modes
- the helix supports a travelling wave of current along its length
- the coaxial feed launches energy at the base
- the ground plane provides a reflection boundary
- the helix geometry determines the phase velocity and radiation characteristics
#### 6.1.4.2 Normal Mode Working
**Operating Conditions**
- $\large D \ll \lambda$ (electrically small, less than 1:10 ratio)
- NL $\large \ll \lambda$ (very short compared to wavelength)
**Working**:
1. The helix behaves as a combination of small loop antenna and a short dipole, both electrically small.
2. The loop element produces magnetic field radiation; the dipole element produces electric field radiation.
3. The turns are so close together that the helix acts like a continuous structure, not a resonant element.
4. By adjusting $\large \alpha$, the loop and dipole contributions can be balanced to achieve circular polarization
	- rare in normal mode, more common in axial mode
5. Typically, normal mode helices produce linear polarization similar to a short monopole
6. The radiation pattern is omnidirectional in the horizontal plane and donut shape in vertical plane.
7. phase velocity on normal mode helix si slow
**Limitations**
- very low radiation resistance, fraction of an ohm
- poor efficiency (< 10 - 30%)
- extremely narrow bandwidth
- used only when small size is critical
#### 6.1.4.3 Axial Mode Working
**Operating Conditions**
- C $\large \approx \lambda$ (typically 0.75 ~ 1.33 $\lambda$)
- S $\large \approx \lambda/4$ (typically 0.2 to 0.35$\lambda$)
- N $\large \ge 5$ for good directivity
**Working**
1. A travelling wave propagates along helix wire at a velocity slightly less than the speed of light.
2. The circumference being approximately one wavelength creates in-phase currents on adjacent turns
3. This in-phase condition causes constructive interference along the helix axis.
4. the wave radiated from each turn adds in phase in the forward direction (end-fire)
5. The ground plane suppress backward radiation
6. the radiation is circularly polarized because of horizontal and vertical components of the travelling wave are 90$\D$ out of phase
### 6.1.5 Adv/Disadv
- ADV: AXIAL MODE
	- Circular polarization is immune to farady rotation in ionosphere; works with any orientation of receiving antenna
	- High gain in compact volume, 10-20 dBi from only few wavelengths long
	- Broadband can operate over 2:1 frequency range without retuning
	- simple feed
	- self matching (impedance is primarily resistive and stable)
	- low side lobes
	- mechanically simple
- ADV: NORMAL MODE
	- very small size, can be made much shorter than $\large \lambda/4$ monopole
	- omnidirectional pattern - suitable for portable devices
	- simple construction  - just wound wire
- DISADV: AXIAL
	- Requires ground plane, that adds to bulk
	- physically long for high gain
	- limited gain per turn: after 20 turns, additional turns give minimal improvements
	- circularly polarization purity degrades at band edges
	- higher cost than simple monopole/dipole
	- not suitable for very low frequencies due to large size
- DISADV: NORMAL
	- Very low radiation resistance (often less than 1$\O$) -> poor efficiency
	- Narrow bandwidth
	- low gain similar to short dipole
	- difficult to match capacitive reactance
	- rarely used in practice, short monopole better in use.
### 6.1.6 Application
- Satellite communication
- Space temetry
- Radio astronomy
- GPS antennas
- Military communication
- Weather radar
- WiFi and wireless links
### 6.1.7 Figure
- ![[Pasted image 20260310221324.png]]
---
## 6.2 Microstrip Antenna
### 6.2.1 Concept
- Definition:
	- A low-profile antenna consisting of a thing conducting patch mounted on a dielectric substrate over ground plane.
	- Also called patch antenna
- Nature:
	- Planar, lightweight, and easily fabricated using PCB technology.
	- Ideal for integration with microwave circuits.
### 6.2.2 Features
- Flat, compact structure: thickness much smaller than wavelength
- printed circuit construction for low cost, mass production
- conformal: can be mounted on curved surfaces
- typically linearly polarized
- narrow bandwidth
- low gain (5 - 9 dBi)
- easy to form arrays for higher gain
### 6.2.3 Specifications
- Frequency range: 1 GHz to 100 GHz
- Patch shape: rectangular (most common), circular, triangular
- Dielectric constant: 2.2 to 12 (lower $\large \epsilon_r$ -> higher BW)
- substrate thickness : 0.01 to 0.05 $\L$
- bandwidth: 1-5% 
- gain: 5 - 9 dBi
- polarization: linear (or circular with dual feed)
- radiation pattern: broadside
- input impedance: typically 50/100$\O$
- efficiency: 70-90%
### 6.2.4 Working
- the patch acts as a resonant cavity open at the edges
- RF energy is fed via coaxial probe, microstrip line, or aperture coupling
- At resonance (path length $\approx$ $\L$/2) fringing fields at the edge radiate
- the two radiating edges are out of phase, producing broadside radiation
- ground plane prevents backward radiation
### 6.2.5 Adv/Disadv
- ADV:
	- very low profile and lightweight
	- low manufacturing cost (PCB tech)
	- easy to integrate with active circuits
	- conformal to surfaces
	- can be made in arrays
- DISADV:
	- narrow bandwidth
	- low gain per element
	- low power handling
	- surface wave losses in substrate
	- requires precision fabrication at high frequencies
### 6.2.6 Applications
- Mobile phones and tablets (internal antennas)
- GPS receivers
- satellite communication (conformal arrays)
- radar systems
- automotive radar
---
## 6.3 Spiral Antenna
### 6.3.1 Concept
- Definition:
	- a frequency independent antenna formed by two or more spiral-shaped metallic arms on a dielectric substrate
- Nature:
	- extremely broadband (several octaves) with constant impedance and pattern
	- provides circular polarization (usually)
### 6.3.2 Features
- Self complementary structure (metal and air gaps are equal width)
- Frequency-independent - electrical properties repeat logarithmically
- circular polarization
- bidirectional radiation often backed with a cavity for unidirectional
- low profile (flat printed construction)
### 6.3.3 Working
- travelling wave propagates outward along the spiral arms
- the active region (where radiation occurs) is where the circumference $\approx$ $\L$
- as frequency changes, the active region moves inward/outward along the spiral
- this movement maintains constant radiation characteristics over a wide bandwidth
- the two orthogonal are fed 180$\D$ out of phase
- radiation is circularly polarized of the geometry's inherent rotation.
### 6.3.4 Adv/Disadv
- Adv
	- extremely wide bandwidth
	- stable radiation pattern and impedance
	- circular polarization
	- low profile
	- simple feed (balun required)
- Disadv:
	- dispersion (different frequencies radiation radiate from different regions)
	- lower gain than resonant antennas
	- bidirectional pattern (requires cavity for unidirectional, adds depth)
	- larger size at lower frequencies
	- efficiency loss in cavity backing
### 6.3.5 Application
- broadband surveillance
- EMC/EMI testing
- direction finding
- satellite communication
- ground penetrating radar
---
## 6.4 Loop Antenna
### 6.4.1 Concept
- Definition:
	- closed loop conductor (circular, square, triangular) used for receiving or transmitting
- Nature:
	- can be electrically small (magnetic dipole) or large (resonant)
	- often used as a receiving antenna due to low noise.
### 6.4.2 Feature
- Two categories
	- small loop (circumference < $\L$/4), magnetic field antenna, low radiation resistance
	- large loop (circumference $\approx \L$), resonant, higher efficiency
- typically vertically polarized for omnidirectional pattern
- low noise reception
- can be shielded for near-field cancellation
### 6.4.3 Working
- Small Loop
	1. the loop behaves as a magnetic dipole (not electric)
	2. current is uniform around the loop (no standing waves)
	3. maximum radiation is in the plane of the loop; null perpendicular to loop
	4. the loop responds to the H-field, rejecting nearby E-field noise.
- Large Loop
	1. for circumference $\approx \L$, a standing wave exists
	2. Can be fed at various points to achieve different patterns
	3. A square loop (quad) is popular for amateur radio (2-3 dBi)
### 6.4.4 Adv/Disadv
- Adv:
	- very low noise (small loop)
	- compact at low frequencies (small loop)
	- simple construction
	- can be directional (figure-8 pattern)
	- shielded loops reject local interference
- Disadv:
	- very low efficiency (small loop)
	- narrow bandwidth (small loop)
	- requires high-Q tuning capacitor for small loop
	- Weak signal output (small loop) requires preamplifier
### 6.4.5 Application
- AM broadcast reception
- direction finding
- near field RFID
- TV reception
- wireless power transfer (resonant loops)
---
# 7 Other
## 7.1 Large Plane Sheet
### 7.1.1 Concept
- Definition:
	- A large flat conducting sheet placed behind a radiating element (e.g., dipole) to reflect forward radiation and increase directivty
- Nature:
	- passive reflector, not fed directly
	- uses image theory to create an equivalent array
### 7.1.2 Features
- Size $\gg \L$
- increases gain by eliminating backward radiation
- simple construction
- can be solid or wire mesh
- frequency sensitive
### 7.1.3 Working
1. Uses image theory, the sheet acts as a mirror.
2. The antenna and its image form a two-element array.
3. Spacing (S) determines phase difference between real and image.
4. At S = λ/4, image currents are in phase → maximum forward gain.
5. At S = λ/2, pattern develops multiple lobes.
6. Finite sheet produces edge diffraction (some back radiation).
### 7.1.4 Adv / Disadv
- **Advantages:**
	- Simple and cheap
	- Significant gain improvement
	- Excellent front-to-back ratio
	- Easy to analyze (image method)
- **Disadvantages:**
	- Large and heavy (especially at lower frequencies)
	- Wind loading problems
	- Solid sheets are heavy; mesh saves weight
	- Fixed direction (cannot steer)
	- Spacing critical for optimal performance
### 7.1.5 Applications
- **Radio telescopes** (large reflecting ground screens)
- **HF/VHF base station antennas** (reflector behind dipole)
- **Microwave antennas** (corner and parabolic reflectors use same principle)
- **EMC anechoic chambers** (floor reflectors)
- **Point-to-point links** (simple reflector behind yagi)
---
## 7.2 Small Plane Sheet
### 7.2.1 Concept
- Definition:
	- A flat conducting sheet whose size is comparable to or smaller than the wavelength, placed behind a radiating element
- Nature:
	- acts as director or reflector, not a perfect mirror
### 7.2.2 Features
- Size $\approx \L$ or less
- edge diffraction is significant
- beam shaping rather than true reflection
- sensitive to frequency
- can be used as a parasitic element like in yagi, but flat)
### 7.2.3 Working
1. Image theory is not accurate because sheet is finite
2. the small sheet scatters and diffracts the incident wave
3. at certain spacings, it can act as a reflector (like yagi reflector)
- at other spacings, it acts as director
- field pattern depend critically on S/$\L$ and sheet size
- edge currents create side lobes and back radiation
### 7.2.4 Adv/Disadv
- Adv:
	- Compact and lightweight
	- can be used where large sheet is impractical
	- simple to add to existing antenna
- Disadv:
	- very narrow bandwidth
	- unpredictable pattern without simulation
	- lower gain improvement than large sheet
	- high sensitivity to exact dimensions
	- edge diffraction causes pattern distortion
### 7.2.5 Application
- Portable VHF/UHF antenna
- Yagi-Uda antenna
- test antenna
- handheld directional antenna
---