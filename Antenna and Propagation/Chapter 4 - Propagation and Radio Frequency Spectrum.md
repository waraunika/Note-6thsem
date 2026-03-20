x# 1 Ground or Surface Wave
## 1.1 Concept
- also called surface wave propagation
- refers to radio waves that travel along the earth's surface, following its curvature.
- these waves glide over the ground and enable communication beyond the optical horizon through diffraction
## 1.2 Technical Details
### 1.2.1 Frequency Range and Bands
| Parameter             | Value                                                            |
| --------------------- | ---------------------------------------------------------------- |
| Range                 | 10 kHz to 2 MHz                                                  |
| Bands                 | VLF, LF, and MF                                                  |
| Upper Practical limit | ~ 3MHz (above this, attenuation makes ground wave impracticable) |
### 1.2.2 Polarization
| Parameter | Value                                         |
| --------- | --------------------------------------------- |
| Linear    | primarily Vertical Polarization               |
| Why?      | vertical polarization minimizes ground losses |
### 1.2.3 Key Parameters
| Parameter          | Typical Value             |
| ------------------ | ------------------------- |
| Transmission Power | Few kW to several MW      |
| Coverage Distance  | Upto ~ 1000 km            |
| Transmission Mode  | AM (Amplitude Modulation) |
| Antenna Pattern    | Omnidirectional           |
### 1.2.4 Frequency vs Coverage
| Band            | Typical Coverage              |
| --------------- | ----------------------------- |
| LW              | ~ 1000 km                     |
| MF              | ~ 100 miles (160 km)          |
| 3 MHz and above | Impracticable for ground wave |
| 10 MHz          | 1-2 miles only                |
### 1.2.5 Radio Horizon
- approximately 4/3 times the optical horizon
- beyond the horizon, direct and reflected waves are blocked by earth's curvature
- propagation continues via diffracted surface wave.
### 1.2.6 Surface Conductivity (Best to worst)
- large body fresh water - very good
- ocean or sea water - good
- flat or hilly loamy soil - fair
- rocky terrain - poor
- desert - poor
- jungle - very poor
- dry sandy terrain, city centers - worst
### 1.2.7 Propagation Method
- primary mechanism: diffraction
- wave produces a mirrored copy beneath the Earth's surface during propagation
### 1.2.8 Attenuation Factors
- increases with frequency
	- Example 3 MHZ signal suffers 20 - 60 dB attenuation
- Dependent on
	- Earth's imperfection
	- Absorbed by ground
	- Reflection from surface
	- wave tilt creating horizontal component (reduces field strength)
## 1.3 Other Details
### 1.3.1 Wavelength Distribution
| Wave Type    | Wavelength Range |
| ------------ | ---------------- |
| Radio waves  | > 0.1 m          |
| Microwaves   | 0.1 - 1 mm       |
| Infrared     | 1 - 700 nm       |
| Visible rays | 700 - 400 nm     |
| UV rays      | 400 - 1 nm       |
| X-rays       | 1 nm - 1 pm      |
| Gamma rays   | < 1 pm           |
### 1.3.2 Factors Affecting Reception
- Ionospheric effects: D/E layer absorption
- Temporal variations
	- Diurnal (Day/nigh)
	- Seasonal changes
	- 11 year sunspot cycle
- Propagation effects
	- fading
	- multipath interference
	- atmospheric absorption
	- refraction
	- thermal noise
### 1.3.3 Special Applications
- Marine communications: 10 - 110 kHz
- Time & frequency management:
	- 16 kHz (UK)
	- 17.8 kHz (US)
### 1.3.4 Medium Wave Broadcasting
- frequency range: 535 kHz - 1625 kHz
- skip distance from sky wave can be minimized using ground wave
## 1.4 Adv/Disadv
### 1.4.1 Adv
- **Beyond horizon coverage**: Enables communication beyond the optical horizon
- **Weather independence**: Relatively unaffected by atmospheric conditions (unlike sky waves)
- **Global potential**: With sufficient power, can communicate between any two points
- **Reliable**: Provides consistent regional coverage
- **Minimizes skip distance**: Can fill in areas where sky wave coverage is problematic
### 1.4.2 Disadv
- **High power requirements**: Needs relatively high transmission power
-  **Frequency limited**: Only practical at VLF, LF, and MF bands
- **Large antennas**: Lower frequencies require physically large antenna structures
- **Surface dependent**: Losses vary considerably with ground material
- **Frequency-dependent attenuation**: Attenuation increases with frequency
- **Limited range at higher frequencies**: Coverage reduces dramatically above 2 MHz
## 1.5 Applications
### 1.5.1 Primary
1. **Broadcasting**
    - AM radio broadcast stations
    - Regional coverage on long and medium wave bands
2. **Maritime Communications**
    - Ship-to-shore communications (10-110 kHz)
    - Navigation systems
3. **Time and Frequency Standards**
    - National time signal services
    - Frequency reference distribution
4. **Local Communications**
    - Regional radio coverage
    - Emergency broadcast systems
### 1.5.2 Typical Use Case
- **LF band**: Long-range navigation, time signals
- **MF band**: AM broadcasting, maritime communications
- **VLF band**: Submarine communications, global navigation
### 1.5.3 Coverage Optimization
- Better performance over wet/humid terrain than dry
- Coastal and maritime paths provide superior propagation
- Agricultural and marshy land preferred over urban/dry areas
---
# 2 Space Wave
## 2.1 Concept
- aka Direct Wave Propagation
- refers to radio waves travelling directly 
  - from the transmitting antenna to the receiving antenna
  - without relying on
    - reflection from the ionosphere or
    - diffraction along the earth's surface.
- this is primary mode for high-frequency communication and forms the basis for LOS and satellite communication.
## 2.2 Technical Details
### 2.2.1 Frequency Range and Bands
- Frequency range: Above 30 MHz
- Frequency bands: VHF, UHF and SHF
- Typical applications: FM radio, TV broadcasting, radar, satellite communications, microwave links

### 2.2.2 Polarization
- linear polarization (Horizontal or vertical)
- Circular Polarization
- Polarization selection depends on application and propagation environment.

### 2.2.3 Key Parameters
| Parameter          | Typical Value                                        |
| ------------------ | ---------------------------------------------------- |
| Transmission Power | 1 kW (Typically)                                     |
| Coverage Distance  | 30 - 70 km (terristrial), upto 36,000 km (satellite) |
| Transmission Modes | AM, FM, PM                                           |
| Antenna Pattern    | Unidirectional                                       |
| Bandwidth          | Wide, Broad and Ultrawide                            |
### 2.2.4 Distance Calculation
- Diagram for Derivation
  - ![[Pasted image 20260318134126.png]]
- Distance between h$_t$ (height of transmitting antenna) and h$_r$ (height of receiving antenna)
  - given by d = X$_1$ + x$_2$
- where
  - X$_1$ = $\large \sqrt{(R + h_t)^2 - R^2}$
  - X$_2$ = $\large \sqrt{(R+h_r)^2 - R^2}$
- then, for d we have:
$$\large
\begin{align}
d &= \sqrt{(R + h_t)^2 - R^2} + \sqrt{(R + h_r)^2 - R^2}\\
  &= \sqrt{2\cdot R\cdot h_t + h_t^2} + \sqrt{2\cdot R\cdot h_r + h_r^2}\\
  \text{Here, R = 6378 km >> hr or ht}\\
  &= \sqrt{2R}\left( \sqrt{h_t} + \sqrt{h_r} \right)\\
  &= \sqrt{2\cdot 6378\cdot 10^3} (\sqrt{h_t} + \sqrt{h_r})\\
  &= 3571.55 (\sqrt{h_t} + \sqrt{h_r})\\
  &= 3.571 (\sqrt{h_t} + \sqrt{h_r})\ \text{km}
\end{align}
$$
- here, h$_t$ and h$_r$ are in meter
### 2.2.5 Skip Distance
- minimum distance from transmitter where a sky wave returns to earth
- for space wave, skip distance is not directly applicable as its a LSO mode
- the formula above gives the maximum LOS distance before earth's curvature blocks the signal.
### 2.2.6 Satellite Communication Distance
- Geostationary Satellites: ~35,786 (~36,000) km above Earth
- Provides hemispheric or global coverage depending on antenna design
## 2.3 Other Details
### 2.3.1 Propagation Characteristics
- Space wave consists of two components
  1. Direct Wave: Travels directly from transmitter to receiver
  2. Ground-reflected wave: Reflects off the earth surface before reaching receiver
- Field strength reduces as distance increases
- Limited by Earth's curvature (beyond horizon -> no signal)
### 2.3.2 Factors Affecting Reception
- Atmospheric conditions:
  - Temperature inversions
  - Humidity variations
  - Pressure changes
- Ionospheric conditions:
  - Refraction at lower frequencies
  - Scintillation effects
- Propagation effects:
  - Fading (multipath interference)
  - Absorption by atmospheric gases
  - Rain attenuation (especially at higher frequencies)
  - Diffraction around obstacles
### 2.3.3 Microwave Links
- Typical link distances: up to 100 km
- beyond 100 km, becomes very uneconomical due to:
  - need for tall towers
  - multiple repeaters required
  - increased power requirements
### 2.3.4 Comparison with other propagation modes
| Aspect      | Space Wave        | Ground Wave | Sky Wave                         |
| ----------- | ----------------- | ----------- | -------------------------------- |
| Frequency   | > 30 MHz          | < 2 MHz     | 2 - 30 MHz                       |
| Range       | LOS limited       | ~ 1000 km   | Global                           |
| Reliability | Weather dependent | Stable      | Variable (ionospheric dependent) |
## 2.4 Adv/Disadv
### 2.4.1 Adv
1. Wide bandwidth: 
	- Supports high-data-rate communications
2. Directional capability:
	- Unidirectional antennas reduce interference and increase efficiency
3. Multiple polarization options:
	- Flexibility in system design
4. Satellite communication:
	- Enables global coverage through space links
5. Frequency reuse:
	- Directional beams allow frequency reuse in different areas
6. Less susceptible to ionospheric disturbances:
	- Unlike sky wave at lower frequencies
7. Secure:
	- Directional beams reduce interception risk
### 2.4.2 Disadv
1. Line-of-sight limitation: Blocked by Earth's curvature and obstacles
2. Distance limited: Terrestrial range typically 30-70 km without repeaters
3. Obstacle sensitivity: Buildings, hills, and vegetation can block signals
4. Atmospheric effects: Rain, fog, and atmospheric gases cause attenuation
5. Tower height requirements: Tall structures needed for longer ranges
6. Economic constraints: Repeaters and tall towers increase infrastructure costs
## 2.5 Applications
### 2.5.1 Primary Applications
1. **Broadcasting**
    - FM radio (VHF band)
    - Television broadcasting (VHF/UHF)
    - Digital audio broadcasting
2. **Telecommunications**
    - Microwave point-to-point links
    - Cellular mobile networks
    - Wireless local loops
    - Wi-Fi and WLAN
3. **Satellite Communications**
    - Geostationary satellites (36,000 km)
    - Low Earth Orbit (LEO) satellites
    - Direct broadcast satellite TV
    - Satellite internet
    - Global navigation systems (GPS, GNSS)
4. **Radar Systems**
    - Air traffic control radar
    - Weather radar
    - Military surveillance
    - Automotive radar
5. **Mobile Communications**
    - Mobile phones (2G/3G/4G/5G)
    - Two-way radios
    - Emergency services communications
### 2.5.2 Typical Use Cases by Band
| Band | Frequency Range | Common Applications               |
| ---- | --------------- | --------------------------------- |
| VHF  | 30-300 MHz      | FM radio, TV, air traffic control |
| UHF  | 300 MHz-3 GHz   | Mobile phones, TV, GPS, Wi-Fi     |
| SHF  | 3-30 GHz        | Satellite, radar, microwave links |
| EHF  | 30-300 GHz      | 5G, advanced radar, research      |
### 2.5.3 Special Applications
- **Remote sensing**: Earth observation satellites
- **Radio astronomy**: Space wave propagation essential for receiving cosmic signals
- **Drone communications**: Control and data links
- **Smart grid**: Utility monitoring and control
- **IoT connectivity**: Long-range IoT systems (LoRa, Sigfox at sub-GHz frequencies)
---
# 3 Ground Reflected wave
- Reflected Signal as the transmission will be reflected by a number of objects
- including
	- earth's surface
	- any hills
	- or large building
- radio waves
	- ground or surface wave propagation
	- space wave propagation
		- LOS or direct wave
		- indirect or Ground reflected wave
	- sky wave propagation
-  Figure for Geometry of Ground Reflected Wave
	- ![[Pasted image 20260318125233.png]]
## 3.1.1 Duct Propagation
- Figure for working of propagation of waves in atmospheric duct
	- ![[Pasted image 20260319131551.png]]
- radio duct or just ducing
- tropospheric ducting
- atmospheric duct
- temperature inversion
- super refraction
- EM propagation within tropospheric layer
- duct propagation for VHF and UHF frequencies
- affect propagation in 50 MHz to 450 MHz
- propagation distance few hundred to 2000 km
- it usually happens 30 - 50 m above ground
- usually decrease in Temp of 6.5$^0$ C / km as h $\uparrow$
- but it is opposite under certain weather condition, i.e. temperature inversion
- as air density $\downarrow$, refractive index $\uparrow$
- with increasing height above the ground
- change in refractive index is linear and gradual
- guides teh radio waves along teh curvature of the earth
- thereby allowing the spreading of wave fronts in a horizontal manner only
- waves are bent by atmospheric refraction
- under certain atmospheric conditions produce a layer of air in the troposphere
- that will be at a higher temperature than the layers of air above and below it
- layer of warm air is trapped above cooled air
	- often over the surface of water
- such a layer will provide a duct creating a path through the warmer layer of air
- which has less signal loss than cooler layers above and below
- wave being reflected from the ionosphere or gliding over the surface of the earth
- due to undergoing successive refraction from the troposphere.
- atmospheric duct is the region present in lower atmosphere
- which is a result of temperature inversion
- the duct behaves as a waveguide in the atmosphere
- troposphere is extended upto 15 km from the surface of the earth
- duct propagation takes place nearly about 30-50m above the troposphere
- duct propagation occurs in troposphere and earth surface
- temperature of this region generally remains constant
- duct propagation allows the propagation of the signals beyond horizon
- this means that unlike surface wave propagation
- it permits the signal transmission without assuring the need for having a line of sight distance between the two antennas
- even duct propagation for VHF and UHF bands
# Ionospheric or Sky Wave
-  Overview of Frequency Spectrum

| Frequency (Hz) | Range          | Radio Presence |
| -------------- | -------------- | -------------- |
| 10             | VLF            |                |
| 100            | VLF            |                |
| 1k             | VLF            | RADIO          |
| 10k            | LF             | RADIO          |
| 100k           | MF             | RADIO          |
| 1M             | HF (3-30 M)    | RADIO          |
| 10M            | VHF (30-300 M) | RADIO          |
| 100M           | UHF (300 - 3G) | RADIO          |
| 1G             | SHF            | RADIO          |
| 10G            | EHF            | RADIO          |
| 100G           | INFRARED       |                |
| 1 T            | INFRARET       |                |
| 10 T           | VISIBLE        |                |
| 100T           | V/UV           |                |
| 10E15          | UV             |                |
| 10E16          | UV             |                |
| 10E17          | UV             |                |
| 10E18          | XRAY           |                |
| 10E19          | XRAY           |                |
| 10E20          | GAMMA          |                |
| 10E21          | GAMMA          |                |
| 10E22          | COSMIC         |                |
| 10E23          | COSMIC         |                |
| 10E24          | COSMIC         |                |
- Short wave is the sky wave
- short wave is used for long distance communication systems
- wave reflected back to the earth
- higher the frequency greater the energy
- large area coverage with skip distance
- mainly frequency range: 2 MHZ to 30 MHz
- mainly HF
- wave is affected by atmospheric changes
- medium play vital role in Ionosphere
- Transmission mode is AM
- Tx power: few KWs (typically 0.5 ~ 5 KW)
- Different layers in ionosphere take part
- refraction for different SW frequencies
- propagation method: refraction equivalent to reflection
- Rx power depends on
	- Tx power
	- frequency being used
	- ionospheric layer's nature
	- tropospheric changes less affected
- signal reception suffered by
	- D/E Layer's Absorption
	- Diurnally (Day time wise)
	- Seasonally
	- Annually (11 year's sunspot cycle)
- Different layers in ionospheric affect sky wave
- D-layer exists only during Day time
- E-layer more active at Night time
- During day time F-Layer is divided into Two parts
- E-layer using day time @ 2400 km cover
- higher frequency needs greater ionization density for radio waves reflection back
- more sunspots, the greater the ionizations
- thus 11 year's sunspot cycle is considered
- actually, signal is Refracted from ionized layers due to layer's refractive index change
- but it looks like the signal was reflected from ionosphere is a radio mirror, at virtual height of the ionosphere
- revolves around the refraction mechanism in the ionosphere
## Ionosphere
- region lying between 90 km to 450 km
- contains charge particles & takes ionization
- plays important role for space communications
- density of Air at the bottom 1.29 x 10 $^{-5}$ kg / m$^3$
- decreases gradually at the to about 1.29 x 10$^{-10}$ kg / m$^3$
- temperature rises form -90$^0$ C to 400$^0$ C to a height of 110 km
- this region is also called thermosphere
- structural details of the ionosphere
	- refraction mechanism depends on a number of factors including
		- frequency of operation
		- angle of takeoff and
		- ionospheric conditions
	- ionospheric is a region above the Mesosphere
	- it is composed of ionized layers
	- four layers: D, E, F$_1$, F$_2$
	- they are assumed to exist at different heights
	- distances of these layers, from the earth, are normally referred to the heights
	- at which the concentration of ionized electrons is Maximum
	- figure for variation of electron density N with height h
		- ![[Pasted image 20260319134359.png]]
- structure
	- F2 layer: 250 - 400 km
	- F1 layer: 150 - 250 km
	- E layer: 90 - 140 km
	- D layer 50/60 - 90 km
- D layer
	- height: 50 - 90 km above the earth's surface
	- photo ionization of O$_2$ Molucules mainly
	- present only in day time
	- largely absent in the night
	- ionization in the D layer is low due to less UV light penetrates to this level
	- ionic density of 400 /cc
	- electronic density (N) is max at noon
	- critical frequency (F$_{crt}$) is about 100 kHz at vertical incidence
	- maximum usable frequency (f$_{MUF}$) < 3 MHz
	- at 30 MHz, Waves cross the D layer attenuated.
	- its structural details are not yet known with certainty
	- for VLF and LF the space between the D layer
	- and the ground acts as a huge waveguide (Duct)
		- making communication possible
	- needs large antennas and high power transmitters
	- at LW and MW ranges, this layer is highly absorptive and limits daytime communication is not possible via D-layer
- E layer
	- exists between 90 - 140 km above the surface
	- maximum density at 110 km
	- ionization of all gases by X ray
	- electron density max is 4 x 1 0^ 5 / cc at 110 km
	- critical frequency (f$_{CRT}$) ~ 3 MHz - 5 MHz (in HF range)
	- effective for some band of SW at Day time
	- useful for Day time Comm
	- almost constant for diurnal or seasonal variations
	- governed by UV light from the sun
	- uniformly decays with time at Night
	- this layer permits medium distance communication in LF and HF bands
	- at night, the D layer slightly rises and the E layer slightly lowers to form one layer
	- which is again called E layer
- F layer
	- F1 laayer exists between 
		- 150 to 250 km above the earth's surface in summer
		- and 200 to 220 km in winter
	- this laayer is almost constant with little diurnal or seasonal variations
	- maximum electron density is at ~ 220 km 
	- this layer remains ionized all the time
	- ionization of all gases by UV, X rays & cosmic rays
	- electron density max < 4 x 10^5 / cc
	- f$_{CRT}$ ~ 5 MHz - 12 MHz (HF range)
	- day time breaks and merges F1 and F2 layers
	- very useful for HF reflection from it
	- F2 layer exists between 250 to 500 km
	- at night, the F1 layer slightly rises and the F2 layer slightly lowers to form one layer
	- which is again called teh F2 layer
	- it is sometimes also referred to F layer
	- it is more variable in nature
	- F2 is responsible for most of the HF long-distance communication
- Sporadic E basics
	- Sporadic E, Es, arises when intense clouds of ionization form in the region E of teh ionosphere
	- the level of ionization is upto about five times 
	- this level reached during the peak of a sunspot cycle
	- low tx power may be heard via sporadic E
	- sporadic E propagation by its name is Sporadic and unpredictable by nature
	- but it enables radio signals to travel over much greater distances
	- often at higher frequenceis that would noramlly be possible via the ionosphere
	- sporadic is a mode of radio propagation that occurs on occassions
	- sporadic E is not easy to predict
	- affects Radio communciation on Frequencies from a few MHz to lower band of VHF
	- on some occasions it can affect radio communication on around 150 MHz and sometimes even above this
	- sporadic E is not normally used for radio communication purposes
	- although radio amateurs use it
	- adds noises and may cover high distance
- UV rays and x-rays from sun produce ionization
- ionized layer is not uniform
- due to varying composition of atmosphere at different heights
- free electron density is found very high in layer between 100 km to 125 km
- this layer is called E-layer or Kennelly Heaviside Layer
- Beyond E-layer to 250 km the Electron Density decreases considerably
- again from 250 km to 350 km, there is high electron density
- the layer is known as appleton layer of F-layer
- useful for long-distance transmission of high frequency (SW)
- used for sky wave propagation significantly
- due to Total Internal Reflection of EM waves
- the Charge Density of Ionosphere increases with Height
	- which results in the decrease in its Refractive index
- higher to lower refractive index causes EM wave having internal refraction
- frequencies less than 2 MHz are absorbed
- frequencies greater than 30 MHz pass through it
- frequency range from 2 - 30 MHz can be propagated
- 3 - 30 MHz can be propagated
- maximum frequency at which total internal reflection from Ionospheric takes place is called Critical frequency (f$_{Crt}$) at 90$^0$.
- mathematically, f$_{Crt}$ = 9$\sqrt{N_{max}}$
## Sky Wave minimum skip distance
- minimum skip distance is influenced by a number of factors
	- frequency of operation
	- state of the ionosphere
	- angle or radiation
	- degree of ionization
	- seasons
- local time is very important for ionizations
- figure for types of sky wave function in propagation
	- ![[Pasted image 20260319133558.png]]
# Critical Frequency, MUF, Skip Distance
- F$i$
	- the highest frequency that returns from an ionospheric layer at a vertical incidence is called f$_{CRT}$ for that particular layer
	- for a regular layer, it is proportional to the square root of maximum electron density in the layer
- maximum usable frequency F$_{MUF}$
	- when the frequency exceed F$_{CRT}$, the return will depend upon the angle of incidence at a particulr  ionospheric layer
	- thus for a specified angle of incidence, there will be a maximum frequency which will be reflected back
	- the maximum possible value of frequency for which reflection takes place for a given distance of propagation is termed as MUF
	- beyond MUF, wave will not be returned
	- sky wave requires the angle of reflection to be 90$^0$.
	- if $\large \phi_i$ is the incident angle and $\large \phi_r$ is the reflection angle, the refractive index n can be written as
		- $$
			\large
			\begin{align}
			n = \dfrac{\sin(\phi_i)}{\sin(\phi_r)}=\sin(\phi_i)&=\sqrt{1-\dfrac{81N_{max}}{f^2_{MUF}}}\\
			\sin^2(\phi_i) &= 1-\dfrac{81N_{max}}{f^2_{MUF}}\\
			\text{here,}\ f_c^2 \text{= 81 N}_{max}\\
			\sin^2(\phi_i) &= 1-\dfrac{f_c^2}{f^2_{MUF}}\\
			\cos^2(\phi_i) &= \dfrac{f_c^2}{f^2_{MUF}}\\
			f^2_{MUF} = f_c^2\cdot \sec^2(\phi_i)
			f_{MUF} = f_c\cdot \sec(\phi_i)
			\end{align}
			$$
## Skip Distance
### When earth is flat
- figure for derivation
	- ![[Pasted image 20260319141440.png]]
- Parameters
	- AC length = distance between two stations on earth = D
	- O = mid point, so AO = OC = D/2
	- BO = normal at incidence = h
	- angle ABO = i, angle OBC = r
- we have:
$$
\large
\begin{align}
cos(\theta_i) = \dfrac{OB}{OA} = \dfrac{h}{\sqrt{h^2 + \dfrac{d^2}{4}}} = \dfrac{h}{h\sqrt{1+\dfrac{d^2}{4h^2}}} &= \dfrac{1}{\sqrt{1+\dfrac{d^2}{4h^2}}}\\
\text{from MUF and CF derivation we have,}\\
f_{MUF} = f_c \sec(\theta_i)\\
f_{MUF} = f_c \sqrt{1+\left( \dfrac{d}{2h} \right)^2}\\
\left( \dfrac{d}{2h} \right)^2 = \dfrac{f_{MUF}^2}{f_{c}^2} - 1\\
d = 2h\sqrt{\dfrac{f_{MUF}^2}{f_{c}^2} - 1}
\end{align}
$$

# 6 RF spectrum and its propagation characteristics
