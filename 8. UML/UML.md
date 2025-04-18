## uml
### obiettivo
- **Documentare** e **comunicare** architettura sistema sofware
### classificazione
- ==Structure Diagram==
	- evidenzia **struttura statica** del sistema
		- componenti, classi e relazione tra esse
	- **logical/Implementation** viewpoint
- ==Behaviour Diagram==
	- evidenzia **comportamento dinamico** del sistema
		- funzionamento runtime, modifiche allo stato, use case, ecc
	- **activity** viewpoint
![[Pasted image 20250325091759.png|500]]
### use case diagrams
- Primo diagramma che si crea a partire dei requisiti
- Rappresentazione di **use case/user stories**
	- sistema come collezione di funzioni utilizzabili
#### attore
- **Interagisce** con funzionalità sistema software
- **Associazione**
	- comunicazione tra attore e use case a cui partecipa
	- rappresentato con linea continua
![[Pasted image 20250325092226.png|200]]
#### sistema
- Racchiuso in un **riquadro**
- Contiene diversi use case
- **Generalizzazione**
	- relazione tra use case generale e specifico
	- rappresentato con freccia a punta triangolare verso parent use case
- ```<<include>>```
	- una parte di use case può essere condivisa e inclusa da più use case
	- freccia con linea tratteggiata
- ```<<extend>>
	- si può estendere un use case base 
	- freccia con linea tratteggiata
![[Pasted image 20250325092537.png|300]]
### component diagram
- Mostra **organizzazione componenti** in sistema software e **dipendenze** tra essi
#### component
- Modulo software legato ad una specifica **funzionalità** del sistema
- Rappresentazione ad **alto livello**
	- può contenere insieme di classi e interfacce
	- possono esserci componenti e sottocomponenti
	- nasconde dettagli implementativi
![[Pasted image 20250323094110.png|150]]
#### interfacce
- Descrivono gruppo di **operazioni** utilizzate o fornite da un determinato **componente**
- **Interfaccia fornita** 
![[Pasted image 20250323094741.png|200]]
- **Interfaccia richiesta** 
![[Pasted image 20250323094757.png|200]]
#### porta
- Connessione tra **interno** e **esterno** di un componente
- Specifica che interfaccia non è fornita/richiesta dal componente direttamente ma da uno dei **sottocomponenti**
![[Pasted image 20250323094943.png|100]]
#### interconnessione tra componenti
- Si mettono in evidenza relazioni tra componenti
![[Pasted image 20250323095055.png|500]]

### class diagram
- Utilizzato per il **design** di dettaglio nella programmazione ad oggetti
- Identifica **entità** e **relazioni** tra esse
#### classe
- **Nome**
	- identifica la classe
	- unico tag obbligatorio
- **Attributi**
	- proprietà della classe che descrivono l'oggetto
	- visibilità
		- ```+```: public
		- ```#```: protected
		- ```-```: private
		- ```/```: derivato (da altri attributi già presenti)
- **Operazioni**
	- metodi
	- può essere specificata la firma (con eventuali parametri e tipi)
![[Pasted image 20250325093944.png|100]]
![[Pasted image 20250325094259.png|100]]
#### relazione di generalizzazione
- Connette una **sottoclasse** a una **superclasse**
- Mostra meccanismo ereditarietà
![[Pasted image 20250325094455.png|100]]
#### relazione di associazione
- **Relazione** tra due classi
	- una classe **contiene** oggetti di un'altra classe
	- se unidirezionale, può essere esplicitata con una freccia
- Si può esplicitare **nome** assocazione
- Può essere **ricorsiva**
- Può essere esplicitata la **molteplicità** 
![[Pasted image 20250325095428.png|200]]
![[Pasted image 20250325095257.png|200]]
- **Classi associative**
	- contiene informazioni relative a associazione tra due classi
![[Pasted image 20250326112844.png|300]]
- ==Aggregazione==
	- classi configurate insieme per creare un oggetto più complesso
![[Pasted image 20250325095840.png|300]]
- ==Composizione==
	- tipo di aggregazione in cui, se la composizione viene cancellata, anche le classi collegate ad essa vengono cancellate
	- espressa attraverso classi interne
		- quella interna non può esiste al di fuori di quella esterna
![[Pasted image 20250325095913.png|400]]
#### relazione di dipendenza
- Relazione **semantica** tra più elementi
- Una classe **utilizza** oggetti di un'altra classe come **tipo** di oggetto in un **metodo**
![[Pasted image 20250326113336.png|400]]
#### interfaccia
- **Insieme di operazioni** che l'oggetto può eseguire
	- nasconde dettagli implementativi
- **NO** stato/attributi
- Può essere rappresentata anche con un **cerchio**
![[Pasted image 20250326114338.png|150]]
#### relazione di realizzazione dell'interfaccia
- Conette **interfaccia** alla classe della relativa **implementazione**
![[Pasted image 20250326114511.png|150]]
#### classe parametrica
- Parametro definisce specifica caratteristica della classe
![[Pasted image 20250326114621.png|150]]
#### enumerazione
- Contiene nome enumerazine e lista costanti denominate
![[Pasted image 20250326115012.png|120]]
#### eccezione
- Rappresentata come classe con aggiunta di ```<<exception>>``` stereotype
![[Pasted image 20250326115107.png|150]]
### package diagram
- Più componenti vengono inscatolati in un **package**
- Possono esserci package di package e generalizzazioni/dipendenze tra package
![[Pasted image 20250327165655.png|300]]
### activity diagram
- Mostra **flusso di attività** che avvengono nel sistema software
	- modello di tipo **dinamico**
- **Attività**: rettangoli con angoli smussati
- **Flussi**: frecce
- **Condizioni**: rombi
	- da essi dipartono più flussi in base a risultato if/else
- **Concorrenza**: linee in grassetto orizzontale
	- **fork**: da cui dipartono più flussi
	- **join**: in cui si ricongiungono più flussi
		- va specificata tra parentesi quadre condizione sincronizzazione
![[Pasted image 20250326113828.png|300]]
![[Pasted image 20250323095404.png|300]]

### sequence diagram
-  Mostra come due o più **oggetti** **interagiscono** nel **tempo**
#### oggetti
- Rappresentati lungo asse **X**
- **Object lifeline**
	- linea tratteggiata che rappresenta **esistenza** oggetto lungo un periodo di tempo
![[Pasted image 20250323095912.png|50]]
#### messaggi
- Rappresentati lungo asse **Y** all'incrementare del **tempo** (verso il basso)
- **Frecce** orizzontali con possibili condizioni in base a cui il **messaggio** viene inviato
	- quelle senza messaggio indicano **return**
![[Pasted image 20250323100205.png|100]]
- Se è significativa la **durata** di trasmissione del messaggio, può essere esplicitata tramite linee diagonali
![[Pasted image 20250326114023.png|150]]
#### ripetizione
- **Asterisco** indica che messaggio viene **ripetuto**
![[Pasted image 20250323100537.png|100]]
#### chiamate sync/async
- Chiamata **sync**
	- rettangolo bianco nel chiamante prolungato
	- chiamante rimane in **attesa** della risposta
![[Pasted image 20250323100408.png|100]]
- Chiamata **async**
	- chiamante **NON** rimane in attesa della risposta
![[Pasted image 20250323100433.png|100]]
#### attività interna
![[Pasted image 20250323100708.png|150]]
#### creazione/distruzione oggetti
![[Pasted image 20250323100755.png|300]]
#### numerazione
- Esplicita **ordinamento** invio messaggi
	- se due messaggi hanno lo stesso numero sono concorrenti
![[Pasted image 20250323100907.png|200]]
#### costrutti aggiuntivi
- Possono indicare
	- ```alt```: alternative flusso esecuzione
	- ```opt```: messaggio opzionale
	- ```loop```: loop di messaggi
![[Pasted image 20250323101044.png|300]]
### state diagram
- Rappresenta **transizioni di stato** del sistema
- Usato principalmente per sistemi **realtime** o **embedded**
#### esempio: semaforo
![[Pasted image 20250327173821.png|300]]
#### esempio: microonde
![[Pasted image 20250327174135.png|300]]