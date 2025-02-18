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

### Generically dependent continuant:
 - Also the properties, ugh... time to try out more specific relation types

  
```
+---------------------key--------------------+
| arrows are "is_a" unless marked otherwise  |
+--------------------------------------------+
```
 ```mermaid

graph RL
	B(Continuant)-->A(Entity):::BFO
	D(Specifically Dependent<br> Continuant)-->B(Continuant):::BFO
	E(Generically Dependent<br> Continuant):::BFO-->B(Continuant)
	F(Independent<br> Continuant)-->B(Continuant)
	G(Material Entity)-->F(Independent<br> Continuant):::BFO
	H(Immaterial<br> Entity)-->F(Independent<br> Continuant)
	I(Quality)-->D(Specifically Dependent<br> Continuant):::BFO
	J(Realizable<br> Entity):::BFO-->D(Specifically Dependent<br> Continuant)
	K(Relational<br> Quality):::BFO-->I(Quality):::BFO

	M(Disposition):::BFO-->J(Realizable<br> Entity)
	N(Function):::BFO-->M(Disposition)

	X(Fiat Object Part):::BFO-->G(Material<br> Entity):::BFO
	Y(Object<br> Aggregate):::BFO-->G(Material<br> Entity):::BFO
	Z(Object):::BFO-->G(Material<br> Entity):::BFO
	C(Occurrent):::BFO-->A(Entity):::BFO
	AA(Process):::BFO-->C(Occurrent):::BFO
	AB(Process<br> Boundary):::BFO-->C(Occurrent)
	AC(Temporal<br> Region):::BFO-->C(Occurrent)
	AD(Spatiotemporal<br> Region):::BFO-->C(Occurrent)
	AF(Zero-Dimensional<br> Temporal Region):::BFO-->AC(Temporal<br> Region):::BFO
	AI(One-Dimensional<br> Temporal Region):::BFO-->AC(Temporal<br> Region):::BFO
	AG(Temporal<br> Instant):::BFO-->AF(Zero-Dimensional<br> Temporal Region):::BFO
	AH(Temporal<br> Interval):::BFO-->AI(One-Dimensional<br> Temporal Region):::BFO

    	EC[signal<br /> property] --> E
		

    	YA[radio] --> Y
		YAA[antenna] -- part_of --> YA
		YAB[tuner] -- part_of --> YA
		YAC[detector] -- part_of --> YA
		YAD[amplifier] -- part_of --> YA
		

		JC[signal] --> J
    	
		UE(wave property) --> K(Relational<br /> Quality)
			UEA[wavelength] -- is_about --> UE
			UEB[frequency] -- is_about --> UE
			UED[amplitude] -- is_about --> UE
			UEF[polarity] -- is_about --> UE
	UF(signal property) --> K(Relational<br /> Quality)
			UFA[rate] -- is_about --> UF
			UFB[bandwidth] -- is_about --> UF
			UFD[modulation] -- is_about --> UF
			UFF[encoding] -- is_about --> UF

			AAC[act of<br />transmission] --> AA(Process)
			AAB[act of<br />reception] --> AA(Process)

	
	
	NA[communication] --> N(Function)
	        
		AFA[transmission<br />period] --> AI
		AFB[reception<br />period] --> AI
    AFC[propagation<br />time] --> AI


    classDef BFO fill:#F5AD27,color:#060606
```
from https://github.com/BFO-ontology/BFO-2020

i am trapped in property graph hell
