## architettura del software
### introduzione
- Processo di **identificazione delle macrocomponenti** di un sistema software
	- requisiti raggruppati in macroblocchi
- Si produce un **modello architetturale
	- descrizione sistema software ad alto livello**
	- presentato attraverso diverse **viste architetturali**
	- identificazione di **pattern architetturali** 
	- permette presentazione architettura agli skateholders
- **Application Architect**
	- figura che si occupa della definizione dell'architettura software
![[Pasted image 20250318090305.png|400]]
#### dall'architettura all'implementazione
![[Pasted image 20250318090703.png|400]]
- **Product Conception**
	- definire macrocomponenti e pattern architetturali
- **Detailed Design**
	- definizione dei vari componenti nel dettaglio con UML
- **Framework selection and development**
	- scelta di un framework di sviluppo per l'applicazione
- **Component and connector implementation**
	- implementazione del codice
### architectural views
- **Diagrammi** che mostrano funzionamento ad alto livello del sistema software
	- macrocomponenti e relazioni tra essi
- **Kruchten**: 4+1 view architecture
![[Pasted image 20250318091141.png|400]]
#### logical viewpoint
- Legata ai **requisiti funzionali**
- Identificazione di **sottosistemi** e **relazioni** tra di essi a livello **logico**
	- non c'è un mapping one-to-one verso moduli software
- Comprensibile anche all'**utente finale**
- Si utilizzano rappresentazioni grafiche custom 
![[Pasted image 20250318091509.png|400]]
#### implementation viewpoint
- **Organizzazione** dei **moduli software** che verranno implementativi
- Ogni componente è self-contained
- Si utilizzano UML implementation diagrams
![[Pasted image 20250318091902.png|400]]

>[!attention] Attenzione
>- Non bisogna fornire indicazioni su implementazione specifica (es. tipo di DB)
#### process viewpoint
- Mostra **interazioni** tra sottosistemi e **transizione tra stati**
- Si utilizzano UML activity/sequence diagrams
![[Pasted image 20250318092143.png|600]]

#### deployment viewpoint
- Mostra come le componenti software sono mappate all'hardware fisico
	- layer = livello logico
	- tier = livello fisico
- Si utilizzano UML deployment diagrams
![[Pasted image 20250318092309.png|500]]
#### scenario viewpoint
- Rappresentazione funzionamento alla base degli **use case** principali
- Mette assieme elementi tratti dalle altre 4 viste
- Si usano UML use csase diagrams
![[Screenshot 2025-03-18 alle 09.25.56.png|300]]
### architectural patterns
- Esistono dei **pattern** standardizzati che garantiscono **qualità** del codice
	- conoscenza condivisa maturata negli anni dello sviluppo software
#### layered pattern
- Architettura realizzata **a livelli**
	- ogni livello è un'**astrazione** di un particolare requisito logico del sistema
		- **componenti** in un certo layer si occupano solo del tipo di **logica** del layer
	- isolati: modifiche in un layer non devono influenzare gli altri layer
- Comunicazione tra layer
	- comunicano tramite **interfacce** ben definite
	- **layer chiuso**
		- solo con layer sottostante
	- **layer aperto**
		- permette di essere bypassato dal layer superiore
- Categorie di layer
	- **Presentation Layer**
		- interfaccia sistema software
		- disaccopiata dalla logica
		- la presentazione cambia e può avere target diversi (es. web, mobile)
	- **Business Layer**
		- logica del programma
		- stabile
		- funzioni con evoluzioni poco frequenti
	- **Persistence Layer**
		- come le informazioni rimangono stabili nel tempo
		- es: informazioni di sessione
	- **Database Layer**
		- informazioni salvate in un database

![[Pasted image 20250318093258.png|400]]

>[!tip] Osservazione
>Spesso si parte da questo modello e poi si aggiungono altri pattern più specifici
#### client-server pattern
- Due layer:
	- **server**
		- gestisce logica
	- **client** 
		- gestisce interfaccia utente
		- può essercene più di uno
- Esempi di utilizzo
	- applicazioni con backend remoto
![[Pasted image 20250318094311.png|100]]
#### peer2peer pattern
- Serie di **nodi** che agiscono sia da **client** che da **server**
- Esempi di utilizzo
	- applicazioni di file sharing
	- protocolli di multimedia
	- blockchains
![[Pasted image 20250318184644.png|300]]
#### model-view-controller pattern
- Applicazione divisa in 3 parti
	- **view**
		- mostra interfaccia utente
	- **controller**
		- cattura azioni utente e cambia stato del model
	- **model**
		- mantiene stato informativo
- Esempi di utilizzo:
	- applicazioni web
![[Pasted image 20250318094434.png|300]]
#### pipe-filter pattern
- Utilizzati per strutturare sistemi che **processano** **flusso** ben definito di **dati**
- Data scorre in **pipes**
	- ad ogni step di processazione è presente un **filter** component
- Esempi di utilizzo
	- processo di compilazione 
![[Pasted image 20250318094852.png|500]]
#### event-bus pattern
- Sistema che raccoglie **coda di eventi**
- **Publisher**
	- produce nuovi eventi
- **Subscriber**
	- consuma eventi
	- può sottoscriversi a determinati tipi di eventi
- Esempi di utilizzo:
	- applicazioni che devono lavorare in modo **asincrono**
![[Pasted image 20250318095201.png|400]]
### web patterns
- Pattern specifici per il mondo web
#### evoluzione dei pattern
1. Prima fase
	- applicazioni monolitiche centralizzate
2. Seconda fase
	- standardizzata comunicazione tra applicazioni
3. Terza fase
	- all'interno della stessa applicazione vi sono più servizi che comunicano tra loro
### service oriented architecture (soa)
- Sistema software che presenta componenti chiamanti **servizi**, ciascuno per ogni funzionalità
- ==Web services==
	- **componenti software** che offrono **servizi**
	- accessibili attraverso HTTP in un formato standard
- **Comunicazione** tra servizi 
	- **service bus**
		- servizio cenetralizzato che instrada le richieste al servizio appropriato
	- utilizzo **interfaccia standard** 
		- es. REST e protocollo JSON
- **Vantaggi**:
	- interoperabilità, accoppiamento debole, astrazione, granularità
- **Svantaggi**:
	- tendenza a sviluppare interdipendenze tra servizi, scalabilità limitata, single point of failure (service bus)

<div style="page-break-after: always;"></div>

### microservices
- Pattern architetturale **prevalente** in applicazioni web
- Microservizi come **piccole** unità funzionali **indipendenti**
	- interfaccia offerta tramite **REST**
	- ciascuno può essere implementato con un **linguaggio** di programmazione diverso
	- **robusti**
		- se un microservizio fallisce, non fallisce l'intero sistema
- Funzionamento **stateless**
	- non vengono mantenuti dati sulla sessione
	- sfrutta cookies: mantiene stato lato utente
- Strato di **persistenza condiviso** (database)
	- permette sincronizzazione tra microservizi
- **Continuos delivery**
	- **pipeline** di produzione indipendente in ciascun microservizio
		- team dedicati per ciascun microservizio 
![[Pasted image 20250320171455.png|500]]

<div style="page-break-after: always;"></div>

#### api Gateway
- **NO** orchestratore (differenza con web services)
- Utilizzato da UI o da sistemi esterni
- Punto **unico** di coordinazione dei vari microservizi
- Costituito da 3 livelli
	- **core layer**
		- controllo di accesso (autentificazionene)
		- caching
		- conversione di protocollo
	- **management layer**
		- gestione traffico
		- definisce quante connessioni può accettare il sistema
	- **monitoring**
		- log delle chiamate all'API
		- metriche sistema

![[Pasted image 20250323084634.png|300]]


 
<div style="page-break-after: always;"></div>
- 

#### scalabilità
- **X: cloning**:
	- più istanze dello stesso microservizio
	- load balancer si occupa della gestione del carico per ciascuna istanza
- **Y: functional decomposition**:
	- divisione applicazione in microservizi indipendenti
- **Z: splitting**
	- partizionamento di chi è servito da varie istanze
	- es. utenti da A a H microservizio 1, da I a Z microservizio 2

![[Pasted image 20250320171618.png|300]]
![[Pasted image 20250320172041.png|400]]

<div style="page-break-after: always;"></div>
- 

#### granularità
- **Dimensione** microservizi
	- **NO** troppo grandi
		- tende a monolitico
	- **NO** troppo piccoli
		- tende a SOAP
		- richiederebbe comunicazione infraservizi per processare richiesta e orchestratore
- Evitare **servite-to-service** communication
	- comunicazione solo attraverso database
	- consentita violazione DRY (don't repeat yourself)
		- implementazione business logic simile in microservizi diversi
		- per mantenere microservizi indipendenti
- Struttura **layered**
	- posso avere più livelli di microservizi
	- dipendenze tra layer diversi

![[Pasted image 20250320173007.png|400]]

>[!fail] Svantaggi
>- Maggiore overhead rispetto a un monolithic
>- Non si usa se serve un orchestratore o non si può avere operazioni transazionali