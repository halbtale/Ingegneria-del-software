## processi software
### definizione di processo software
- Insieme di attività strutturato necessario per sviluppare un sistema software
![[Pasted image 20250301092116.png|400]]
### processi lineari o iterativi
#### processo lineare
- Si eseguono le 4 macroattività in **ordine** in una **singola iterazione**
	- tutte le fasi sono indipendenti
	- ogni fase inizia dopo il rilascio del deliverable della fase precedente
- Modello **a cascata**
![[Pasted image 20250227165033.png|400]]
- Diagramma di **GANTT**
	- puntini gialli: rilascio di deliverable dopo ogni parte
![[Pasted image 20250227165608.png|400]]
#### processo iterativo
- Software rilasciato a **più iterazioni**
	- ad ogni versione vengono aggiunte funzionalità
- Le 4 macroattività vengono ripetute ciclicamente
### modello pianificato o agile
#### modello pianificato
- Processo univocamente **determinato** all'**inizio**
- Pianificazione completa
	- date di rilascio
	- costi 
	- tutte le funzionalità
- Vantaggi
	- utilizzato per **sviluppo di grandi sistemi ingegneristici**
		- tipicamente le specifiche sono definitive all'inizio del progetto
	- utilizzato per progetti **pubbliche amministrazioni**
		- il contratto deve avere costo, funzionalità e data rilascio specifiche
		- necessario per questioni burocratiche
- Svantaggi:
	- **poco flessibile**
		- difficoltà di permettere cambiamenti durante il processo
		- se cambia qualcosa durante lo sviluppo devo rivedere specifiche iniziali
#### modello agile
- **NO** pianificazione completa iniziale (principale caratteristica)
- Pianificazione incrementale
	- ==outline==
		- versione minima di requisiti e design
	- ==cicli brevi==
		- rilasci parziali tra ogni macroattività
		- es. una funzionalità alla volta
- Vantaggi:
	- **flessibilità**
		- posso facilmente permettere cambiamenti durante lo sviluppo
	- **feedback**
		- posso ottenere feedback dopo ogni funzionalità rilasciata
	- **rilascio rapido**
		- posso rilasciare un MVP e poi estenderlo in seguito
- Svantaggi:
	- **meno controllo dei costi**
		- processo non determinato all'inizio
		- ci possono essere imprevisti
	- **struttura sistema tende a degradare**
		- cambiamenti durante lo sviluppo rischiano di far degradare la struttura del sistema
		- potrebbe diventare meno mantenibile e più instabile
![[Pasted image 20250227165823.png|400]]
### riusabilità del software
- Lo sviluppo di software consiste solo nello sviluppo di un sottile layer superiore
	- si basa su **librerie** e codice scritto da altri
- Vantaggi:
	- **riduzione costo** produzione
	- **rilascio** più **rapido**
- Svantaggi:
	- **meno controllo** su tutte le parti del sistema
	- rischio di **vulnerabilità**
- Nella definizione di specifiche c'è una fase di **software discovery** e **evalutation**
	- si cerca se alcune funzioni esistono già e non serve re-implementarle da zero
	- nel design ci saranno dei black box
		- blocchi funzionali forniti dall'esterno
![[Pasted image 20250227171330.png]]
#### tipi di riusabilità software
- ==Stand-alone==
	- **applicazioni** che incorporo direttamente nel mio sistema
		- **COTS** (Commercial Off-the-Shelf component)
	- es. Apache
- ==Collections of objects==
	- **librerie** che utilizzo per sviluppare un mio software
	- devono essere integrate in una applicazione
	- es. React
- ==SaaS==
	- utilizzo servizi di vendor esterni attraverso chiamate ad un **API** remoto
	- paradigma **microservizi**
### macroattività
#### requirements
- ==Elicitation==
	- estrarre informazione grezza dal committente
	- produce **system descriptions**
		- documento di descrizione discorsivo
- ==Specification==
	- esiste la figura di "requirement engineer"
	- strutturare informazione grezza in modo articolato e tecnico
	- iterativo: è spesso necessario chiedere ulteriori informazioni al committente
	- produce **requirements specification**
- ==Validation==
	- si validano le specifiche
	- produce **requirements document**
![[Pasted image 20250301092709.png|250]]

<div style="page-break-after: always;"></div>

#### design & implementation
- Implementazione delle specifiche strutturate
- ==Design==
	- **Architectural design**
		- identificare macrocomponenti e relazioni tra essi
	- **Database design**
		- definire come i dati vengono rappresentati nel DB
	- **Interface design**
		- definire le interfacce delle classi
	- **Component design**
		- ricerca/definizione di componenti riutilizzabili
	- produce **design documents**
- ==Implementation==
	- programmazione software e configurazione di moduli esterni
	- importante seguire **design patterns**
	- produce **codice**
![[Pasted image 20250301092834.png|300]]

#### verificatioN & validation
- Necessario per dimostrare che il software **soddisfa** i **requisiti**
- ==Development testing==
	- **unit testing**
		- singolo metodo
	- **component testing**
		- classe
	- **system testing**
		- intero sistema
- ==Release testing==
	- team di persone che si occupa di testare il sistema software
- ==User testing==
	- il cliente testa il software e controlla se funziona correttamente
- **Modello a V**:
![[Pasted image 20250301093502.png|400]]
- In alcuni casi si scrivono dei **test plan** nelle fasi precedenti
![[Pasted image 20250301093604.png|400]]
#### maintenance
- Fase successiva al **lancio** in **produzione** del software
- **Gestione** di **cambiamenti** del sistema
- Nel mondo agile la **demarcazione** tra sviluppo e maintenance è molto **sottile**
	- continuazione dello stesso modello ciclico di sviluppo adottato in precedenza
![[Pasted image 20250301093713.png|350]]
### cambiamenti nei requisiti nel project time
- Inevitabili in larghi progetti
#### anticipazione dei cambiamenti
- Fare il possibile per anticipare i cambiamenti
- Costruire prima un **prototipo** del progetto
	- fatto in un modo non industriale
		- non andrà in produzione
	- es. interfaccia con Figma
	- minimale (non tutte le funzionalità, non tutti gli edge case)
#### tolleranza ai cambiamenti
- **Sviluppo incrementale**
	- sviluppo e consegno un pezzo alla volta
	- di solito utilizzato con modello agile
- **Rilascio incrementale**
	- prima MVP, poi versioni più complete
	- permette di avere feedback degli utenti
	- non funziona in progetti di **replacement** (sostituire un progetto con uno nuovo)
### project maturity approach
- Fase di **analisi** dei processi utilizzati e **ottimizzazione** degli stessi 
- Obiettivo: **incrementare qualità** e **ridurre** **costi**/**tempo** sviluppo
- ==Maturity approach==
	- più i processi sono maturi e ottimizzati, più si è in grado di produrre software di qualità in modo prevedibile e efficiente
#### attività necessarie
- ==Process measurement==
	- raccogliere metriche legate al processo di sviluppo
	- dati quantitativi
		- **tempo** per completare le attività
		- **risorse** necessarie per le varie attività
		- **numero** di **occorrenze** di un particolare evento
- ==Process analysis==
	- analisi delle metriche per trovare punti deboli processo e possibili miglioramenti
- ==Process change==
	- modifica del processo con le ottimizzazioni trovate
![[Pasted image 20250301094553.png|200]]

<div style="page-break-after: always;"></div>

#### livelli di maturità dei processi software - sei
- **Initial**
	- processo non controllato, caotico
- **Repeatable**
	- iniziale definizione e utilizzo di processi
	- risultati possono essere ripetuti
- **Defined**
	- processi ben definiti e applicati
- **Managed**
	- applicate strategie di controllo qualità
	- raccolta metriche su processi utilizzati
- **Optimizing**
	- utilizzo di strategie per l'ottimizzazione dei processi