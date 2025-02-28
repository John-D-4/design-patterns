# pattern exercise: toaster
## Decision Support Questions
- what is a toaster?
- what is it meant to do?
- how does it do it?

## classes sketched out
### Properties (quality, determinable)
 - input
 - output
 - process

### Material entities:
 - toaster components

### Immaterial entities:
 - heat waves: not represented as not all toasters supply their own heat

### Qualities:
 - Toastiness 
  
### Processes:
 - Act of toasting
  
### Temporal Region:
 - toasting time



Notes


a toaster has the function of toasting bread: represented

the resulting bread's quality of toastiness is affected by the toasting process: represented

a toaster is a [140-BFO] object [024-BFO] with components such as bread grate and human interface: not represented

a toaster toasts successfully by exposing bread to heat without exposing the user to the same heat: not represented

  
```
+---------------------key--------------------+
| arrows are relations                       |
| relation is "is_a" unless marked otherwise |
| all nodes are classes unless purple        |
| purple nodes are particulars/instances     |
+--------------------------------------------+
```
 ```mermaid

graph RL

	B(Continuant)-->A(Entity):::BFO
	D(Specifically Dependent<br> Continuant)-->B(Continuant):::BFO
	E(Generically Dependent<br> Continuant):::BFO-->B(Continuant)
	F(Independent<br> Continuant)-->B(Continuant)
	G(Material Entity)-->F(Independent<br> Continuant):::BFO

	I(Quality):::BFO-->D(Specifically Dependent<br> Continuant):::BFO
	J(Realizable<br> Entity):::BFO-->D(Specifically Dependent<br> Continuant)


	M(Disposition):::BFO-->J(Realizable<br> Entity)
	N(Function):::BFO-->M(Disposition)


	Z(Object<br />024-BFO):::BFO-->G(Material<br> Entity):::BFO
	C(Occurrent):::BFO-->A(Entity):::BFO
	AA(Process):::BFO-->C(Occurrent):::BFO

	AC(Temporal<br> Region):::BFO-->C(Occurrent)

	
	AI(One-Dimensional<br> Temporal Region):::BFO-->AC(Temporal<br> Region<br />103-BFO):::BFO
	
	IA[toastiness] --> I
		
    	ZA[toaster] --> Z
	
	
	ZA -- has_function --> NA
		ZAA[my toaster]:::p -. instance_of .-> ZA
		ZA -- participates_in --> AAA
	ZB[bread] --> Z
		ZBA[my breakfast]:::p -. instance_of .-> ZB
	ZB -- has_realization --> IA
		AAA[act of<br />toasting] --> AA(Process)
		AAA -- occurs in --> AFA
		ZB -- participates_in --> AAA
		
	
	NA[to toast] --> N(Function)
	
		AFA[toasting<br />time] --> AI



subgraph Key
K00(BFO class):::BFO
K01[class]
K02[particular]:::p
end
    classDef BFO fill:#F5AD27,color:#060606
    classDef p fill:#771177,color:#AAAAAA

	
```
from https://github.com/BFO-ontology/BFO-2020
