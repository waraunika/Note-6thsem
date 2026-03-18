# 1 Ground or Surface Wave
## 1.1 Concept
- also called surface wave propagation
- refers to radio waves that travel along the earth's surface, following its curvature.
- these waves glide over the ground and enable communication beyond the optical horizon through diffraction
-  Geometry of Ground Reflected Wave
  -  ![[Pasted image 20260318125233.png]]
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
# 3 Direct and Ground Reflected wave
### 3.1.1 Duct Propagation
# 4 Ionospheric or Sky Wave
Short wave is Sky Wave
- long distance communication system
- large area coverage with skip distance 
- higher the frequency greater the Energy
- wave reflected back to earth
- 2 - 30 MHz

- radio window
	- 300 kHz to 10 GHz
	- HF: 3 MHz - 30 MHz
	- VHF: 30 MHz - 300 MHz
	- UHF: 300 MHz - 3 GHz

- Band: Mainly HF
- wave is affected by atmospheric (ionospheric) changes
- medium play vital role in iosphere
- transmission mode AM
- Tx power: Few kWs (Typically 0.5 ~ 5 kW)
- Different layers in ionosphere take part
- refraction for different SW frequencies

- Minimum skip distance is influenced by number of factors
	- frequency of operation
	- state of the ionosphere
	- angle of radiation
	- degree of ionization
	- seasons
	- local time is very important for ionizations

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
### 4.1.1 Sky Wave
- Different layers in ionospheric affect sky wave
- D-layer exists only during Day time
- E-layer more active at Night time
- During day time F-Layer is divided into Two parts
- E-layer using day time @ 2400 km cover
- higher frequency needs greater ionization density for radio waves reflection back

### 4.1.2 Ionospheric or Sky Wave
- more sunspots, the greater the ionizations
- thus 11 year's sunspot cycle is considered
- actually, signal is Refracted from ionized layers due to layer's refractive index change
- but it looks like the signal was reflected from ionosphere is a radio mirror, at virtual height of the ionosphere
- revolves around the refraction mechanism in the ionosphere

### 4.1.3 Ionosphere
- region lying between 90 km to 450 km
- contains charge particles & takes ionization
- plays important role for space communications
- density of Air at the bottom 1.29 x 10 $^{-5}$ kg / m$^3$
- decreases gradually at the to about 1.29 x 10$^{-10}$ kg / m$^3$
- temperature rises form -90$^0$ C to 400$^0$ C to a height of 110 km
- this region is also called thermosphere
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

### 4.1.4 Ionospheric or Sky Wave
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

-> sanjeevan sir told me to contact him after our class he will be in department 
- 5pm ki 4pm? k ko lagi  after class? 2:25 
- yo paxi nai hola class ma koi pani xaina yetti matra student vayo vane I will cancel SG sir discussion session sir le alik manchhe chainxa class ma thorai vayo vane lidina vaneko xa 
# 5 Tropospheric Wave
# 6 Radio frequency spectrum and its propagation characteristics
