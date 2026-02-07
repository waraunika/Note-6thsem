1. Introduction (4 hours)
    1.1. Analog and Digital communication sources, transmitters, transmission channels and receivers.
    1.2. Noise, distortion and interference. Fundamental limitations due to noise, distortion and interference.
    1.3 Types and reasons for modulation.

2. Representation of signals and systems in communication (2 hours)
    2.1. Review of signals (types, mathematical representation and applications)
    2.2. Linear/non-linear, time variant/invariant systems. Impulse response and transfer function of a system. Properties of LTI systems.
    2.3. Low pass and band pass signals and systems, bandwidth of the system, distortionless transmission, the Hilbert transform and its properties.
    2.4. Complex envelops rectangular (in-phase and quadrature components) and polar representation of band pass and limited signals.

3. Spectral Analysis (8 hours)
    3.1. Review of Fourier series and transform, energy and power, Parseval's theorem.
    3.2. Energy Density Spectrum, periodogram, power spectral density function (psdf).
    3.3. Power spectral density functions of harmonic signal and white noise.
    3.4. The autocorrelation (AC) function, relationship between psdf and AC function.

4. Amplitude Modulation and Demodulation (6 hours)
    4.1. Time domain expressions, frequency domain representation, modulation index, signal bandwidth of Amplitude Modulated (AM) signal.
    4.2. AM for a single tone message, carrier and side-band components, powers in carrier and side-band components, bandwidth and power efficiency
    4.3. Generation of Double Side Band- Full Carrier (DSB-FC) AM
    4.4. Double Side Band Suppressed Carrier AM (DSB-AM), time and frequency domain expressions, powers in side-bands, bandwidth and power efficiency
    4.5. Generation of DSB-AM (balanced, ring modulators)
    4.6. Single Side Band Modulation, time and frequency domain expressions, powers
    4.7. Generation of SSB (SSB filters and indirect method)
    4.8. Introduction to Vestigial Side Bands (VSB), Independent Side Bands (ISB) and Quadrature Amplitude Modulations (QAM)
    4.9. Demodulation of DSB-FC, DSB-SC and SSB using synchronous detection
    4.10. Square law and envelop detection of DSB-FC
    4.11. Demodulation of SSB using carrier reinsertion, carrier recovery circuits
    4.12. Phase Locked Loop (PLL), basic concept, definitions, equations and applications, demodulation of AM using PLL

5. Angle Modulation and Demodulation (4 hours)
    5.1. Basic definitions, time domain expressions for Frequency Modulation (FM) and Phase Modulation (FM)
    5.2. Time domain expression for single tone modulated FM signals, spectral representation, Bessel's function and properties
    5.3. Bandwidth of FM, Carson's rule, narrow and wideband FM
    5.4. Generation of FM (direct and Armstrong's methods)
    5.5. Demodulation of FM and PM signals, synchronous (PLL) and non-synchronous (limiter-discriminator) demodulation
    5.6. Stereo FM, spectral details, encoder and decoder
    5.7. Pre-emphasis and de-emphasis networks
    5.8. The super-heterodyne radio receivers for AM and FM

6. Source Coding and Sampling Theory (6 hours)
    6.1. Digital communication sources, transmitters, transmission channels and receivers.
    6.2. Source coding, coding efficiency, Shannon-Fano and Huffman codes, coding of continuous time signals (A/D conversion)
    6.3. Nyquist-Kotelnikov sampling theorem for strictly band-limited continuous time signals, time domain and frequency domain analysis, spectrum of sampled signal, reconstruction of sampled signal
    6.4. Ideal, flat-top and natural sampling processes, sampling of band-pass signals, sub-sampling theory
    6.5. Practical considerations: non-ideal sampling pulses (aperture effect), non-ideal reconstruction filter and time-limitness of the signal to be sampled (aliasing effects)

7. Pulse Modulation Systems (6 hours)
    7.1. Pulse Amplitude Modulation (PAM), generation, bandwidth requirements, spectrum, reconstruction methods
    7.2. Pulse position and pulse width modulations, generation, bandwidth requirements
    7.3. Pulse code modulation as the result of analog to digital conversion, uniform quantization.
    7.4. Quantization noise, signal to quantization noise ratio in uniform quantization.
    7.5. Non uniform quantization, improvement in average SQNR for signals with high crest factor, companding techniques (μ and A law companding).
    7.6. Data rate and bandwidth of a PCM signal.
    7.7. Differential PCM, encoder, decoder
    7.8. Delta Modulation, encoder, decoder, noises in DM, SQNR. Comparison between PCM and DM
    7.9. Parametric speech coding, vocoders

8. Baseband Data Communication Systems (4 hours)
    8.1. Introduction to information theory, measure of information, entropy, symbol rates and data (bit) rates.
    8.2. Shannon Hartley Channel capacity theorem. Implications of the theorem and theoretical limits.
    8.3. Electrical representation of binary data (line codes), Unipolar NRZ, bipolar NRZ, unipolar RZ, bipolar RZ, Manchester (split phase), differential (binary RZ-alternate mark inversion) codes, properties, comparisons
    8.4. Baseband data communication systems, Inter-symbol interference (ISI), pulse shaping (Nyquist, Raised-cosine) and bandwidth considerations
    8.5. Correlative coding techniques, duobinary and modified duobinary encoders
    8.6. M-ary signaling, comparison with binary signaling.
    8.7. The eye diagram.

9. Bandpass (modulated) data communication systems (6 hours)
    9.1. Binary digital modulations, ASK, FSK, PSK, DPSK, QPSK, GMPSK, implementation, properties and comparisons
    9.2. M-ary data communication systems, quadrature amplitude modulation systems, four phase PSK systems
    9.3. Demodulation of binary digital modulated signals (coherent and non-coherent)
    9.4. Modems and its applications.

10. Random signals and noise in communication systems (6 hours)
    10.1. Random variables and processes, random signals, statistical and time averaged moments, interpretation of time averaged moments of a random process stationary process, ergodic process, psdf and AC function of a ergodic random process
    10.2. White noise, thermal noise, band-limited white noise, the psdf and AC function of white noise
    10.3. Passage of wide-sense stationary random signals through a LTI
    10.4. Ideal low-pass and RC filtering of white noise, noise equivalent bandwidth of a filter
    10.5. Optimum detection of a pulse in additive white noise, the matched filter. Realization of matched filters (time co-relaters). The matched filter for a rectangular pulse, ideal LPF and RC filters as matched filter
    10.6. Performance limitation of baseband data communications due to noise, error probabilities in binary and M-ary baseband data communication.

11. Noise performance of band-pass (modulated) communication systems
    11.1. Effect of noise in envelop and synchronous demodulation of DSB-FC AM, expression for gain parameter (ratio of output SNR to input SNR), threshold effect in non-linear demodulation of AM
    11.2. Gain parameter for demodulations of DSB-SC and SSB using synchronous demodulators
    11.3. Effect of noise (gain parameter) for non-coherent (limiter discriminator-envelop detector) demodulation of FM, threshold effect in FM. Use of pre-emphasis and de-emphasis circuits in FM.
    11.4. Comparison of AM (DSB-FC, DSB-SC, SSB) and FM (Narrow and wide bands) in terms power efficiency, channel bandwidth and complexity.
    11.5. Noise performance of modulated digital systems. Error probabilities for ASK, FSK, PSK, DPSK with coherent and non-coherent demodulation.
    11.6. Comparison of modulated digital systems in terms of bandwidth efficiency, power efficiency and complexity.

12. Multiplexing (2 hours)
    12.1. Principle of frequency division multiplexing (FDM), FDM in telephony, hierarchy
    12.2. Frequency Division Multiple Access (FDMA) systems- SCPC, DAMA, SPADE etc.
    12.3. Filter and oscillator requirements in FDM.
    12.4. Time Division Multiplexing with PCM, data rate and bandwidth of a PCM signal.
    12.5. The T1 and E1 TDM PCM telephone hierarchy

13. Error control coding techniques (4 hours)
    13.1. Basic principles of error control coding, types, basic definitions (hamming weight, hamming distance, minimum weight), hamming distance and error control capabilities
    13.2. Linear block codes (systematic and non-systematic), generation, capabilities, syndrome calculation
    13.3. Binary cyclic codes (systematic and non-systematic), generation, capabilities, syndrome calculation.
    13.4. Convolutional codes, implementation, code tree, trellis and decoding algorithms.


## Signal and Systems
- Nagoor Kani (20-30 Marks)