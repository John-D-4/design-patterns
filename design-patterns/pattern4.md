# RF pattern draft, fourth pass
## Competency Question
 - What is required to locate BlueTooth protocol emissions?


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
