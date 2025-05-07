# RF pattern draft, third pass
## Competency Questions
 - What transmission properties are defined by a given protocol?
 - What protocols are normally found at a given frequency?
 - What attribute measurements are required to identify a given protocol?
 - What hardware is required to detect a given protocol?
 - Where and when are detections or emitters sensed?


```
+-Key-0--------------------------------------+
| arrows are relations                       |
| relation is "is_a" unless marked otherwise |
| all nodes are classes unless purple        |
| purple nodes are particulars/instances     |
+--------------------------------------------+
```
```mermaid

graph RL
%%comments%%
	M(BFO:Disposition):::BFO-->J(BFO:Realizable<br> Entity):::BFO
	N(BFO:Function):::BFO-->M(BFO:Disposition):::BFO

		OA[transceiver<br />position] --> O(BFO:Site):::BFO
		OB[sensor<br />position] --> O 

	AH(BFO:Temporal<br> Interval):::BFO-->AI(BFO:One-Dimensional<br> Temporal Region):::BFO
		AFA[transmission<br />period] --> AI
		AFB[reception<br />period] --> AI
		AFC[propagation<br />time] --> AI
		
	NA[communication] --> N(BFO:Function):::BFO
	        
	AAC[act of<br />transmission] --> AA(BFO:Process):::BFO
	AAB[act of<br />reception] --> AA(BFO:Process):::BFO

    	YA[radio] --> Z(BFO:Object):::BFO
		YAA[antenna] -- part_of --> YA
		YAA -- participates_in --> AAC
		YAA -- participates_in --> AAB

		YAB[tuner] -- part_of --> YA
		YAB -- participates_in --> AAC
		YAB -- participates_in --> AAB

		YAC[detector] -- part_of --> YA
		YAC -- participates_in --> AAB

		YAD[amplifier] -- part_of --> YA
		YAD -- participates_in --> AAC
		
		YA -- concretizes --> JC
		JC[signal] --> J(BFO:Realizable<br> Entity):::BFO
    	
		UE[wave property] --> K(BFO:Relational<br /> Quality):::BFO
			UEA[wavelength] -- is_about --> UE
			UEB[frequency] -- is_about --> UE
			UED[amplitude] -- is_about --> UE
			UEF[polarity] -- is_about --> UE

		UF[signal property] --> K(BFO:Relational<br /> Quality):::BFO
			UFA[rate] -- is_about --> UF
			UFB[bandwidth] -- is_about --> UF
			UFD[modulation] -- is_about --> UF
			UFF[encoding] -- is_about --> UF

	PA[Bluetooth]:::p -- instance_of --> JC
		PA -- bearer_of --> UE
		PA -- bearer_of --> UF
	PB[LTE]:::p -- instance_of --> JC
		PB -- bearer_of --> UE
		PB -- bearer_of --> UF
	PC[LightBridge]:::p -- instance_of --> JC
		PC -- bearer_of --> UE
		PC -- bearer_of --> UF

subgraph Key-1
K00(BFO:class):::BFO -- is_a --> K01[local<br />class]
K02[particular<br />or instance]:::p -- instance_of --> K01
end
    classDef BFO fill:#F5AD27,color:#060606
    classDef p fill:#771177,color:#AAAAAA

```
from https://github.com/BFO-ontology/BFO-2020

## test cases
 - IEEE 802.11b. freq: 2.4GHz, 12-14 channels. rate: 1-11Mbit/s. bandwidth: 22MHz. modulation: Freq Hopping Spread Spectrum DBPSK, DQPSK, or QPSK. wavelength: 13cm
 - TBS XF. freq: 915 or 868MHz, 100 channels. rate: 50 or 150Hz. bandwidth: 5 or 2.5MHz. modulation: Chirp Spread Spectrum. wavelength: 32cm 
 - FT8. freq: HF, see table. rate: 5.86Hz. bandwidth: 47Hz. modulation: multiple frequency-shift keying (MSFK). wavelength: see table.

| λ (m) | f (MHz) |
|-------|:-------:|
| 160m  | 1.840   |
| 80m   | 3.573   |
| 40m   | 7.074   |
| 30m   | 10.136  |
| 20m   | 14.074  |
| 17m   | 18.100  |
| 15m   | 21.074  |
| 12m   | 24.915  |
| 10m   | 28.074  |
| 6m    | 50.313  |
| 2m    | 144.174 |

# Noted ambiguities:
 - not all protocols define freq, bandwidth, rate, modulation, and wavelength
 - wavelength, frequency, bandwidth, and rate are mathematically interdependent
 - sometimes one or more of these variables defines the protocol instead, probably
 - sometimes none of them serve to define. CW is defined purely by encoding only, and is just as usable in longitudinal waves as it is in transverse waves.
