HPF : Pre Emphasis Before FM
LPF : De Emphasis Before FM demod

Floor noise
To increase high freq
- Sm(t) -> SPF -> FM -> Sc(t)


Source of info/dest -> Source encoding/decoding -> Channel encoding/decoding -> ... -> (x)
			Signal		           S (t)                                S$_{Mne}$ (t)                                               Noise

Security
Noise
Manage Channel Capacity

# Channel Encoding
- Forouzan
- Uses
	- Correction
	- Detection
## Block Coding
- Data words :  Divide message into blocks each of k bits
- Add r redundant bits to each bloc to make length n = k + r
- Code words : Resulting n bit blocks

- E Detection
- E Correction
- Hamming Dist
- Min Hamming Dist

## Types of Errors
## Redundancy
## Detection Vs Correction
## Forward Error Correction Vs Retransmission
## Coding
## Modular Arithmetic







Systematic Cyclic Codes

g(c) = 1 + x + x^3
Message : 0101
C(7,4)
m = 4
q = 3
x^q = x^3


x^3 (m)
x^3 (x^2 + 1)
= x^5 + x^3

	             ___________
	g(x)         ) x^3 (m)

				_______________
	x^3 + x + 1  ) x^5 + x^3    ( x^2
				   x^5 + x^3 + x^2
				_______________
							 x^2

Generate the code word for given generator polynomial and message  = [0101]



	1 + x^1 + x^3
	g(x) = 1 . x^0 + 1 . x^1 + 0 . x^2 + 1 . x^3

		x^0-----x^1-----x^2-----x^3------
		  |       |               |       |
		  |       |               |       |
		  |--FF--(X)--FF---------(X)--FF-(X)


Discuss the procedure for generation of SCC

Draw and explain the SCC encoder circuit for C(15,9) CC with generator polynomial g(x) = 1 + x^3 + x^4 + x^5 + x^6 