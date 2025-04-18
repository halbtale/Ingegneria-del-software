## grasp
### design patterns
- **Principi** di risoluzione di problemi 
- **NON** sono librerie
- Tiplogie
	- **GRASP** patterns
		- generici
	- **Gang of Four** (GoF)
		- soluzione di problemi specifiic nella programmazione
		- permettono di indiduare oggetti di **pure fabbrication** da implementare
### responsability driven design (rdd)
- Principio alla base: identificare **responsabilità** degli oggetti del sistema
	- **doing** responsability
		- nel fare una certa azione
	- **knowing** responsability
		- nel conoscere o derivare dati
- ==GRASP== = **General Responsability Assignment Software Patterns**
	- principi che definiscono a quali oggetti **assegnare** le **responsabilità**
### principio "creator"
#### problema
- Chi **crea** la classe **A**
#### pattern
- Si sceglie **classe B che aggrega o contiene A**
	- facendo riferimento a domain model
#### esempio
![[Pasted image 20250408090013.png|300]]
- Sale crea SaleLineItem

>[!warning] Attenzione
>In presenza di oggetti molto complessi, potrebbero essere necessari design patterns diversi (come factory)

### principio "information expert"
#### problema
- Come assegnare la **responsabilità**
	- quale **classe** deve implementare un determinato **metodo**
#### pattern
- Scelgo la classe che **contiene** l'**informazione** necessaria per implementare il metodo
	- classe è detta **information expert**
- Creazione **progressiva** di nuove classi nel **design model**
	- controllo se c'è classe valida per implementare determinato metodo
	- se non c'è
		- ne creo una nuova sulla base del **domain model**
		- aggiorno system **sequence diagram**
- Informazione **distribuita** tra più classi
	- collaborazione tra più **information expert**
#### esempio
![[Pasted image 20250408091521.png|500]]
![[Pasted image 20250408091534.png|400]]
>[!warning] Attenzione
>Se si gestisce **persistence** con database, tipicamente si accentra la funzione per salvataggio su database in un oggetto di boundary, in deroga a questo principio

<div style="page-break-after: always;"></div>

### principio "controller"
#### problema
- Quale oggetto del dominio deve ricevere le **richieste** dall'**esterno** del sottosistema
	- es. da UI
#### pattern
- **Controller** 
	- primo oggetto **responsabile** di gestire **operazioni** del **sistema** definite nell'interfaccia
	- non **gestisce** direttamente le richieste
		- **delega** il lavoro alle altre classi interne al sistema
- Tipologie di controller
	- **façade controller**
		- singolo oggetto che **rappresenta** l'intero **sottosistema**
		- contiene **tutti** i **metodi** dell'interfaccia
		- può essere un oggetto del dominio o uno generato ad hoc
		- non deve essere _bloaded_ (sovraccaricato con troppe funzioni)
	- **handlers**
		- creare un **handler** che **gestisce** ciascun **use case**
		- preferibile in sistemi complessi per evitare di avere un unico controller troppo grande
		- ```<UseCaseName>Handler```/```<UseCaseName>Coordinator```/```<UseCaseName>Session```
#### esempio
![[Pasted image 20250408093747.png|500]]

<div style="page-break-after: always;"></div>

### principio "low coupling"
#### problema
- Come minimizzare **impatto** dei cambiamenti
#### pattern
- **Couping** (dipendenza)
	- misura quanto le classi sono **connesse** tra loro
	- quanto il cambiamento di una certa classe **impatta** le altre classi
- Si assegna responsabilità classi in modo da **mimizzare** **coupling**
	- si fa in modo che una classe non abbia troppe dipendenze verso le altre
#### esempio
![[Pasted image 20250408094423.png|400]]
- Preferire far dipendere Payment da Sale invece che da Register
### principio "high cohesion"
#### problema
- Come rendere gli oggetti **focalizzati** e **gestibili**
#### pattern
- **Cohesion**
	- misura quanto **correlate** sono le **responsabilità** assegnate ad una classe
- Si assegna responsabilità classi in modo da mantenere **alta cohesion**
	- funzionalità classe altamente **correlate** e **focalizzate**
	- **NO** classe con responsabilità diverse slegate tra loro
>[!warning] Attenzione
>Ci sono casi in cui conviene avere oggetti non particolarmente coesi (nel caso di performance della comunicazione o persistence)

### principio "pure fabrication"
#### problema
- Tra le classi del **domain model** potrebbe non esserci una classe adatta a soddisfare una certa responsabilità
#### pattern
- Si costruiscono **nuove classi** artificiali non presenti nel **domain model** 
	- classi di **boundary**
		- controller in ingresso 
		- drivers chiamate in uscita (es. per chiamate verso DB)
	- classi di **controllo**
		- oggetti di utility che risolvono dei problemi standard
		- es. factory per creare oggetti simili
		- si sfruttano principi presenti nella **GoF**