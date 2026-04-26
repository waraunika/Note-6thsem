# 1 Concept and Definitions
- Definition:
	- An optical fiber is a
	- flexible transparent fiber
	- made of glass (silica) or plastic
	- that acts as a waveguide for light.
- It is slightly thicker than human hair
- It is used to transmit light between two ends of fiber.
- First developed: 1970
- Revolutionized: Telecommunications, enabling the Information Age
- Core principle: Total Internal Reflection (TIR)
- Nature:
	- Transparent dielectric medium
	- Waveguide made for light (visible or infrared)
	- Can be used as a component in integral optical circuits or as transmission medium for local/long-distance optical communication.
- Figure:
	- ![[Pasted image 20260426125621.png | 400]]
# 2 Optical Fiber Communication System
## 2.1 Diagrams
```
┌─────────────┐    ┌────────────────┐    ┌──────────────┐   ┌───────────────┐    ┌─────────────┐
│ Information │───▶│    Optical     │───▶│   Optical    │───│    Optical    │───▶│ Destination │
│   Source    │    │  Transmitter   │    │    Fiber     │   │   Receiver    │    │             │
└─────────────┘    └────────────────┘    └──────────────┘   └───────────────┘    └─────────────┘
                           │                     │                  │
                           ▼                     ▼                  ▼
                       (LED/Laser)          (Waveguide)       (Photodetector)
```
![[Pasted image 20260426125852.png | 600]]
![[Pasted image 20260426125936.png | 600]]
## 2.2 Elements
|Element|Function|Key Components|
|---|---|---|
|**Transmitter**|Converts electrical signal to optical signal|Light source (LED or Laser Diode), driver circuit|
|**Optical Fiber**|Guides light from transmitter to receiver|Core (high $n_1$), Cladding (low $n_2$), Coating|
|**Receiver**|Converts optical signal back to electrical signal|Photodetector (PIN diode, APD), amplifier, signal processor|
|**Repeater** (long distance)|Regenerates and amplifies signal|Optical amplifier (EDFA), opto-electronic regenerator|
|**Coupler/Splitter**|Combines or splits optical signals|Fused biconical taper, planar waveguide|
## 2.3 Basic Operation
- The simplest fiber-optic communication system is a point-2-point connection with a single data channel.
- It has simplified Transmitter-Channel-Receiver Structure.
- Working principle:
	- Information to be transmitted is encoded
	- Transmitter converts electrical signal to light
	- Light travels through optical fiber via total internal reflection
	- Receiver converts light back to electrical signal
	- Information is decoded at destination
## 2.4 Typical Applications
- Backbone of high-speed internet (long-haul terrestrial networks)
- Trans-oceanic communication (submarine cables)
- Cable TV (CATV) distribution
- LANs: Fiber to the Home (FTTH), Fiber to the x (FTTx)
- Telephone networks in trunk lines
- Data centers needing high-bandwidth server interconnects
- Medical imaging like endoscopes
- Military and aerospace (secure, EMI-immune links)
- Industrial automation (sensors, control systems)
- Broadcast video (studio-to-transmitter links)
## 2.5 Properties to Consider when Selecting Fiber
|Property|Consideration|
|---|---|
|**Wavelength of operation**|Match source wavelength (850 nm, 1310 nm, 1550 nm) to fiber's low-loss windows|
|**Attenuation (loss)**|Lower loss (dB/km) allows longer spans between repeaters|
|**Bandwidth**|Higher bandwidth (MHz·km or GHz·km) supports higher data rates|
|**Dispersion**|Low dispersion reduces pulse spreading, enables longer distances at high bit rates|
|**Numerical Aperture (NA)**|Higher NA captures more light from source but may increase modal dispersion|
|**Core diameter**|Single-mode (8-10 μm) for long distance; Multi-mode (50-62.5 μm) for short distance|
|**Mechanical strength**|Tensile strength, bend radius, environmental resistance|
|**Cost**|Single-mode fiber and lasers are more expensive than multi-mode with LEDs|
|**Compatibility**|Match with existing connectors, splicers, and test equipment|
|**Environmental conditions**|Temperature range, humidity, chemical exposure, radiation|
## 2.6 Adv/Disadv
### 2.6.1 Performance Adv
|     | Adv                           |                                                                                   |
| --- | ----------------------------- | --------------------------------------------------------------------------------- |
| 1   | **Highest transmission rate** | Lab record: up to 10 Tbps; practical: 10 Gbps                                     |
| 2   | **High channel capacity**     | Can transmit 130,000 voice channels or 16 HDTV channels simultaneously            |
| 3   | **Very wide bandwidth**       | ~50 THz available for optical fibers                                              |
| 4   | **Low transmission loss**     | As low as 0.2 dB/km (compare: 100 m copper loss ≈ 2000 m fiber loss)              |
| 5   | **Low bit error rate (BER)**  | 1 in 10⁹ bits for fiber vs. 1 in 10⁶ for coaxial cable                            |
| 6   | **Immunity to EMI and RFI**   | No external electromagnetic interference                                          |
| 7   | **No crosstalk**              | Signals in adjacent fibers do not interfere                                       |
| 8   | **No radiation**              | Non-inductive, does not radiate energy (secure, no interference to other systems) |
| 9   | **High security**             | Difficult to tap without detection (no radiated energy to intercept)              |
| 10  | **No jamming possible**       | Immune to EMI/RFI-based jamming                                                   |
### 2.6.2 Physical/Environmental Adv
|     | Adv                                  |                                                                    |
| --- | ------------------------------------ | ------------------------------------------------------------------ |
| 11  | **Light weight and small size**      | Much lighter and thinner than copper cables of equivalent capacity |
| 12  | **Greater tensile strength**         | Stronger than copper of same diameter; bends easily                |
| 13  | **Higher resistance to environment** | Inert glass – no corrosion, no water damage                        |
| 14  | **Ruggedness**                       | Glass is inert, no corrosive effects                               |
| 15  | **No spark hazard**                  | Safe in explosive environments                                     |
### 2.6.3 Economic/Operational
|     | Advantage                                     | Explanation                                               |
| --- | --------------------------------------------- | --------------------------------------------------------- |
| 16  | **Cheap raw materials**                       | Silica (sand) is abundant                                 |
| 17  | **Long operation life**                       | Decades of reliable service                               |
| 18  | **Low transmission cost**                     | Lower cost per bit over long distances                    |
| 19  | **No ground/high-voltage protection needed**  | No conductive path                                        |
| 20  | **Low handling, shipping, installation cost** | Lightweight and flexible                                  |
| 21  | **Channel capacity can be upgraded**          | Future-proof; upgrade electronics without replacing fiber |
| 22  | **Conserves Earth's resources**               | Copper is limited; silica is abundant                     |
### 2.6.4 Disadv
|     | Disadv                                      |                                                                                 |
| --- | ------------------------------------------- | ------------------------------------------------------------------------------- |
| 1   | **High initial installation cost**          | Cables are expensive to install (though long-term cost is lower)                |
| 2   | **Repeaters required at intervals**         | Even with low loss, long distances need amplification (every 80-100 km)         |
| 3   | **Fragile**                                 | Can be broken if bent into loops < 1 cm diameter; needs protective coating      |
| 4   | **More protection required**                | Fiber cables need more armor/strength members than copper                       |
| 5   | **Difficult splicing/connection**           | Requires precise alignment and expensive equipment                              |
| 6   | **No mobile terminals**                     | Cable must be physically laid (not wireless)                                    |
| 7   | **Highly skilled staff required**           | Maintenance needs specialized training                                          |
| 8   | **Only point-to-point working**             | Not naturally a multi-point/broadcast medium (though PON networks address this) |
| 9   | **Precise and costly instruments required** | OTDR, fusion splicers, power meters are expensive                               |
### 2.6.5 Comparison with Radio/Microwave
|Aspect|Optical Fiber|Radio/Microwave|
|---|---|---|
|**Bandwidth**|Extremely high (THz)|Limited (MHz-GHz)|
|**Attenuation**|Very low (0.2 dB/km)|Higher (depends on distance, weather)|
|**EMI immunity**|Complete|Susceptible|
|**Security**|Very high (no radiation)|Low (signals can be intercepted)|
|**Installation**|Requires trenching/cable laying|Tower/antenna installation|
|**Mobility**|Fixed (cable)|Mobile|
|**Weather dependence**|None (underground/submarine)|High (rain, fog, ducting)|
|**Line of sight required?**|No (fiber bends)|Yes (for terrestrial)|
|**Cost for long distance**|Lower per bit|Higher per bit|
## 2.7 Types of Optical Fiber
Optical fibers are classified into two categories based on:
1. Number of Modes (Single-mode vs Multi-mode)
2. Refractive index profile (Step index vs graded index)
### 2.7.1 No. of Modees
![[Pasted image 20260426140045.png]]
#### 2.7.1.1 Single Mode Fiber (SMF)
|Parameter|Value|
|---|---|
|Core diameter|~5-10 μm (typically 8-10 μm)|
|Cladding diameter|~70-125 μm|
|Number of modes|Only 1 mode (fundamental mode)|
|Refractive index difference (Δn)|Very small|
|Light source|Laser diode (stable, uniform, focusable)|
|Bandwidth|Very high (double that of MMF)|
|Attenuation|Extremely low|
|Dispersion|No intermodal dispersion (only chromatic/waveguide)|
|Cost|More expensive than MMF|
|Applications|Long-distance, high-bandwidth (telecom backbone, submarine cables)|
#### 2.7.1.2 Multi Mode Fiber (MMF)
| Parameter                        | Value                                             |
| -------------------------------- | ------------------------------------------------- |
| Core diameter                    | 40-100 μm (typically 50, 62.5, or 100 μm)         |
| Cladding diameter                | 70-125 μm                                         |
| Number of modes                  | Many (hundreds to thousands)                      |
| Refractive index difference (Δn) | Larger than SMF                                   |
| Light source                     | LED (cheaper than laser)                          |
| Bandwidth                        | Lower than SMF                                    |
| Attenuation                      | Higher than SMF                                   |
| Dispersion                       | Significant modal dispersion (signal degradation) |
| Cost                             | Cheaper than SMF                                  |
| Applications                     | Short distance, LAN, data centers, CCTV           |
#### 2.7.1.3 Adv/Disadv
##### 2.7.1.3.1 Adv of Multi-mode over Single-mode
|Advantage|Explanation|
|---|---|
|Cheaper light source|Uses LEDs instead of expensive lasers|
|Easier coupling|Larger core diameter simplifies alignment|
|Lower connector cost|Less precision required|
|Suitable for short distances|LANs, data centers (< 2 km)|
##### 2.7.1.3.2 Disadv of Multi-mode over Single-Mode
|Disadvantage|Explanation|
|---|---|
|Higher attenuation|More signal loss per km|
|Lower bandwidth|Limited by modal dispersion|
|Shorter transmission distance|Typically < 2 km (vs. 100+ km for SMF)|
|Modal dispersion|Different modes travel at different speeds|
##### 2.7.1.3.3 Adv of Single-mode over Multi-mode
|Advantage|Explanation|
|---|---|
|Extremely low attenuation|0.2-0.4 dB/km|
|Very high bandwidth|No modal dispersion|
|Long transmission distances|100+ km without repeaters|
|Higher security|Harder to tap (single mode, small core)|
### 2.7.2 Refractive Index Profile
![[Pasted image 20260426140517.png | 500]]
![[Pasted image 20260426140616.png | 500]]
#### 2.7.2.1 Step Index Fiber
|Property|Step Index Fiber|
|---|---|
|Core refractive index|Uniform, constant|
|Cladding refractive index|Uniform, constant|
|Index change at boundary|Abrupt (step)|
|Core diameter (MMF)|50-200 μm|
|Core diameter (SMF)|~10 μm|
|Ray path|Zig-zag (meridional rays crossing fiber axis)|
|Attenuation|Higher for MMF, very low for SMF|
|Bandwidth|Lower|
|Mode types|Meridional rays only|
#### 2.7.2.2 Graded Index Fiber
| Property                  | Graded Index Fiber                                              |
| ------------------------- | --------------------------------------------------------------- |
| Core refractive index     | Varies parabolically (max at center, decreases toward cladding) |
| Cladding refractive index | Uniform, constant                                               |
| Index change              | Gradual (graded)                                                |
| Core diameter (MMF)       | ~50 μm                                                          |
| Ray path                  | Helical/spiral (skew rays, do not cross fiber axis)             |
| Attenuation               | Lower than step index MMF                                       |
| Bandwidth                 | Higher than step index MMF                                      |
| Mode types                | Skew rays (helical paths)                                       |
##### 2.7.2.2.1 Why graded index reduces modal dispersion
- Rays travelling near the center (shorter path) encounter higher refractive index
	- resulting in slower velocity
- Rays travelling farther from center (longer path) encounter lower refractive index
	- resulting in faster velocity
- Net result: all rays arrive at approximately the same time (self-focusing effect)
### 2.7.3 Summary
| Fiber Type                      | Core Dia. | Modes | Index Profile      | Ray Path              | Bandwidth   | Attenuation          | Typical Use              |
| ------------------------------- | --------- | ----- | ------------------ | --------------------- | ----------- | -------------------- | ------------------------ |
| **Single-mode Step Index**      | 5-10 μm   | 1     | Step               | Straight (single ray) | Very high   | Very low (0.2 dB/km) | Long haul, telecom       |
| **Multi-mode Step Index**       | 50-200 μm | Many  | Step               | Zig-zag (meridional)  | Low         | High                 | Short distance, low cost |
| **Multi-mode Graded Index**     | 50 μm     | Many  | Graded (parabolic) | Helical (skew)        | Medium-High | Medium               | LANs, data centers       |
| **Single-mode Dual-step Index** | Special   | 1     | Dual step          | Special               | Very high   | Very low             | Dispersion-shifted fiber |  
# 3 Light Propagation Characteristics
## 3.1 Basic Principles of Optics
**Law of Reflection**:
Angle of Incidence = Angle of Reflection

**Law of Refraction** (Snell's Law):
![[Pasted image 20260426141047.png | 500]]
$$\large
\dfrac{n_2}{n_1} = \dfrac{\sin(i)}{\sin(r)}
$$
**Refractive Index**
for a medium's n:
$$\large
n = \dfrac{c}{v}
$$
**Critical Angle**
- Angle of incidence at which the refracted ray travels along the interface ($\large r = 90\D$)
$$\large
\sin(\theta_c) = \dfrac{n_2}{n_1}
$$
![[Pasted image 20260426141432.png | 500]]
**Total Internal Reflection**:
Condition for TIR:
1. Light must travel from denser medium (higher $n_1$) to a rarer medium (lower $n_2$)
2. Angle of incidence must be greater than the critical angle: $\large i > \theta_c$

At TIR:
- $\large i = r$
- No light escapes the denser medium
- 100% reflection (ideally)

**In optical Fiber**:
- Core has n1
- Cladding has n2
- light launched at an angle > critical angle at core-cladding interface is trapped and propagates
## 3.2 Acceptance Angle
### 3.2.1 Concept
- Definition:
	- the maximum angle
	- from the fiber axis
	- at which the light can enter the fiber
	- and still propagate via TIR
- all light entering within the acceptance cone (half-angle $\large \theta_a$) will be guided.
- Light entering outside this cone will refract into the cladding and be lost.
- figure:
	- ![[Pasted image 20260426141839.png]]
### 3.2.2 Derivation
![[Pasted image 20260426142153.png | 500]]
From Snell's law at the air-core interface ($\large n_0 = 1$ for air):
$$\large
n_0 \sin(\theta_a) = n_1 \sin(\theta_1)
$$
At the core-cladding interface, for TIR to occur:
$$\large
\sin(\theta_2) = \dfrac{n_2}{n_1}
$$
Also, from geometry: $\large \theta_1 = 90\D - \theta_2$, so $\large \sin(\theta_1) = \cos(\theta_2)$ 
Therefore:
$$\large
\sin(\theta_1) = cos(\theta_2) = \sqrt{1-\sin^2(\theta_2)} = \sqrt{1- \left( \dfrac{n_2}{n_1} \right)^2 }
$$
Thus:
$$\large
\sin(\theta_a) = n_1 \sin(\theta_1) = n_1 \sqrt{1- \left( \dfrac{n_2}{n_1} \right)^2 } = \sqrt{n_1^2 - n_2^2}
$$
# 4 Numerical Aperture
## 4.1 Concept
- NA means
	- the light-gathering capacity
	- of an optical fiber
- defined as
	- the sine of the maximum acceptance angle
	- when the fiber is in air, $\large n_0 = 1$
- Derivation as above
## 4.2 NA and Relative Refractive Index Difference
The refractive index difference $\large \Delta$ is defined as:
$$\large
\Delta = \dfrac{n_1^2 - n_2^2}{2n_1^2} \approx \dfrac{n_1 - n_2}{n_1}
$$
## 4.3 Physical Interpretation of NA
|NA Value|Light Gathering Capacity|Typical Fiber|
|---|---|---|
|Low (0.1-0.2)|Small acceptance cone|Single-mode fiber|
|Medium (0.2-0.3)|Moderate|Multi-mode telecommunications fiber|
|High (0.3-0.5)|Large acceptance cone|Plastic optical fiber, short-distance fiber|
Main Points:
- Higher NA captures more light from source
- Higher NA also increases modal dispersion (in MMF)
- Trade-off: NA vs BW
## 4.4 Losses in Optical Fiber
Several Categories:
```
Losses in Optical Fiber
├── Absorption Loss
│   ├── Intrinsic Absorption (Material, Electron)
│   └── Extrinsic Absorption (Impurity, OH⁻ ions)
├── Scattering Loss
│   ├── Linear Scattering (Rayleigh, Mie)
│   └── Non-linear Scattering (Brillouin, Raman)
├── Dispersion Loss
│   ├── Intermodal (Modal) Dispersion
│   └── Intramodal Dispersion (Chromatic, Waveguide)
├── Bending Loss
│   ├── Macrobending Loss
│   └── Microbending Loss
├── Insertion Loss
├── Return Loss
├── Radiation Loss
└── Coupling Loss
```
### 4.4.1 Insertion Loss (Attenuation Loss)
- Definition:
	- The loss of optical energy
	- as it travels through fiber
- aka transmission loss
- Measurement:
	- units: dB/km
	- measured as difference between output power and input power
$$\large
\alpha = \dfrac{10}L \log_{10}\left( \dfrac{P_\text{in}}{P_\text{out}} \right)\ \text{ dB/km}
$$
	- where:
	- Pin = input signal power (incident power)
	- Pout = output signal power (transmitted power)
	- L = fiber length in km
- Typical values:
	- Single Mode Fiber: 0.2 - 0.4 dB/km
	- MMF: 1.4 db/km
### 4.4.2 Return Loss
- Definition:
	- The ratio of reflected power to incident power
	- light reflected back in fiber
- e.g., from connectors or splices
- Formula:
$$\large
RL\ (dB) = 10 \log_{10} \left( \dfrac{P_\text{reflected}}{P_\text{incident}} \right)
$$
- Other Specifications:
	- Percent reflected power
	- Standing Wave ratio
	- Reflection Coefficient
### 4.4.3 Absorption Loss
- Definition:
	- Dissipation of optical power
	- into heat
	- due to interaction of light
	- with fiber material
#### 4.4.3.1 Intrinsic Absorption
- Cause:
	- Due to fundamental properties of the fiber material itself (silica glass)
- Mechanism:
	- Vibration of silicon-oxygen (Si-O) bonds interacting with the EM field
- Location:
	- UV and IR regions (electronic absorption bands)
- Result:
	- Minimal absorption in pure material
	- cannot be eliminated, only minimized
- Types within intrinsinc
	- Material Absorption: Related to composition of fiber material
	- Electron Absorption: Photon excites electron to higher level
#### 4.4.3.2 Extrinsic Absorption (Impurity Absorption)
- Cause:
	- impurities introduced during fiber fabrication
- Major impurities:
	- Iron (Fe), Nickel (Ni), Chromium (Cr), Hydroxyl ions (OH- from water vapor)
- Significance:
	- Much more significant than intrinsic absorption
- Mitigation:
	- Modern fabrication reduces impurities below 1 part in $\large 10^{10}$
	- glass refining (vapor oxidation)
	- use dry fiber to reduce OH- ion concentration
### 4.4.4 Scattering Loss
- Definition:
	- Loss due to interaction of light
	- with density fluctuations, compositional variations, structural inhomogeneities and manufacturing defects
#### 4.4.4.1 Linear Scattering Losses
|Type|Cause|Wavelength Dependence|
|---|---|---|
|**Rayleigh Scattering**|Microscopic density fluctuations (frozen into glass during cooling)|$\propto 1/\lambda^4$ (dominant at shorter wavelengths)|
|**Mie Scattering**|Larger defects, inhomogeneities, diameter variations|$\propto 1/\lambda^2$|
#### 4.4.4.2 Non-linear Scattering Losses
|Type|Cause|Effect|
|---|---|---|
|**Stimulated Brillouin Scattering (SBS)**|Interaction with acoustic phonons|Backward scattering, limits input power|
|**Stimulated Raman Scattering (SRS)**|Interaction with optical phonons|Forward scattering, energy transfer to longer wavelengths|
### 4.4.5 Dispersion Loss
- Definition
	- The spreading of the optical signal
	- over time
	- as it travels along the fiber
	- causing pulse broadening and 
	- limiting bandwidth
#### 4.4.5.1 Intermodal Dispersion
|Property|Description|
|---|---|
|**Occurs in**|Multi-mode fiber only|
|**Cause**|Different modes take different path lengths → different arrival times|
|**Result**|Pulse broadening|
|**Mitigation**|Use graded index fiber or single-mode fiber|
For step index MMF: $\large \Delta T \propto \dfrac{n_1 L}{c} \left(\dfrac{n_1 - n_2}{n_2}\right)$
AKA **modal** dispersion
#### 4.4.5.2 Intramodal Dispersion
|Property|Description|
|---|---|
|**Occurs in**|Both single-mode and multi-mode fiber|
|**Cause**|Refractive index varies with wavelength (different colors travel at different speeds)|
|**Two components:**|1. Material dispersion (glass property)  <br>2. Waveguide dispersion (core-cladding structure)|
AKA **chromatic** dispersion
#### 4.4.5.3 Waveguide Dispersion
- Cause:
	- Different refractive indices of core and cladding
- Effect:
	- Some light travels in cladding as well as core
- Wavelength dependence:
	- Longer wavelengths propagate at higher velocities
- Result:
	- Optical pulse disperses/spreads over distance
### 4.4.6 Bending Loss
- Bending losses occur when the fiber is subjected to stress (curvature)
- Stronger bending (smaller radius) causes greater loss.
- Fiber makes a very good stress sensor for this reason.
#### 4.4.6.1 Key Characteristics
|Characteristic|Description|
|---|---|
|Higher loss for longer wavelength|Wavelength-dependent|
|Smaller loss for higher NA|Higher NA fibers are more bend-resistant|
|Critical bending radius exists|Below this radius, loss increases dramatically|
|Larger core-cladding index difference|Minimizes bend loss|
|Trench-index profile|Special profile to minimize bend loss|
#### 4.4.6.2 Macrobending Loss
- Definition:
	- Loss due to bends
	- large enough to be seen
	- with the naked eye
- curvature radius much larger than fiber diameter
- Characteristics:
	- Curvature radius > fiber diameter
	- occurs when fiber is physically bent past the critical angle
	- Common in multi-mode fiber cores
	- Certain in multi-mode fiber cores
	- Certain modes are not properly reflected -> loss to cladding
- Typical causes:
	- Cable installation bends
	- Coiling fiber on spools
	- Routing around corners
#### 4.4.6.3 Microbending Loss
- Definition:
	- Loss due to bends
	- too small to be seen
	- with the naked eye
- small scale fluctuations in fiber axis of curvature
- Characteristics
	- Arises when fibers are incorporated into cables
	- Caused by pressure applied to fiber surface
	- Results in deformation of core at core-cladding interface
	- Induced under surface pressure conditions (crushing, tension)
- Typical causes:
	- Cable manufacturing stress
	- thermal expansion mismatches
	- pressure from cable jacket
	- temperature variations
#### 4.4.6.4 Comparison
|Feature|Macrobending|Microbending|
|---|---|---|
|Bend visibility|Visible to naked eye|Invisible (microscopic)|
|Radius of curvature|> fiber diameter|Small-scale fluctuations|
|Primary cause|Physical bending, coiling|Pressure, cable stress, temperature|
|Location|Whole fiber bends|Core-cladding interface deformation|
|Loss mechanism|Modes not reflected|Light reflected at inconvenient angles|
### 4.4.7 Other Losses
|Loss Type|Definition|
|---|---|
|**Radiation Loss**|Loss due to leakage of light from fiber (e.g., from sharp bends or defects)|
|**Coupling Loss**|Loss at connections between fibers or between source and fiber (Fresnel reflection, misalignment)|
# 5 Light Source and Photo Detector

## 5.1 Light Sources (Optical Transmitters)
| Light Source                                       | Wavelength             | Bandwidth | Cost   | Used with         | Advantages                                       |
| -------------------------------------------------- | ---------------------- | --------- | ------ | ----------------- | ------------------------------------------------ |
| **LED (Light Emitting Diode)**                     | 850 nm (MMF)           | Lower     | Low    | Multi-mode fiber  | Cheap, long life, simple drive circuit           |
| **Laser Diode (LD)**                               | 1310 nm, 1550 nm (SMF) | Higher    | High   | Single-mode fiber | High power, narrow spectral width, high speed    |
| **VCSEL** (Vertical Cavity Surface Emitting Laser) | 850-1310 nm            | High      | Medium | Multi-mode/SM     | Surface emitting, easy to test, low cost for MMF |
The choice of light source depends on the fiber type, data rate, and distance.
**Operating wavelength bands:**
- **First window (850 nm):** Multi-mode fiber, LEDs
- **Second window (1310 nm):** Single-mode fiber, zero dispersion
- **Third window (1550 nm):** Single-mode fiber, minimum attenuation
## 5.2 Photo Detectors (Optical Receivers)
| Photo Detector                  | Type          | Sensitivity | Speed     | Application                                       |
| ------------------------------- | ------------- | ----------- | --------- | ------------------------------------------------- |
| **Photoresistor (LDR)**         | Passive       | Low         | Slow      | Low-cost light sensing (not for high-speed comms) |
| **Photo Diode** (PIN)           | Active        | Medium      | High      | Standard fiber optic receivers                    |
| **Avalanche Photo Diode (APD)** | Active (gain) | Very high   | Very high | Long-haul, low-light, high-sensitivity systems    |
| **Photo Transistor**            | Active        | Medium      | Medium    | Medium-speed applications                         |
| **Charge Coupled Device (CCD)** | Active        | High        | Medium    | Imaging, WDM monitoring                           |
## 5.3 Key Selection Criteria for Light Sources and Detectors
**For Light Source:**
- Wavelength matching to fiber low-loss window
- Output power sufficient for link length
- Spectral width (narrow for low dispersion)
- Modulation bandwidth (data rate)
- Coupling efficiency to fiber (NA matching)
- Cost and reliability
**For Photo Detector:**
- Responsivity (A/W) at operating wavelength
- Speed (bandwidth)
- Sensitivity (minimum detectable power)
- Dark current (noise)
- Active area size (coupling from fiber)