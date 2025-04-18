## modellazione di sistema
### introduzione
- Processo di **design** di un sistema software nel dettaglio
	- si può modellare sistema **nuovo** o **esistente**
- Obiettivo:
	- partire dai **requisiti** e identificare **oggetti** e **metodi**
	- seguire principi di **manutenibilità** e **scalabilità**
- Utilizzo **UML**
### classificazione viste di sistema
#### statica/dinamica
- ==Statica==
	- **logical view**
	- si usa **class diagram**
	- modellare **struttura**
- ==Dinamica==
	- **process view**
	- si usa **sequence diagram**
	- modellare **comportamento/interazioni**
#### esterna/interna
- ==Esterna==
	- vista dall'**esterno**/black box
- ==Interna==
	- esplorare **interno** sistema
### domain model
- Vista **statica**
- Costruire un **modello** del mondo in **classi concettuali**
- Modello ponte tra **use case** e **disegno di dettaglio**
- Processo identificazione classi concettuali a partire dagli use case
	- estrazione dei **nomi** $\rightarrow$ diventano **oggetti**
![[unnamed.png|350]]


>[!attention] Attenzione
>- **NO** metodi
>- **NO** classi software (es. database)
>- **NO** troppi dettagli (solo attributi principali)
#### attributi vs classi
- Un entità deve essere trattata come **oggetto** e non come **attributo** se potrebbe contenere degli attributi
#### description class
- Oggetto che contiene informazioni che descrive un altro oggetto
	- informazione **indipendente** dalle istanze dell'oggetto descritto
	- riduce **duplicazione** di informazioni condivise tra diverse istanze
![[Pasted image 20250401092843.png|300]]
#### relazioni
- Si specificano relazioni di **associazione** e etichette associate
#### sintassi uml
![[Pasted image 20250401093414.png|500]]
### external behavioural model
- Vista **dinamica**
- **Comportamento dinamico** sistema in risposta a **stimoli** esterni
- Tipologie di modellazione
	- ==data-driven modelling==
		- sistemi che **processano dati** in input per generare output
		- si utilizza **sequence diagram**
	- ==event-driven modelling==
		- tipico di sistemi **real-time**
		- **eventi** che portano transizioni da uno **stato** all'altro
		- si utilizza **state diagram**
#### data-driven modelling
- **Dettaglia** gli **use-case** e rappresenta **interazione**
	- attraverso **system sequence diagraméé
	- mostra **funzioni di interfaccia** che il sistema deve **esporre**
	- **NO** rappresentazione di attori che non interagiscono direttamente con il sistema
- Scelta **nomi** delle frecce
	- technology independent

![[RP7B3OCm38RlcS8Bi007Td63MomIXnhJYkqRY2AWxJ7-7v_i65iWG8iElIK5lyoM8gcRK8qzJoYso-Vt3MLqrTbqMMv1wRdGRF1c6th5jylJfkcggmMMcTJ0e_RVMJvhMsuVlv1xD2hJaD9KfAFHA_KanXWg_QTOfiLElgCS_41-F4ia_oaOqv9t_Y5S4CLKejjrQZ_c9GBUEB2jRXDg3Fsu4xzW3tuHn2IqNhgIt5aZcABC-PyuoGS0.png|200]]
### cross-subsystem behavioural model
- Flusso di **interazione** tra i vari **sottosistemi**
	- sfrutta **sequence diagram**
	- lista sottosistemi proveniente da viste architetturali
- **Sottosistema** all'interno del sistema
	-  **subsystem interface object**
		- lista pubblica di operazioni offerte da un sottosistema
		- interfaccia definita nel design mentre API definito nell'implementazione
	- **coerenza**
		- le entità nel sottosistema eseguono task simili e sono strettamente correlate
	- NO **coupling**
		- dipendenze esterne minime
		- una modifica in un sottosistema non deve influire altri sottosistemi
	- rappresentato come **package** in UML
- **Relazioni** tra sottosistemi
	- **dipendenza compiler-time** (_depends on_)
		- più moduli/librerie inglobati in un unico eseguibile
	- **dipendenza run-time** (_call_)
		- locale (comunicazione tra processi)
		- remota (attraverso **middleware** come REST)

![[Pasted image 20250403171829.png|500]]
![[Pasted image 20250403172743.png|500]]
### internal behavioural model
- **Dettaglio** di un **singolo sottosistema**
	- interazione tra **classi** del sottosistema
	- rappresentato attraverso **sequence diagram**
- Si basa sul **cross-subsystem behavioural model** per le funzioni di ingresso
- Si basa sul **domain model** per gli oggetti presenti nel sottosistema
#### tipologie di classi
- ==Boundary objects==
	- astrazione interfacce
	- permettono **interazione** con esterno sottosistema
		- gestiscono chiamate da sottosistema a esterno
- ==Entity objects==
	- oggetti derivati dal **domain model**
- ==Control objects==
	- oggetti extra di utilità derivati da **design patterns**
		- offrono soluzioni **standardizzate**

<div style="page-break-after: always;"></div>

### design class model
- **Struttura** del codice orientato ad oggetti all'interno del singolo **sottosistema**
	- rappresentato attraverso **class diagram**
- Si basa su classi rappresentate nell'**internal behavioural model**
- Presenta corrispondenza diretta con il **codice**
![[Pasted image 20250405155809.png|400]]

<div style="page-break-after: always;"></div>
- **Metodi della classe**
	- derivano dall'**internal sequence diagram**
	- implementa il metodo chi **riceve** la chiamata 
- **Variabili della classe**
	- derivano da **attributi** del domain model
![[Pasted image 20250408085247.png|500]]