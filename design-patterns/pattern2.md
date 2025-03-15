# RF pattern draft
## Competency Questions
 - What frequencies, bandwidths, rates, modulations, wavelengths are defined by a given protocol?
 - What protocols are normally found at a given frequency?
 - What attribute measurements are required to identify a given protocol?

## classes sketched out
### Wave Properties (quality, determinable)
 - Wavelength
 - Frequency
 - Amplitude
 - Polarity
  
### Signal properties:
 - Rate
 - Bandwidth
 - Modulation
 - Encoding

### Protocol properties:
 - Bands
 - Rates
 - Frequencies
 - Frequency changes

### Radio components:
 - Antenna
 - Tuner
 - Detector
 - Amplifier

### Material entities:
 - Radio components

### Immaterial entities:
 - radio waves

### Qualities:
 - Properties listed
  
### Processes:
 - Act of transmission
 - Act of reception
  
### Realizable entity:
 - Signal

### Immaterial entities?:
 - Space
 - Carrier wave

### Temporal Region:
 - Propagation time
 - Reception
 - Transmission

# Noted ambiguities:
 - not all protocols define freq, bandwidth, rate, modulation, and wavelength
 - wavelength, frequency, bandwidth, and rate are mathematically interdependent
 - sometimes one or more of these variables defines the protocol instead, probably
 - sometimes none of them serve to define. CW is defined purely by encoding only, and is just as usable in longitudinal waves as it is in transverse waves.
```
+---------------------key-0------------------+
| arrows are relations                       |
| relation is "is_a" unless marked otherwise |
| all nodes are classes unless purple        |
| purple nodes are particulars/instances     |
+--------------------------------------------+
```
 ```mermaid

graph RL
	
	M(BFO:Disposition):::BFO-->J(BFO:Realizable<br> Entity):::BFO
	N(BFO:Function):::BFO-->M(BFO:Disposition):::BFO

	AH(BFO:Temporal<br> Interval):::BFO-->AI(BFO:One-Dimensional<br> Temporal Region):::BFO

    	EC[signal<br /> property] --> E(BFO:Generically <br />Dependent Continuant):::BFO
		
	NA[communication] --> N(BFO:Function):::BFO
	        
		AFA[transmission<br />period] --> AI
		AFB[reception<br />period] --> AI
    		AFC[propagation<br />time] --> AI

    	YA[radio] --> Z(BFO:Object):::BFO
		YAA[antenna] -- part_of --> YA
		YAA -- participates_in --> AAC
		YAA -- participates_in --> AAB

		YAB[tuner] -- part_of --> YA
		YAB -- participates_in --> AAC
		YAB -- participates_in --> AAB

		YAC[detector] -- part_of --> YA
		YAA -- participates_in --> AAC

		YAD[amplifier] -- part_of --> YA
		YAA -- participates_in --> AAB
		
YA -- concretizes --> JC
		JC[signal] --> J(BFO:Realizable<br> Entity):::BFO
    	
		UE(wave property) --> K(BFO:Relational<br /> Quality):::BFO
			UEA[wavelength] -- is_about --> UE
			UEB[frequency] -- is_about --> UE
			UED[amplitude] -- is_about --> UE
			UEF[polarity] -- is_about --> UE
	UF(signal property) --> K(BFO:Relational<br /> Quality):::BFO
			UFA[rate] -- is_about --> UF
			UFB[bandwidth] -- is_about --> UF
			UFD[modulation] -- is_about --> UF
			UFF[encoding] -- is_about --> UF

			AAC[act of<br />transmission] --> AA(BFO:Process):::BFO
			AAB[act of<br />reception] --> AA(Process)

	
	



subgraph Key 1
K00(BFO class):::BFO
K01[class]
K02[particular]:::p
end
    classDef BFO fill:#F5AD27,color:#060606
    classDef p fill:#771177,color:#AAAAAA

```
from https://github.com/BFO-ontology/BFO-2020
