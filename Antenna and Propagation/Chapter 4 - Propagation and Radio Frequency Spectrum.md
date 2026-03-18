# Ground or Surface Wave
## Concept
- also called surface wave propagation
- refers to radio waves that travel along the earth's surface, following its curvature.
- these waves glide over the ground and enable communication beyond the optical horizon through diffraction
-  Geometry of Ground Reflected Wave
  -  ![[Pasted image 20260318125233.png]]
## Technical Details
### Frequency Range and Bands
| Parameter             | Value                                                            |
| --------------------- | ---------------------------------------------------------------- |
| Range                 | 10 kHz to 2 MHz                                                  |
| Bands                 | VLF, LF, and MF                                                  |
| Upper Practical limit | ~ 3MHz (above this, attenuation makes ground wave impracticable) |
### Polarization
| Parameter | Value                                         |
| --------- | --------------------------------------------- |
| Linear    | primarily Vertical Polarization               |
| Why?      | vertical polarization minimizes ground losses |
### Key Parameters
| Parameter          | Typical Value             |
| ------------------ | ------------------------- |
| Transmission Power | Few kW to several MW      |
| Coverage Distance  | Upto ~ 1000 km            |
| Transmission Mode  | AM (Amplitude Modulation) |
| Antenna Pattern    | Omnidirectional           |
### Frequency vs Coverage
| Band            | Typical Coverage              |
| --------------- | ----------------------------- |
| LW              | ~ 1000 km                     |
| MF              | ~ 100 miles (160 km)          |
| 3 MHz and above | Impracticable for ground wave |
| 10 MHz          | 1-2 miles only                |
### Radio Horizon
- approximately 4/3 times the optical horizon
- beyond the horizon, direct and reflected waves are blocked by earth's curvature
- propagation continues via diffracted surface wave.
### Surface Conductivity (Best to worst)
- large body fresh water - very good
- ocean or sea water - good
- flat or hilly loamy soil - fair
- rocky terrain - poor
- desert - poor
- jungle - very poor
- dry sandy terrain, city centers - worst
### Propagation Method
- primary mechanism: diffraction
- wave produces a mirrored copy beneath the Earth's surface during propagation
### Attenuation Factors
- increases with frequency
	- Example 3 MHZ signal suffers 20 - 60 dB attenuation
- Dependent on
	- Earth's imperfection
	- Absorbed by ground
	- Reflection from surface
	- wave tilt creating horizontal component (reduces field strength)
## Other Details
### Wavelength Distribution
| Wave Type    | Wavelength Range |
| ------------ | ---------------- |
| Radio waves  | > 0.1 m          |
| Microwaves   | 0.1 - 1 mm       |
| Infrared     | 1 - 700 nm       |
| Visible rays | 700 - 400 nm     |
| UV rays      | 400 - 1 nm       |
| X-rays       | 1 nm - 1 pm      |
| Gamma rays   | < 1 pm           |
### Factors Affecting Reception
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
### Special Applications
- Marine communications: 10 - 110 kHz
- Time & frequency management:
	- 16 kHz (UK)
	- 17.8 kHz (US)
### Medium Wave Broadcasting
- frequency range: 535 kHz - 1625 kHz
- skip distance from sky wave can be minimized using ground wave
## Adv/Disadv
### Adv
- **Beyond horizon coverage**: Enables communication beyond the optical horizon
- **Weather independence**: Relatively unaffected by atmospheric conditions (unlike sky waves)
- **Global potential**: With sufficient power, can communicate between any two points
- **Reliable**: Provides consistent regional coverage
- **Minimizes skip distance**: Can fill in areas where sky wave coverage is problematic
### Disadv
- **High power requirements**: Needs relatively high transmission power
-  **Frequency limited**: Only practical at VLF, LF, and MF bands
- **Large antennas**: Lower frequencies require physically large antenna structures
- **Surface dependent**: Losses vary considerably with ground material
- **Frequency-dependent attenuation**: Attenuation increases with frequency
- **Limited range at higher frequencies**: Coverage reduces dramatically above 2 MHz
## Applications
### Primary
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
### Typical Use Case
- **LF band**: Long-range navigation, time signals
- **MF band**: AM broadcasting, maritime communications
- **VLF band**: Submarine communications, global navigation
### Coverage Optimization
- Better performance over wet/humid terrain than dry
- Coastal and maritime paths provide superior propagation
- Agricultural and marshy land preferred over urban/dry areas
- surface conductivity

- ground wave (EM wave) produces  mirrored copy of induced wave beneath the surface of earth during propagation
- the degree of attenuation is dependent upon a variety of factors
  - frequency of the radio signal
  - losses rise with increasing frequency
- so it is impracticable above 3 MHz (SW)
- typically a signal at 3.0 MHz will suffer an attenuation that may be in the region of 20 to 60 dB
- high power HF radio broadcast stations may only be audible for a few miles from Tx site via ground wave.
- salty sea water is the best, and rich agricultural or marshy land is also good.
- dry sandy terrain and city centers are by the worst.
- propagation method: diffraction
- rx power depends on
  - tx power
  - frequency
  - surface nature
  - season wise
- signal reception suffered by
  - D/E layer's absorption
  - Diurnally (Day time wise)
  - Seasonally
  - Annually (11 yrs sun cycle)
  - fading effect
- get attenuated
  - due to earth imperfection, absorption and reflection by earth surface
- attenuation increases with frequency
- by the tilt in the wave as it progresses along the curvature of earth
- due to this horizontal component of electric field get shorter, which reduces strength of electric field.
- Effect of Imperfect Earth
  - attenuation and attenuation distortion
  - free space loss
  - noise
  - atmospheric absorption
  - multipath
  - refraction
  - thermal noise
- advantages:
  - given enough power they can be used to communicate between any two points in the world.
  - they are relatively unaffected atmospheric conditions like sky waves.
- disadvantages:
  - requires relatively high transmission power
  - they are limited to very low, low and medium frequencies which require large antennas
  - losses on the ground vary considerably with surface material
  - ground wave get attenuated
  - due to earth imperfection, absorption and reflection by earth surface and attenuation increases with frequency.

# 4.2 Space wave
# 4.3 Direct and Ground Reflected wave
### 4.3.1 Duct Propagation
# 4.4 Ionospheric or Sky Wave
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
### Sky Wave
- Different layers in ionospheric affect sky wave
- D-layer exists only during Day time
- E-layer more active at Night time
- During day time F-Layer is divided into Two parts
- E-layer using day time @ 2400 km cover
- higher frequency needs greater ionization density for radio waves reflection back

### Ionospheric or Sky Wave
- more sunspots, the greater the ionizations
- thus 11 year's sunspot cycle is considered
- actually, signal is Refracted from ionized layers due to layer's refractive index change
- but it looks like the signal was reflected from ionosphere is a radio mirror, at virtual height of the ionosphere
- revolves around the refraction mechanism in the ionosphere

### Ionosphere
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

### Ionospheric or Sky Wave
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
# 4.5 Tropospheric Wave
# 4.6 Radio frequency spectrum and its propagation characteristics
