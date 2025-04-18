## gestione di progetti agile (scrum)
### schema di sintesi
![[Pasted image 20250306172649.png|600]]
![[Pasted image 20250306164634.png|600]]
### ruoli
- Presenza di **3** ruoli
#### produttore
- **Committente** (o delegato) è **presente** con una figura che lavora quotidianamente con il team
- Compito:
	- identifica funzionalità e **requisiti** prodotto
	- collabora nella scrittura delle **user stories**
	- responsabile del **ROI**
	- definisce date di rilascio e stories incluse nelle **release**
	- **accetta/rifiuta** deliverable
#### development team
- **Team di sviluppo**: programmatori, tester, designer, ecc.
- Membri lavorano su un progetto full-time (con eccezioni)
- Team si auto-gestisce
- Dimensione ottimale empirica: **7** persone
	- se ci sono troppe persone, non si coordinano bene
	- se ci sono troppe poche persone, i tempi sono maggiori
#### scrum Master
- **Responsabile** della gestione del progetto
	- simile al project manager
- Compito:
	- facilita il team negli aspetti **gestionali/operativi** (es. organizza daily meeting)
	- **monitora** sviluppo del progetto
	- **risolve** elementi bloccanti nello sviluppo
	- si **interfaccia** con i clienti
### eventi
- **5 eventi**
#### sprint
- **Ciclo** nel quale si produce un deliverable
	- mediamente dura 2 settimane
- Finestra di tempo blindata
	- non sono permessi cambiamenti durante uno sprint
#### sprint planning
- **Pianificazione** all'inizio dello sprint
- ==Sprint prioritization==
	- si produce riassunto sintetico dell'**obiettivo** dello sprint
	- si ottiene **sprint goal**
- ==Sprint planning==
	- si **selezionano** le stories da completare dal **product backlog**
	- si traducono user stories in **task**
	- si stimano gli story points per ogni task
	- si ottiene **sprint backlog**
![[Pasted image 20250306170758.png|400]]
#### daily scrum
- **Riunione informale** per scambiare informazioni nel development team
	- punto di **sincronizzazione**
	- si descrivono **progressi** di ciascuno e eventuali **problemi** insorti
- Durata: 15 minuti
- Detto anche stand-up meeting
#### sprint review
- Ispezione del **deliverable** prodotto alla fine dello sprint
- Si fanno **demo** di ciò che viene realizzato
	- deliverable non contiene solo pezzi di codice, ma **funzionalità** effettive
- Partecipano tutti
#### sprint retrospective
- Breve riunione successiva allo Sprint Review
- **Introspezione** del development team
	- si analizza cosa è andato **bene** o **male** nello **sprint**

<div style="page-break-after: always;"></div>

### artefatti
- **3** artefatti
#### product backlog item (pbi)
- Lista di **elementi** che bisogna sviluppare 
	- può contenere
		- **user stories**
		- **attività di supporto** (es. attività di ricerca, refactoring, exception handling)
	- **atomici** e ben definiti
	- ciascuno ha una **stima** delle **story** **points**
- Responsabilità del **produttore**
#### sprint backlog
- **User stories** selezionate per lo sprint corrente
	- suddivise in task
	- ogni storia deve portare un valore aggiunto al prodotto
- Responsabilità del **development team**
	- tutti i membri possono modificare lo sprint backlog
	- ogni task è scelta volontariamente dallo sviluppatore, mai assegnata dall'alto
#### product increment
- Insieme dei **PBI** che sono nello stato **DONE**
- Deve essere **production ready**
	- gestione eccezioni, casi particolari, ecc.
### fasi dello scrum
- **Pianificazione iniziale** del progetto
	- obiettivi e design generali
- **Serie** di **sprint**
	- sviluppo incrementale del software
- **Chiusura** del progetto
	- completamento di eventuale documentazione aggiuntiva per futuro mantenimento
### software utilizzati per gestione dello scrum
- **Trello**
- **Jira**
### monitoraggio
- Gestito dallo **scrum master**
- **Velocity** del team
	- numero di **stories points** che è in grado di rilasciare in uno sprint
- Si misura la differenza tra _expected_ e _actual_ stories points completati
	- serve per individuare criticità e risolverle
- Attraverso **diagrammi**
	- nella durata complessiva del progetto o all'interno del singolo sprint
![[Pasted image 20250306173204.png|600]]
![[Pasted image 20250306173409.png|600]]

>[!info] Osservazione
>- **BurnDown** utilizzato tipicamente all'interno di un singolo sprint (requisiti fissi)
>- **BurnUp** utilizzata tipicamente all'interno del progetto complessivo (requisiti variabili)

<div style="page-break-after: always;"></div>

### scalabilità metodoligia agile
- Di solito la metodologia AGILE si usa solo per progetti **medio**-**piccoli** sviluppati **da zero**
- Progetti di grandi dimensioni presentano **diversi sistemi** e **diversi team** di sviluppo
	- difficile applicare **AGILE**
#### scrum distribuito
- Metodologia per gestire **grandi progetti**
- Suddivisione del progetto in tanti **sottoprogetti** da assegnare a diversi team 
- Ciascun team lavora **autonomamente**
	- uno **scrum master** per ogni team
	- riunioni tra i diversi **scrum master** (daily scrum of scrums)
![[Pasted image 20250306174116.png|500]]
