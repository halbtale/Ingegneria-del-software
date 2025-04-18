## tecniche di sviluppo agile (xp)
### user stories
- I requisiti del progetto sono espressi tramite **user stories** o **scenarios**
	- semplici descrizioni di una **funzionalità** dal punto di vista dell'utente
	- scritti su delle card
	- il cliente sceglie quali **stories** vuole includere nel prossimo rilascio
		- in base a priorità e tempistiche
- Team di sviluppo traduce le stories in **tasks** per l'implementazione
#### definizione di una user story
- Dimensione corretta di una **user story**
	- tempo di realizzazione stimato: da 1 giorno a 2 settimane
	- stima fatta tramite **planning poker**
- **Split**: divisione da stories generali a specifiche
	- con attività di **ricerca**
		- trovare una soluzione migliore per rendere più semplice implementazione
	- riconoscendo **fasi** story
		- ogni fase diventa una story **secondaria**
	- in base ai **dati**
		- una story per gestire dati corretti e una per gestire edge case
	- in base a **interfacce**
		- dividerle in base al tipo di browser, sistema operativo, hardware, ecc
- Schema per scrivere la **user story**
	- As a
	- I want
	- So that
- Criterio ==INVEST== sulla qualità di una **story**
	- **independent**
	- **negotiable**
	- **valuable**
	- **estimable**
	- **small**
	- **testable**
- **Definition of done (DoD)**
	- specifica gli **acceptance criteria**
		- requisiti che deve soddisfare la funzionalità per essere ritenuta completata

![[Pasted image 20250302150511.png|600]]
![[Pasted image 20250302152751.png|400]]
### refactoring
- Si richiede **refactoring continuo** del codice quando possibile
- Importante mantenere il codice ben **strutturato** e **scalabile**
	- migliora leggibilità
	- più flessibile al cambiamento
- **Code refactoring**
	- migliorare struttura interna e design del codice senza cambiarne il funzionamento
	- migliorare mantenibilità e leggibilità
- **Architectural refactoring**
	- si ricostruisce intera architettura del software
	- modifiche su larga scala

<div style="page-break-after: always;"></div>

### test-first Development
- Scrittura di **test automatici** (es. JUnit) **PRIMA** dell'implementazione stessa
- Affinché una task sia completa, tutti i test devono avere successo
	- permette di evitare di introdurre nuovi **bug**
- Ruolo del **cliente** nel processo di testing
	- descrive i **test** necessari a soddisfare i requisiti di accettazione della story
- Svantaggi di questo approccio
	- i programmatori tendono a scrivere **test incompleti** per potersi focalizzare sul codice
	- è **difficile** scrivere test incrementalmente
### pair programming
- Sviluppatori lavorano **a coppie** 
	- utilizzano lo stesso computer
	- coppie cambiano dinamicamente durante il processo di sviluppo
- Permette un **processo di review informale**
	- modalità di correzione reciprica
	- migliora **comprensione** del codice da parte del team
- Spesso si ottiene **più efficienza** rispetto a due programmatori che lavorano indipendentemente
- Conviene nelle task **first-of-a-kind**
- **Costa** sempre **di più**