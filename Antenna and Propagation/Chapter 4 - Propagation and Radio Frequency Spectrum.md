# 1 Ground or Surface Wave
## 1.1 Concept
- also called surface wave propagation
- refers to radio waves that travel along the earth's surface, following its curvature.
- these waves glide over the ground and enable communication beyond the optical horizon through diffraction
---
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
---
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
---
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
---
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
---
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
---
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

---
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
---
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
## 3.1 Concept
- A ground reflected wave
	- is the component of a transmitted radio signal
	- that reaches the receiver after reflecting off the Earth's surface 
	- or other large obstacles (hills, buildings). 
- It typically combines with the direct (LOS) wave in space wave propagation,
	- leading to interference and multipath effects.
---
## 3.2 Technical Details
### 3.2.1 Propagation Context
Radio waves propagate via three primary mechanisms:
1. **Ground wave** – follows Earth's surface
2. **Space wave** – consists of:
    - Direct (LOS) wave
    - **Indirect (Ground reflected) wave**
3. **Sky wave** – reflected by ionosphere
### 3.2.2 Reflection Geometry
- Reflection occurs from:
    - Earth's surface
    - Hills
    - Large buildings
- Geometry of ground reflected wave: _(refer to diagram)_
	-  ![[Pasted image 20260318125233.png]]
---
## 3.3 Key Characteristics
| Parameter       | Detail                                |
| --------------- | ------------------------------------- |
| Nature          | Indirect component of space wave      |
| Interaction     | Combines with direct wave at receiver |
| Primary effect  | Constructive/destructive interference |
| Frequency range | Same as space wave (>30 MHz)          |
### 3.3.1 Mathematical Consideration
- The reflected wave undergoes:
    - Phase reversal (typically 180° for horizontal polarization at grazing incidence)
    - Amplitude reduction (depending on reflection coefficient of surface)
    - Path length difference relative to direct wave
- Resulting field at receiver = Direct wave + Reflected wave (vector sum)
---
## 3.4 Other Details
### 3.4.1 Reflection Effects
- Reflection coefficient depends on:
    - Surface material (conductivity, permittivity)
    - Polarization (vertical/horizontal)
    - Incident angle
    - Frequency
### 3.4.2 Typical Scenarios
| Surface Type  | Reflection Behavior                 |
| ------------- | ----------------------------------- |
| Smooth water  | Strong reflection, low loss         |
| Rough terrain | Diffuse reflection, scattered       |
| Urban area    | Multiple reflections from buildings |
### 3.4.3 Interference Pattern
- Direct and reflected waves combine to produce:
    - **Lobes** – constructive interference (signal enhancement)
    - **Nulls** – destructive interference (signal cancellation)
- Pattern varies with antenna heights and distance
## 3.5 Adv/Disadv
- Adv
	1. Can provide signal enhancement at certain distances (constructive interference)
	2. Extends coverage beyond pure LOS in some cases
	3. Useful for over-water propagation paths
- Disadv
	1. Causes **multipath fading** – signal varies with location and time
	2. Creates **null zones** – areas of very weak reception
	3. Makes system design complex (requires height optimization)
	4. Frequency-selective fading in wideband systems
---
## 3.6 Applications
1. **Antenna siting** – optimizing heights to minimize destructive interference
2. **Radar** – ground reflection used in target detection (multipath radar)
3. **Broadcast planning** – predicting coverage areas with nulls and lobes
4. **Wireless link design** – accounting for ground bounce in link budget
- Reflected Signal as the transmission will be reflected by a number of objects
---
# 4 Duct Propagation
## 4.1 Concept
- Duct propagation occurs when radio waves become trapped in an atmospheric layer (duct) caused by temperature inversion in the troposphere.
- The duct acts as a waveguide, guiding VHF/UHF signals far beyond the optical horizon without requiring line-of-sight.
---
## 4.2 Technical Details
### 4.2.1 Frequency Range
- **Primary affected frequencies**: 50 MHz to 450 MHz
- **Bands**: VHF and UHF
- Can extend up to ~5 GHz in strong ducts
### 4.2.2 Propagation Distance
- Typical range: few hundred km
- Maximum reported: up to 2000 km
- Far exceeds normal LOS (30-70 km)
### 4.2.3 Height of Duct
- Typically forms **30-50 meters** above ground
- Occurs in the troposphere (extends up to 15 km from Earth's surface)
- Figure for working of propagation of waves in atmospheric duct
	- ![[Pasted image 20260319131551.png]]
### 4.2.4 Normal vs Inversion Conditions
| Parameter            | Normal Conditions                 | Temperature Inversion (Ducting)   |
| -------------------- | --------------------------------- | --------------------------------- |
| Temperature gradient | -6.5°C/km (decreases with height) | Temperature increases with height |
| Air density          | Decreases with height             | Warm air trapped above cool air   |
| Refractive index     | Decreases gradually               | Super-refraction occurs           |
| Wave behavior        | Bends slightly                    | Trapped in duct                   |
### 4.2.5 Refractive Index Relationship
- As air density decreases → refractive index increases
- Under inversion, change in refractive index is **non-linear** and creates a duct
---
## 4.3 Other Details
### 4.3.1 Mechanism of Duct Formation
1. Warm air layer forms above cooler air (often over water surfaces)
2. Temperature inversion creates a **refractive boundary**
3. Radio waves entering this boundary undergo **super-refraction**
4. Waves become trapped and guided along Earth's curvature
5. Propagation spreads **horizontally** (not vertically)
### 4.3.2 Types of Atmospheric Ducts
| Duct Type          | Formation                      | Typical Duration       |
| ------------------ | ------------------------------ | ---------------------- |
| Surface-based duct | Extends from ground upward     | Few hours to days      |
| Elevated duct      | Above ground (30-50 m typical) | Several hours          |
| Evaporation duct   | Over warm water bodies         | Persistent over oceans |
### 4.3.3 Propagation Behavior
- Waves undergo **successive refractions** between duct boundaries
- Duct acts as a **waveguide in the atmosphere**
- Signal loss is significantly lower than normal propagation
- Enables **beyond-horizon** communication without LOS
### 4.3.4 Comparison with Ground Wave
| Aspect        | Ground Wave | Duct Propagation         |
| ------------- | ----------- | ------------------------ |
| Mechanism     | Diffraction | Refraction / Waveguiding |
| Frequency     | <2 MHz      | 50-450 MHz               |
| Range         | ~1000 km    | 2000 km (max)            |
| LOS required? | No          | No                       |
## 4.4 Adv/Disadv
- Adv
	1. **Extreme range** – Communication far beyond horizon (hundreds to thousands of km)
	2. **No LOS required** – Unlike normal space wave propagation
	3. **Uses VHF/UHF bands** – Enables wide bandwidth communication over long distances
	4. **Lower power** – Exploits natural atmospheric phenomenon
- Disadv
	1. **Unpredictable** – Occurs only under specific weather conditions
	2. **Temporary** – Ducts last hours to days, then disappear
	3. **Interference cause** – Long-distance signals interfere with local services on same frequency
	4. **Not controllable** – Cannot be engineered reliably; only exploited when present
	5. **Seasonal/geographic** – More common over warm water bodies (e.g., Persian Gulf, Mediterranean)
---
## 4.5 Applications
### 4.5.1 Primary Exploitation
1. **Over-the-horizon radar** – Detecting targets beyond normal radar range
2. **Long-range VHF communication** – Military and maritime use
3. **TV/FM DX-ing** – Amateur radio enthusiasts receiving distant stations
### 4.5.2 Affected Systems (Usually Unintentionally)
| System            | Effect During Ducting                      |
| ----------------- | ------------------------------------------ |
| TV broadcast      | Reception of stations hundreds of km away  |
| Cellular networks | Co-channel interference from distant cells |
| FM radio          | Distant stations override local ones       |
| VHF air traffic   | Unexpected long-range communication        |
### 4.5.3 Geographic Hotspots
- Coastal regions (warm land/water temperature differences)
- Persian Gulf (famous for ducting)
- Mediterranean Sea
- Great Lakes region
- Tropical oceans (evaporation ducts are persistent)
### 4.5.4 Weather Conditions Favoring Ducting
- **Temperature inversion** after clear, calm nights
- **High-pressure systems** with stable air
- **Warm air over cool water** (sea breezes)
- **Early morning hours** (radiation inversions)
---
## 4.6 Summary Table: All Three Wave Components

| Wave Component        | Mechanism                 | Frequency  | Range       | Reliability              |
| --------------------- | ------------------------- | ---------- | ----------- | ------------------------ |
| Direct (LOS) wave     | Line-of-sight             | >30 MHz    | 30-70 km    | High (weather dependent) |
| Ground reflected wave | Reflection + interference | >30 MHz    | Same as LOS | Variable (fading)        |
| Duct propagation      | Atmospheric waveguiding   | 50-450 MHz | 200-2000 km | Low (weather dependent)  |

---
# 5 Ionospheric or Sky Wave
## 5.1 Technical Details
### 5.1.1 Frequency Range
| Parameter       | Value                                     |
| --------------- | ----------------------------------------- |
| Operating range | **2 MHz – 30 MHz**                        |
| Band            | HF (High Frequency, 3-30 MHz)             |
| Below 2 MHz     | Absorbed by D layer                       |
| Above 30 MHz    | Passes through ionosphere (not reflected) |
### 5.1.2 Transmission Characteristics
| Parameter          | Typical Value                      |
| ------------------ | ---------------------------------- |
| Transmission power | 0.5 – 5 kW (few kW)                |
| Transmission mode  | AM (primarily)                     |
| Propagation method | Refraction (appears as reflection) |
| Coverage           | Large area with skip distance      |
- ![[Pasted image 20260319133558.png]]
### 5.1.3 Critical Frequency Formula
The maximum frequency at which total internal reflection occurs at vertical incidence (90°):
$$\large fcrt=9\sqrt{N_{max}} $$​
Where:
- $f_{crt}$ = Critical frequency (Hz)
- $N_{max}$ = Maximum electron density (electrons/m³)
### 5.1.4 Frequency vs Ionization Relationship
- Higher frequencies require **greater ionization density** for reflection
- Sunspot activity increases ionization (11-year cycle)
- More sunspots → greater ionization → higher usable frequencies
---
## 5.2 Ionosphere Structure
### 5.2.1 Overview
- **Region**: 90 km to 450 km above Earth's surface
- **Also called**: Thermosphere (temperature rises from -90°C to 400°C at 110 km)
- **Contains**: Charged particles, free electrons, ionized gases
- **Density variation**:
    - Bottom: 1.29 × 10⁻⁵ kg/m³
    - Top: 1.29 × 10⁻¹⁰ kg/m³
### 5.2.2 Layer Structure
| Layer  | Height Range | Day/Night           | Critical Frequency | Electron Density (max) | Notes                                   |
| ------ | ------------ | ------------------- | ------------------ | ---------------------- | --------------------------------------- |
| **D**  | 50-90 km     | Day only            | ~100 kHz           | 400/cc                 | Highly absorptive; limits MW/LW daytime |
| **E**  | 90-140 km    | Both (stronger day) | 3-5 MHz            | 4×10⁵/cc               | Useful for SW daytime comm              |
| **F₁** | 150-250 km   | Day only            | 5-12 MHz           | <4×10⁵/cc              | Merges with F₂ at night                 |
| **F₂** | 250-500 km   | Both                | 5-12 MHz           | Variable               | Most important for HF long-distance     |
### 5.2.3 Layer Details
#### 5.2.3.1 D Layer
- **Ionization mechanism**: Photoionization of O₂ molecules
- **Present**: Only during daytime (absorbs UV)
- **Absent**: At night (recombines)
- **Critical frequency (f_crt)**: ~100 kHz at vertical incidence
- **Maximum usable frequency (MUF)**: <3 MHz
- **At 30 MHz**: Waves cross D layer with attenuation
- **For VLF/LF**: Space between D layer and ground acts as **waveguide (duct)**
- **Limitation**: High absorption at LW/MW — daytime communication not possible via D layer
#### 5.2.3.2 E Layer (Kennelly-Heaviside Layer)
- **Maximum density height**: ~110 km
- **Ionization mechanism**: X-rays ionizing all gases
- **Electron density**: Max 4×10⁵/cc at 110 km
- **Critical frequency**: ~3-5 MHz (HF range)
- **Characteristics**:
    - Almost constant diurnal/seasonal variations
    - Governed by UV light from sun
    - Uniformly decays at night
    - Permits medium-distance communication in LF/HF bands
- **Night behavior**: D layer rises, E layer lowers → merge into single E layer
#### 5.2.3.3 F Layer (Appleton Layer)
**F₁ Layer (Daytime only)**:
- Height: 150-250 km (summer), 200-220 km (winter)
- Maximum electron density: ~220 km
- Little diurnal/seasonal variation
- Ionization: UV, X-rays, cosmic rays
- Remains ionized all the time
**F₂ Layer (Primary for HF)**:
- Height: 250-500 km
- Most variable layer
- **Responsible for most HF long-distance communication**
- Night behavior: F₁ rises, F₂ lowers → merge into single F₂ layer
### 5.2.4 Electron Density vs Height Profile

*(Refer to diagram: N vs h showing peaks at E layer ~110 km and F layer ~250-350 km)*
- ![[Pasted image 20260319134359.png]]
- **90-140 km (E)**: High electron density
- **140-250 km**: Density decreases
- **250-350 km (F)**: High electron density again
---
## 5.3 Other Details
### 5.3.1 Refraction Mechanism
#### 5.3.1.1 Principle
- Charge density of ionosphere **increases with height**
- Refractive index **decreases with height**
- Wave travels from higher to lower refractive index → **total internal refraction** (appears as reflection)
#### 5.3.1.2 Virtual Height
- Signal appears to reflect from a "radio mirror" at virtual height
- Actual mechanism is gradual refraction through ionized layers
### 5.3.2 Factors Affecting Reception
| Factor                 | Effect                                  |
| ---------------------- | --------------------------------------- |
| D/E layer absorption   | Reduces signal strength                 |
| Diurnal variation      | Day/night changes layer behavior        |
| Seasonal variation     | Sun angle changes ionization            |
| 11-year sunspot cycle  | Peak cycle = higher usable frequencies  |
| Frequency used         | Higher frequencies need more ionization |
| Takeoff angle          | Affects skip distance                   |
| Ionospheric conditions | Variable, unpredictable                 |
### 5.3.3 Skip Distance
Minimum skip distance depends on:
- Operating frequency
- Ionization state
- Radiation angle
- Time of day
- Season
### 5.3.4 Sporadic E (Es)

|Aspect|Detail|
|---|---|
|Nature|Intense, unpredictable ionization clouds in E region|
|Ionization level|Up to 5× normal peak levels|
|Frequency range|Few MHz to lower VHF (occasionally up to 150 MHz)|
|Behavior|Sporadic, unpredictable, not reliable|
|Use|Radio amateurs; not used for commercial communication|
|Effect|Adds noise, enables very long distances at low power|
## 5.4 Adv/Disadv
- Adv
	1. **Long distance** – Enables global communication (hundreds to thousands of km)
	2. **No infrastructure** – No satellites, cables, or repeaters needed
	3. **Wide coverage** – Large area coverage with skip distance
	4. **Beyond horizon** – Not limited by Earth's curvature
	5. **Low power potential** – Can work with few kW
	6. **Frequency flexibility** – Different layers support different frequency ranges
- Disadv
	1. **Unreliable** – Highly variable with time of day, season, sunspot cycle
	2. **Frequency dependent** – Only works in 2-30 MHz range
	3. **Absorption** – D layer absorbs lower frequencies during daytime
	4. **Fading** – Multipath from multiple layers causes signal variation
	5. **Skip zone** – Dead zone between ground wave coverage and first sky wave return
	6. **Noise** – Sporadic E and atmospheric noise affect reception
	7. **Predictability** – Requires propagation forecasting
---
## 5.5 Applications
### 5.5.1 Primary Applications
1. **International broadcasting** – Shortwave radio (BBC, Voice of America, etc.)
2. **Long-distance amateur radio** – Ham radio operators (DX communication)
3. **Maritime communication** – Ship-to-shore HF links
4. **Aeronautical HF** – Long-range aircraft communication over oceans
5. **Military communication** – Tactical and strategic HF networks
6. **Emergency communication** – Disaster relief when infrastructure fails
7. **Remote area communication** – Polar regions, deserts, oceans
### 5.5.2 Typical Use Cases by Layer

| Layer          | Typical Use                         |
| -------------- | ----------------------------------- |
| D (day)        | VLF/LF waveguide propagation        |
| E (day)        | Medium-distance SW communication    |
| F₁ (day)       | Long-distance HF                    |
| F₂ (day/night) | Primary for global HF communication |
### 5.5.3 Frequency Selection Guidelines

| Condition       | Usable Frequencies                                                  |
| --------------- | ------------------------------------------------------------------- |
| Daytime         | Higher frequencies (10-30 MHz) – D layer absorption lower           |
| Nighttime       | Lower frequencies (2-10 MHz) – D layer absent, E/F lower ionization |
| Sunspot maximum | Higher usable frequencies (up to 30+ MHz)                           |
| Sunspot minimum | Lower usable frequencies (down to 2-3 MHz)                          |

---
## 5.6 Frequency Spectrum Overview
| Frequency         | Range               | Radio Presence |
| ----------------- | ------------------- | -------------- |
| 10 Hz - 1 kHz     | VLF                 | —              |
| 1 kHz - 10 kHz    | VLF                 | RADIO          |
| 10 kHz - 100 kHz  | LF                  | RADIO          |
| 100 kHz - 1 MHz   | MF                  | RADIO          |
| 1 MHz - 10 MHz    | HF (3-30 MHz)       | RADIO          |
| 10 MHz - 100 MHz  | VHF (30-300 MHz)    | RADIO          |
| 100 MHz - 1 GHz   | UHF (300 MHz-3 GHz) | RADIO          |
| 1 GHz - 10 GHz    | SHF                 | RADIO          |
| 10 GHz - 100 GHz  | EHF                 | ~RADIO         |
| 100 GHz - 1 THz   | Infrared            | —              |
| 1 THz - 10 THz    | Infrared            | —              |
| 10 THz - 100 THz  | Visible             | —              |
| 100 THz - 10¹⁵ Hz | UV                  | —              |
| 10¹⁵ - 10¹⁸ Hz    | UV/X-ray            | —              |
| 10¹⁸ - 10²⁰ Hz    | X-ray               | —              |
| 10²⁰ - 10²² Hz    | Gamma               | —              |
| 10²² - 10²⁴ Hz    | Cosmic              | —              |

---
## 5.7 Summary Table: All Propagation Modes
| Mode             | Frequency  | Range       | Mechanism               | Reliability                      |
| ---------------- | ---------- | ----------- | ----------------------- | -------------------------------- |
| Ground wave      | <2 MHz     | ~1000 km    | Diffraction             | High                             |
| Space wave (LOS) | >30 MHz    | 30-70 km    | Direct line-of-sight    | Moderate                         |
| Duct propagation | 50-450 MHz | 200-2000 km | Atmospheric waveguiding | Low                              |
| Sky wave         | 2-30 MHz   | Global      | Ionospheric refraction  | Variable (sun/weather dependent) |

---
# 6 Critical Frequency, MUF, Skip Distance
## 6.1 Critical Frequency ($f_c$)
- **Definition:** The highest frequency that returns from an ionospheric layer at vertical incidence is called the **critical frequency ($f_{crt}$ or $f_c$)** for that particular layer.
- For a regular layer, it is proportional to the square root of the maximum electron density in the layer:  
  $\large f_c \propto \sqrt{N_{max}}$
  $\large f_c = 9\sqrt{N_{max}}$
---
## 6.2 Maximum Usable Frequency (MUF)
- When the frequency exceeds $f_c$, the return will depend upon the **angle of incidence** at a particular ionospheric layer.
- Thus, for a specified angle of incidence, there will be a maximum frequency which will be reflected back.
- The maximum possible value of frequency for which reflection takes place for a given distance of propagation is termed as **Maximum Usable Frequency (MUF)**.
- Beyond MUF, the wave will not be returned.
- Sky wave requires the angle of reflection to be $90^\circ$.
### 6.2.1 Derivation of MUF Formula
Let:
- $\phi_i$ = incident angle
- $\phi_r$ = reflection angle
- $n$ = refractive index

We have:  
$$\large
n=\dfrac{\sin⁡(ϕ_i)}{\sin⁡(ϕ_r)}=sin⁡(ϕ_i)=\sqrt{1-\dfrac{81N_{max}}{f^2_{MUF}}}$$
Squaring both sides:  
$$\large
\sin^2(\phi_i) = 1-\dfrac{81N_{max}}{f^2_{MUF}}
$$

Here, $f_c^2 = 81N_{max}$. 
Substituting:  
$$\large
\sin^2(\phi_i) = 1-\dfrac{f_c^2}{f^2_{MUF}}
$$
Rearranging:  
$$\large
\cos^2(\phi_i) = \dfrac{f_c^2}{f^2_{MUF}}
$$
Therefore:  
$$\large
f_{MUF} = f_c\cdot \sec(\phi_i)
$$

---
## 6.3 Skip Distance
### 6.3.1 When earth is flat
- figure for derivation
	- ![[Pasted image 20260319141440.png]]
**Parameters**
 - $AC$ = distance between two stations on Earth = $\large d$
- $O$ = midpoint, so $AO = OC = d/2$
- $BO$ = normal at incidence = $\large h$
- $\large \angle ABO = \theta_i$, $\large \angle OBC = \theta_r$
**Derivation**
From geometry:
$$\large
cos(\theta_i) = \dfrac{OB}{OA} = \dfrac{h}{\sqrt{h^2 + \dfrac{d^2}{4}}} = \dfrac{h}{h\sqrt{1+\dfrac{d^2}{4h^2}}} = \dfrac{1}{\sqrt{1+\dfrac{d^2}{4h^2}}}
$$
From the MUF and critical frequency derivation:
$$\large
f_{MUF} = f_c \sec(\theta_i)
$$
Substituting $\sec(\theta_i) = 1/\cos(\theta_i)$:
$$\large
f_{MUF} = f_c \sqrt{1+\left( \dfrac{d}{2h} \right)^2}
$$
Rearranging, **Final equation**:
$$\large
d = 2h\sqrt{\dfrac{f_{MUF}^2}{f_{c}^2} - 1}
$$
---
### 6.3.2 When earth is curved
![[Pasted image 20260404104944.png]]
**Parameters:**
- $d'$ = arc distance between two stations on curved Earth
- $R$ = radius of Earth
- $h$ = height of the ionospheric layer
- $\theta$ = half of the central angle subtended by the arc
---
**Step 1: Basic geometric relations**
Arc length:  
$$\large d' =2Rθ$$
Angle:
$$\large 2θ=d'/R$$
From Geometry:
$$
AD=R\sin⁡(θ)
$$
$$OD=R\cos⁡(θ)$$
$$BD=OE+EB−OD=R+h−R\cos⁡(θ)$$
​
---
**Step 2: Express $\cos(\theta_i)$**
$$\large
AB = \sqrt{(AD)^2+(BD)^2} = \sqrt{(R\sin(\theta))^2 + (R + h - R\cos(\theta))^2}$$
$$\large
\cos(\theta_i) = \dfrac{BD}{AB} = \dfrac{R+h-R\cos(\theta)}{\sqrt{(R\sin(\theta))^2 + (R + h - R\cos(\theta))^2}}
$$
Therefore,
$$\large 
(\cos(\theta_i))^2 = \dfrac{(R+h-R\cos(\theta))^2}{(R\sin(\theta))^2 + (R + h - R\cos(\theta))^2}
$$
From MUF relation:
$$\large
\dfrac{f_c^2}{f^2_{MUF}} = (\cos(\theta_i))^2
$$
---
**Step 3: Approximations for small $\theta$**
We know:
$$\large
\cos(\theta) = \dfrac{OA}{OB} = \dfrac{R}{R+h}
$$
Since $\theta$ is very small, expand using binomial theorem
$$\large
\cos(\theta) = \dfrac{R}{R+h} = \left(1 + \dfrac{h}{R} \right)^{-1} \cong \left(1 - \dfrac{h}{R} \right)
$$
Using Taylor series for small $\theta$:
$$\large
\cos(\theta) = 1- \theta^2/2
$$
Equating the two expressions:
$$\large
1 - \theta^2/2 = 1 - h/R
$$
or,
$$\large
\theta^2 = \dfrac{2h}{R}
$$
Now, expression $d'$ in terms of $h$:
$$\large
d'^2 = 4R^2\theta^2 = 4R^2\ \dfrac{2h}{R} = 8hR
$$
And
$$\large
h = \dfrac{d'^2}{8R}
$$
Also:
$$\large
\cos(\theta) = 1 - \dfrac{h}{R} = 1 - \dfrac{d'^2}{8R^2}
$$

---
**Step 4: Derive $f_{MUF}$ in terms of $d'$**
From $$\large f_{MUF}^2 = f_c^2 \sec^2(\theta_i) = f_c^2 \cdot \frac{1}{\cos^2(\theta_i)}$$
we get, 
$$\large
F_{MUF} = f_c^2 \dfrac{(R\sin\theta)^2 + (R+h-R\cos\theta)^2}{(R+h-R\cos\theta)^2}
$$
Substitute $$\large R\sin\theta \approx R \cdot \theta = R \cdot \frac{d'}{2R} = \frac{d'}{2}$$
And substitute $$\large \cos\theta = 1 - \frac{d'^2}{8R^2}$$
To get:
$$\large
R + h - R\cos(\theta) = R + h - R\left( 1 - \dfrac{d'^2}{8R^2}\right) = h + \dfrac{d'^2}{8R}
$$
Also,
$$\large
(R\sin(\theta))^2 = \dfrac{d'^2}{4}
$$
Therefore:
$$\large
f_{MUF}^2 = f_c^2 \cdot\dfrac{\dfrac{d'^2}{4} + h+\dfrac{d'^2}{8R}}{\left(h+\dfrac{d'^2}{8R}\right)^2}
$$
Simplify to get **main formula**:
$$\large
f_{MUF}^2 = f_c  \left(1 + \dfrac{d'^2/4}{\left( h+\dfrac{d'^2}{8R} \right)^2} \right)
$$
**Final curved Earth MUF Formula**:
$$\large
f_{MUF} = f_c \sqrt{ 1 + \dfrac{d'^2/4}{\left(h+\dfrac{d'^2}{8R}\right)^2} }
$$

---
**Step 5: Express skip distance in terms of MUF**
Let:
$$\large
X = \sqrt{\left( \dfrac{f_{MUF}}{f_c} \right)^2 - 1}
$$
from the geometry, and F$_{MUF}$,
$$\large
d' = 2 \left( h + \dfrac{d'^2}{8R} \right)\ X
$$
This is a quadratic equation, in $d'$. solving for $d'$ we get:
$$\large d' = \dfrac{2R}X \pm 2\sqrt{\left( \dfrac RX \right)^2 - 2hR}$$
---
## 6.4 Additional Frequency Definitions
1.  Lowest Usable Frequency (LUF)
The frequency below which the entire power gets absorbed by the ionosphere.
2.  Optimum Usable Frequency (OUF)
The frequency at which there is optimum return of wave energy (maximum signal strength with minimal absorption and fading).
---
# 7 The RF Spectrum & Propagation Characteristics

## 7.1 The Complete Electromagnetic Spectrum
| Frequency Range                               | Wavelength (Free Space) | Designation   | Common Applications                          |
| --------------------------------------------- | ----------------------- | ------------- | -------------------------------------------- |
| < 3 Hz                                        | > 100 Mm                | —             | Geophysical prospecting                      |
| 3 - 30 Hz                                     | 10 - 100 Mm             | **ELF**       | Detection of buried metals                   |
| 30 - 300 Hz                                   | 1 - 10 Mm               | **SLF**       | Power transmission, submarine communications |
| 300 Hz - 3 kHz                                | 0.1 - 1 Mm              | **ULF**       | Telephone, audio, mine communication         |
| 3 - 30 kHz                                    | 10 - 100 km             | **VLF**       | Navigation, positioning, naval communication |
| 30 - 300 kHz                                  | 1 - 10 km               | **LF**        | Navigation, radio beacons, Longwave AM       |
| 0.3 - 3 MHz                                   | 0.1 - 1 km              | **MF**        | AM broadcasting (Medium Wave)                |
| 3 - 30 MHz                                    | 10 - 100 m              | **HF**        | Shortwave broadcasting, Citizen's band       |
| 30 - 300 MHz                                  | 1 - 10 m                | **VHF**       | TV (Band I/III), FM Radio, Police            |
| 0.3 - 3 GHz                                   | 10 - 100 cm             | **UHF**       | Radar, TV (Band IV/V), GPS, Cellular, WiFi   |
| 3 - 30 GHz                                    | 1 - 10 cm               | **SHF**       | Radar, Satellite Comms, Microwave Links      |
| 30 - 300 GHz                                  | 0.1 - 1 cm              | **EHF**       | Radar, Remote Sensing, 5G, Security Scanners |
| 0.3 - 1 THz                                   | 0.3 - 1 mm              | Millimeter    | Astronomy, Meteorology                       |
| $10^{12} - 10^{14}$ Hz                        | 3 - 300 $\mu$m          | Infrared      | Heating, Night vision, Optical fiber         |
| $3.95 \times 10^{14} - 7.7 \times 10^{14}$ Hz | 390 - 760 nm            | Visible Light | Vision, Optical communication                |
| $10^{15} - 10^{18}$ Hz                        | 0.3 - 300 nm            | UV            | Sterilization                                |
| $10^{16} - 10^{22}$ Hz                        | —                       | X-rays        | Medical diagnosis                            |
| $10^{18} - 10^{22}$ Hz                        | —                       | Gamma Rays    | Cancer therapy, Astrophysics                 |
| > $10^{22}$ Hz                                | —                       | Cosmic Rays   | Astrophysics                                 |
## 7.2 Broadcast Frequency Standards
| Service             | Frequency Range | Band          | Channel Spacing        |
| ------------------- | --------------- | ------------- | ---------------------- |
| **AM Radio** (Asia) | 535 - 1625 kHz  | MF            | 10 kHz (107 channels)  |
| **FM Radio**        | 88 - 108 MHz    | VHF (Band II) | 200 kHz (100 channels) |
| **TV Band I**       | 54 - 88 MHz     | VHF           | Channels 2 - 6         |
| **TV Band III**     | 174 - 216 MHz   | VHF           | Channels 7 - 13        |
| **TV Bands IV & V** | 470 - 806 MHz   | UHF           | Channels 14 - 69       |
## 7.3 IEEE Microwave Band Designations
| Frequency Range | Band Name |
| --------------- | --------- |
| 500 - 1000 MHz  | **P**     |
| 1 - 2 GHz       | **L**     |
| 2 - 4 GHz       | **S**     |
| 4 - 8 GHz       | **C**     |
| 8 - 12.4 GHz    | **X**     |
| 12.4 - 18 GHz   | **Ku**    |
| 18 - 26.5 GHz   | **K**     |
| 26.5 - 40 GHz   | **Ka**    |
| 30 - 50 GHz     | Q         |
| 40 - 60 GHz     | **U**     |
| 50 - 75 GHz     | V         |
| 60 - 90 GHz     | E         |
| 75 - 110 GHz    | W         |
| 90 - 140 GHz    | F         |
| 110 - 170 GHz   | D         |
## 7.4 Band-by-Band Propagation Characteristics
### 7.4.1 Extremely Low Frequency (ELF) / SLF / ULF
- **Frequency:** 3 Hz – 3 kHz
- **Wavelength:** 100,000 – 100 km
- **Propagation:** Ground wave, diffracts around large obstacles.
- **Unique Property:** Can penetrate seawater.
- **Key Application:** Communication with submerged submarines (huge grounded wire antennas / ground dipoles).
- **Other Uses:** Atmospheric/magnetospheric science, communication within mines (ULF).
### 7.4.2 Very Low Frequency (VLF)
- **Frequency:** 3 – 30 kHz
- **Wavelength:** 100 – 10 km
- **Main Wave:** Ground/Surface Wave
- **Propagation Method:** Diffraction
- **Tx Power:** Up to a few MW
- **Tx Mode:** AM
- **Applications:** Navigation, time signals, submarine communications, wireless heart rate monitors, geophysics.
### 7.4.3 Low Frequency (LF) / Long Wave (LW)
- **Frequency:** 30 – 300 kHz
- **Wavelength:** 10 – 1 km
- **Main Wave:** Ground/Surface Wave
- **Propagation Method:** Diffraction
- **Tx Power:** Up to a few MW
- **Tx Mode:** AM
- **Broadcast Range:** 148.5 – 283.5 kHz
- **Applications:** Navigation, time signals, AM longwave broadcasting, RFID, amateur radio, radio beacons.
### 7.4.4 Medium Frequency (MF) / Medium Wave (MW)
- **Frequency:** 300 – 3000 kHz (Broadcast: 535.5 – 1625.5 kHz)
- **Wavelength:** 1000 – 100 m
- **Main Wave:** Ground/Surface Wave (glides over Earth's surface).
- **Polarization:** Linear (mostly Vertical)
- **Propagation Method:** Diffraction
- **Tx Power:** Up to a few kW
- **Tx Mode:** AM
- **Antenna Types:** Marconi, Whip, Telescopic, Aerial.
- **Note:** Less absorption for frequencies < 100 kHz.
- **Applications:** Regional radio broadcasting, amateur radio, avalanche beacons, radio/aeronautical radio-navigation, standard time/frequency services.
### 7.4.5 High Frequency (HF) / Short Wave (SW)
- **Frequency:** 3 – 30 MHz
- **Wavelength:** 100 – 10 m
- **Main Wave:** Sky Wave (Ionospheric)
- **Propagation Method:** Refraction (appears as reflection)
- **Tx Power:** Few kW (0.5 – 5 kW typical)
- **Tx Mode:** AM
- **Antenna Types:** Dipole, Yagi-Uda, Log-periodic, Vertical whip.
- **Applications:** Shortwave broadcasting, citizen's band, amateur radio, over-the-horizon aviation/radar, RFID, ALE, NVIS, marine, mobile radio telephony, telemetry, radio astronomy.
### 7.4.6 Very High Frequency (VHF)
- **Frequency:** 30 – 300 MHz
- **Wavelength:** 10 – 1 m
- **Main Wave:** Direct/Space Wave
- **Propagation Method:** Line-of-Sight (LOS)
- **Tx Power:** Up to a few hundred Watts
- **Tx Mode:** AM / FM / PM
- **Antenna Types:** Dipole, Folded Dipole, Yagi-Uda, Whip, Collinear.
- **Applications:** FM/TV broadcasts, air traffic control, land/maritime mobile, amateur radio, weather radio, military/police comms.
### 7.4.7 Ultra High Frequency (UHF)
- **Frequency:** 300 – 3000 MHz (3 GHz)
- **Wavelength:** 1 – 0.1 m
- **Main Wave:** Direct/Space Wave
- **Propagation Method:** LOS (Tropospheric ducting possible)
- **Tx Power:** Few Watts
- **Tx Mode:** AM / FM / PM
- **Antenna Types:** Parabolic, Yagi-Uda, Patch, Helical, Phased Arrays, Whip.
- **Notes:**
    - Short wavelengths permit highly directional antennas.
    - TV Band: 470 – 806 MHz.
    - "Money Band" for cellular/PCS (800-2500 MHz).
- **Applications:** Radar, TV, GPS, cellular/PCS, WiFi, Bluetooth, ZigBee, 5G, satellite radio, microwave ovens (915 MHz/2.45 GHz), ADSB.
### 7.4.8 Super High Frequency (SHF) / Centimeter Waves
- **Frequency:** 3 – 30 GHz
- **Wavelength:** 100 – 10 mm
- **Main Wave:** Direct/Space Wave
- **Propagation Method:** Strictly LOS
- **Tx Power:** Up to a few Watts
- **Tx Mode:** AM / FM / PM
- **Antenna Types:** Aperture antennas (Parabolic, Horn), Phased Arrays.
- **Notes:**
    - Base of satellite communications and point-to-point wideband relay.
    - Narrow beams are used for communication.
    - Used for industrial heating, medical diathermy, microwave hyperthermy (cancer treatment).
- **Applications:** Most modern radars, satellite TV (DBS), microwave links, wireless LAN, amateur radio, STL links.
### 7.4.9 Extremely High Frequency (EHF) / Millimeter Waves
- **Frequency:** 30 – 300 GHz
- **Wavelength:** 10 – 1 mm
- **Main Wave:** Direct/Space Wave
- **Propagation Method:** Strictly LOS (short range, <1 km typically)
- **Tx Power:** Few Watts
- **Tx Mode:** AM / FM / PM
- **Antenna Types:** High-gain aperture antennas, Microstrip arrays.
- **Notes:**
    - First investigated by J. C. Bose (reached 60 GHz in 1894-96).
    - High atmospheric attenuation (Oxygen at 60 GHz, Water vapor at 24 GHz & 184 GHz).
    - Severe "rain fade" (wavelength similar to raindrop size).
    - Used in 5G networks, military fire-control radar, airport security scanners.
- **Applications:** Military support, space research, radio astronomy, microwave relays, remote sensing, directed-energy weapons, mmWave scanners (802.11ad/WiGig).
- **Frequency:** $10^{12} - 10^{14}$ Hz
- **Wavelength:** 3 – 300 $\mu$m
- **Propagation:** Strictly LOS, significant atmospheric absorption (does not penetrate fog).
- **Applications:** Optical fiber communications, very short-range wireless, building-to-building links, night vision, heating.
---
## 7.5 Summary: Long Wave, Medium Wave, and Short Wave
| Feature                  | **Long Wave (LW)**                                          | **Medium Wave (MW)**                                     | **Short Wave (SW)**                                                         |
| ------------------------ | ----------------------------------------------------------- | -------------------------------------------------------- | --------------------------------------------------------------------------- |
| **Frequency Range**      | 30 - 300 kHz (LF)                                           | 300 - 3000 kHz (MF)                                      | 3 - 30 MHz (HF)                                                             |
| **Wavelength**           | 10 - 1 km                                                   | 1000 - 100 m                                             | 100 - 10 m                                                                  |
| **Primary Propagation**  | Ground / Surface Wave                                       | Ground / Surface Wave (Day)  <br>Sky Wave (Night)        | Sky Wave (Ionospheric)                                                      |
| **Daytime Range**        | Up to 1000 km (stable)                                      | 100 - 200 miles (ground wave)                            | Global (via F-layer)                                                        |
| **Nighttime Range**      | Similar to day (stable)                                     | Hundreds to thousands of km (sky wave appears)           | Global (improved, lower frequencies)                                        |
| **Key Characteristics**  | Follows Earth's curvature,  <br>very stable, large antennas | Day: Ground wave  <br>Night: Sky wave causes fading/skip | "Skip distance",  <br>dependent on sunspots,  <br>unreliable but long-range |
| **Typical Applications** | Navigation (NDB),  <br>Time signals,  <br>Submarine comms   | AM Broadcasting,  <br>Regional radio                     | International broadcasting,  <br>Amateur radio,  <br>Maritime/Aero HF       |
| **Antenna Size**         | Very Large (hundreds of meters)                             | Moderate (tens of meters)                                | Small (meters)                                                              |
| **Atmospheric Effect**   | Very little                                                 | Nighttime ionospheric reflection                         | Highly dependent on solar activity                                          |
