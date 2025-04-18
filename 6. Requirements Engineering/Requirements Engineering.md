## requirements engineering
### introduzione
- **Disciplina ingegneristica** che si occupa della **descrizione** in termini di **servizi** e **vincoli** di un sistema software
### user e system requirements
- ==User requirement==
	- descrizione ad **alto livello** di cosa deve fare il sistema
	- comprensibile dal committente
- ==System requirement==
	- traduzione degli user requirements in modo **dettagliato**
		- descrizione **quantitativa**
		- legata alla soluzione **implementativa**
	- parte del **contratto** e della **documentazione**
	- definito in modo preciso
		- **verificabile**
		- completo e consistente
		- no spazio ad interpretazione da parte degli sviluppatori
![[Pasted image 20250311084913.png|400]]
### system skateholders
- Individuo, gruppo, organizzazione direttamente coinvolto nel sistema software
- Categorie:
	- utenti del sistema
	- manager del sistema
	- committente del sistema
	- esterni
### requisiti nel modello agile
- **NO** requirements document
- Descritti nelle **user stories**
### requisiti funzionali
- **Funzionalità** del sistema software
### requisiti non funzionali
- Attributi di **qualità**
- Possono influenzare l'intera **architettura**
	- es. se un sistema deve essere attivo 24/7, serve un'infrastruttura che lo permetta
- Può implicare anche aggiunta di **requisiti funzionali**
	- es. sicurezza -> funzionalità di autentificazione
- Può avere una parte di **user requirements** e **system requirements**
	- per dettagliare i requisiti si utilizzano **metriche**
![[Pasted image 20250311092103.png|600]]
#### classificazione
- ==Product requirements==
	- **usability** (usabilità)
		- es. garantire accesso a ipovedenti
	- **efficiency** (efficienza)
		- legata anche al system engineering (requisiti HW)
		- es. tempo di risposta
	- **dependability** (affidabilità)
		- legata anche al system engineering (requisiti HW)
		- es. percentuale uptime, failure rare
	- **security** (sicurezza)
		- es. crittografia dati
- ==Organizational requirements==
	- **environmental** (di ambiente)
		- es. eseguibile su Windows
	- **operational** (di gestione del sistema)
		- es. funzionalità di backup
	- **development** (di sviluppo)
		- es. programmato in Java
- ==External requirements==
	- **regulatory** (di regolamento)
		- legata a regolamenti di settore
		- implementazione di un certo standard
	- **legislative** (di legislazione)
		- deriva da una legge
		- può comportare implementazioni di tipo funzionale
		- es. GDPR sul trattamento dei dati
	- **ethical** (etici)
		- rispettare condizioni etiche
		- es. bias su AI

![[Pasted image 20250311091453.png|350]]
### processi di requirement engineering
- Adottato principalmente da sviluppo **pianificato**
- Processo **iterativo** (ciclo di raffinamento)
#### elicitation
- Processo di **estrazione** di **informazioni** dal cliente
- **Problematiche** da affrontare
	- il committente di solito non sa esattamente che soluzione adottare al proprio problema
	- ci possono essere più stakeholders con opinioni diversi
	- i requisiti possono cambiare nell'analisi
	- committente potrebbe usare linguaggio tecnico non facilmente comprensibile
- Si produce una **descrizione del sistema** discorsiva di alto livello
#### specification
- Si struttura **informazione grezza** raccolta nella fase di elicitation
- Si scrivono i **system requirements** a partire dagli **user requirements**
- Modalità di scrittura dei requisiti di sistema:
	- **linguaggio naturale**
		- ambiguità e non chiaro
	- **linguaggio naturale strutturato**
		- forma più tabellare sulla base di template 
		- diviso in sezioni strutturate
	- **notazione grafica**
- ==Use cases==
	- atomi funzionali da implementare nel sistema
	- vengono tradotti in tabelle dettagliate (a differenza delle user stories)
- Produzione **software requirements document**
	- include sia **user requirements** e **system requirements**
	- contiene la descrizione del problema, non come implementarlo
	- standard di documentazione:
		- **IEEE Std 803-1998**
		- **VOLERE**
		- **Enterprise-specific standards**

<div style="page-break-after: always;"></div>

#### validation
- Verificare che le specifiche siano complete, realistiche e verificabili
	- importante interfacciarsi con il cliente
- È possibile produrre un **prototype**
- È possibile dei generare **test case**
#### change
- Presenza di **metodologie standard** per tenere traccia dei cambiamenti dei requisiti
![[Pasted image 20250311095657.png|600]]