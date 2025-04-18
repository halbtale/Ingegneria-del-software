## gOF
### introduzione
- Design patterns che permettono di individuare oggetti di **pure fabbrication**
- Soluzione a problemi **specifici**
- 3 tipologie
	- **creazionale**
		- creazione/configurazione di oggetti
	- **strutturale**
		- composizione di oggetti
	- **behavioural**
		- comportamenti di oggetti
### adapter
#### problema
- Presenza di interfacce **non compatibili**
- Si presenta tipicamente con librerie esterne o oggetti legacy
#### pattern
- Si implementa un **oggetto intermedio** che fa da bridge tra l'interfaccia desiderata e l'interfaccia reale
- Definizione dell'**interfaccia** desiderata come entità indipendente
	- uno (o più) **adapter** implementano l'interfaccia
- **Client** utilizza direttamente **interfaccia**
	- non ha bisogno di conoscere quale adapter la implementa
- ==Object adapter ==
	- l'adapter **contiene** una istanza della classe adaptee e **implementa** l'interfaccia
![[Pasted image 20250418084240.png|300]]
- ==Class adapter==
	- l'adapter è una **sottoclasse** della classe adaptee e **implementa** l'interfaccia
### singleton
#### problema
- Gestione delle classi che devono avere una **singola istanza**
#### pattern
- Variabile privata **statica** ```theInstance``` che contiene l'unica istanza della classe o null
- Metodo pubblico **statico** ```getInstance()```
	- se non già presente, crea istanza classe e aggiorna ```theInstance```
	- restituisce -```theInstance```
- Utilizzo **costruttore privato**
	- può essere invocato solo da ```getInstance()```, non dall'esterno
![[Pasted image 20250418084702.png|250]]
### factory
#### problema
- Istanziare una **sottoclasse** la cui scelta dipende da parametri runtime 
	- chi dovrebbe essere **responsabile** della **logica condizionale** per la scelta?
#### pattern
- ==Factory method/virtual constructor==
	- incapsula **logica condizionale** per la **scelta** di quale delle **sottoclassi** istanziare
	- es. metodo ```createProduct()```
		- chiama il costruttore per creare la specifica sottoclasse di ```Product```
	- implementato nella classe chiamante o in una apposita **factory class** (singleton)
![[Pasted image 20250418085437.png|300]]
- ==Abstract factory==
	- famiglia di factory relative ad un'unica interfaccia comune
	- la scelta della sottoclasse nel metodo ```createSomething```dipende dalla specifica factory istanziata
![[Pasted image 20250418085945.png|300]]
>[!info] Vantaggi della factory class
>- Incapsulamento logica creazione sottoclassi
>- Possibilità utilizzo strategie di gestione della memoria (recycling, caching)

### strategy
#### problema
- **Scelta** specifica **implementazione algoritmo** a **runtime**
	- es. chiamando ```sort()```, scelta runtime tra ```mergesort()```e ```insertionsort()```
#### pattern
- Promozione di un metodo ad una **strategia** 
	- definisce una **famiglia di algoritmi**, li **incapusla** e li **rende intercambiabili**
	- interfaccia relativa può avere diverse implementazioni
		- la specifica implementazione utilizzata è **trasparente** all'utilizzo della strategia
![[Pasted image 20250418090304.png|600]]
### composite
#### problema
- Necessità **uniformità di interfaccia** tra le classi **primitive** e le classi **composite** che contengono più classi primitive
- Esempi
	- calcolare il prezzo totale in un carrello dove ci sono prodotti e bundle di prodotti
		- unico for loop che somma prezzo ciascun elemento, indipendentemente che sia primitive (prodotto) o composite (bundle)
#### pattern
- Utilizzare una stessa **interfaccia comune** tra le classi primitive e le classi composite
	- le classi composite **delegano** le operazioni alle classi primitive che contengono
- Funziona anche strutture ad albero complesse con composite di composite
![[Pasted image 20250418091847.png|700]]
### facade
#### problema
- Fornire unico punto di accesso ad un **sottosistema** 
	- legato al principio GRASP **controller**
#### pattern
- **Façade controller**
	- fornisce **interfaccia unificata** ad alto livello del sottosistema 
		- rende sottosistema facile da utilizzare dall'esterno (incapsulamento)
	-  contiene tutti i **metodi** dell'interfaccia del sottosistema
		- **delega** le operazioni a classi interne al sottosistema
![[Pasted image 20250418092857.png|500]]
### observer
#### problema
- Oggetti che vogliono **conoscere** lo **stato** di un **oggetto** in **tempo reale**
- Esempi
	- sincronizzazione dati grafico excel con tabella
	- aggiornamento GUI sulla base dello stato dell'app
#### pattern
- **Subject**
	- oggetto che deve essere osservato
	- classe astratta che è estesa da **ConcreteSubject**
	- ```attach()```
		- associa un observer
	- ```detach()```
		- deassocia observer
	- ```notify()```
		- chiama ```update()```su tutti gli observer associati
	- ```getState()```
		- restituisce lo stato
	- ```setState()```
		- imposta lo stato e chiama ```notify()```
- **Observer**
	- oggetto che rimanne in attesa dei cambiamenti di stato del subject
	- classe astratta che è estesa da **ConcreteObserver**
	- ```update()```
		- chiama ```getState()```sul subject per ottenere lo stato aggiornato
- ==Pull-notification pattern==
	- l'observer effettua **pull** sul subject ad ogni **intervallo di tempo** fissato per ottenere stato aggiornato
- ==Push notification pattern==
	- Ogni volta che lo stato del subject cambia,**tutti** gli observer sono **notificati**
		- il subject chiama un metodo su tutti gli observer
		- gli observer chiamano ```getState()``` sul subject per ottenere nuovo stato
- ==Push-update notification pattern==
	- subject **notifica cambiamento** e **invia stato aggiornato** agli observer
### command
#### problema
- Le classi **invoker** che chiamano metodi su classi **receiver** hanno un grado di **coupling alto**
	- se cambio qualcosa sulla classe receiver, dovrò modificare anche la classe invoker
#### pattern
- **Command**
	- promozione della logica di chiamata di un metodo ad un **oggetto** a sè stante
		- **incapsula** tutta la **logica** e **informazioni** necessarie per chiamare un metodo sulla classe receiver
	- fornisce **interfaccia comune** a ```ConcreteCommand``` diversi
	- completa separazione tra **invoker** e **receiver**
		- invoker non ha bisogno di conoscere interfaccia specifica di receiver
		- se modifico classe receiver, devo modificare solo il relativo command, non l'invoker
 - Esempi:
	- una stanza potrebbe avere un comando per accendere le luci, uno per riprodurre musica
		- la stanza utilizza ciascun comando in modo generico con interfaccia ```Command```
- Permette decoupling tra boundary objects (UI) e controller
	- i boundary objects non chiamano direttamente il controller ma sfruttando i comandi 
```java
Button btn = new Button(new PlaceOrderCommand());
btn.click(); // Esegue il comando
```

![[Pasted image 20250418095427.png|500]]
>[!info] Vantaggi command pattern
>- Rendere azioni parametriche
>- Log command
>- Code di command
>- Operazione undo di un command

