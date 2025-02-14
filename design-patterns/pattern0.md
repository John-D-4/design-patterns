Decision Support Questions
  What frequencies, bandwidths, rates, modulations, wavelengths are defined by a given protocol?
  What protocols are normally found at a given frequency?
  What attribute measurements are required to identify a given protocol?

Wave Properties:
  Wavelength
  Frequency
  Amplitude
  Polarity
  
Signal properties:
  Rate
  Bandwidth
  Modulation
  Encoding

Protocol properties:
  Bands
  Rates
  Frequencies
  Frequency changes

Radio components:
  Antenna
  Tuner
  Detector
  Amplifier

Material entities:
  Radio components

Immaterial entities:
  radio waves

Qualities:
  Properties listed
  
Processes:
  Act of transmission
  Act of reception
  
Realizable entity:
  Signal

Immaterial entities:
  Space
  Carrier wave

Temporal Region:
  Propagation time

Generically dependent continuant:
  Also the properties, ugh

  
+---------------------key--------------------+
| arrows are "is_a" unless marked otherwise  |
+--------------------------------------------+
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
	O(Site):::BFO-->H(Immaterial<br> Entity):::BFO

 

 

	X(Fiat Object Part):::BFO-->G(Material<br> Entity):::BFO
	Y(Object<br> Aggregate):::BFO-->G(Material<br> Entity):::BFO
	Z(Object):::BFO-->G(Material<br> Entity):::BFO
	C(Occurrent):::BFO-->A(Entity):::BFO
	AA(Process):::BFO-->C(Occurrent):::BFO
	AB(Process<br> Boundary):::BFO-->C(Occurrent)
	AC(Temporal<br> Region):::BFO-->C(Occurrent)
	AD(Spatiotemporal<br> Region):::BFO-->C(Occurrent)
	AE(History):::BFO-->AA(Process):::BFO
	AF(Zero-Dimensional<br> Temporal Region):::BFO-->AC(Temporal<br> Region):::BFO
	AI(One-Dimensional<br> Temporal Region):::BFO-->AC(Temporal<br> Region):::BFO
	AG(Temporal<br> Instant):::BFO-->AF(Zero-Dimensional<br> Temporal Region):::BFO
	AH(Temporal<br> Interval):::BFO-->AI(One-Dimensional<br> Temporal Region):::BFO
	
	    EA[radio] --> G

    	EC[signal<br /> property] --> E
		

    	JA[rf transceiver] --> J(Realizable<br />Entity)

		JC[signal] --> J
    	
		UE(signal property) --> K(Relational<br /> Quality)
			UEA[frequency] --> UE
			UEB[power] --> UE
			UED[protocol] --> UE
			UEF[periodicity] --> UE
		


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
