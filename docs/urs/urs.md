**Versione : 1.0**

**Autore**  
Matteo Bonino

**REVISIONE N.1**


| Version    | Date        | Authors      | Notes        |
| ----------- | ----------- | ----------- | ----------- |
| 1.0 | 29/09/22 | Matteo Bonino | - |

# Tabella dei contenuti

1. [Introduzione](#p1)
	1. [Obbiettivi del documento](#sp1.1)
	2. [Definizioni e Acronimi](#sp1.2) 
	3. [Riferimenti](#sp1.3)
2. [Descrizione del Sistema](#p2)
	1. [Contenuti e Motivazioni](#sp2.1)
	2. [Obbiettivi del Progetto](#sp2.2)
3. [Richieste](#p3)
 	1. [Soggetti](#sp3.1)
 	2. [Richieste Funzionali](#sp3.2)
 	3. [Richieste non Funzionali](#sp3.3)
  
  

<a name="p1"></a>

## 1. Introduzione

<a name="sp1.1"></a>
Su commissione dell'azienda ePortafoglio, siamo qui a realizzare un sistema di home banking
(nome provvisorio "BancApp") che permetta ai clienti di poter eseguire diverse operazioni 
sul proprio conto bancario, garantendo massima sicurezza tramite l'utilizzo di credenziali 
e codici univoci.

### 1.1 Obbiettivi del Documento
Lo scopo  di questo documento è quello di illustrare ogni aspetto del sistema, presentare 
le sue features, nonché essere anche una guida introduttiva sul suo funzionamento. 
Il documento descriverà i potenziali utenti e i casi d'uso, sia attraverso descrizioni
a parole, sia con l'utilizzo di Diagrammi di Classi e Diagrammi di Sequenza.

<a name="sp1.2"></a>

### 1.2 Definizione e Acronimi

| Acronym				| Definition | 
| ------------------------------------- | ----------- | 
| SW                                    | Software |
| GUI					| Graphical User Interface |
| Login					| Autenticazione Accesso |
| HB      | Home Banking |

<a name="sp1.3"></a>

### 1.3 Riferimenti 

Fare riferimento al documento esame.pdf presente nel repository, cartella main\docs\ref

<a name="p2"></a>

## 2. Descrizione Del Sistema 
<a name="sp2.15"></a>
Il SW è un applicativo di home banking, con una interfaccia grafica user-friendly, che permette
all'utilizzatore di eseguire le classiche operazioni sul proprio conto: invio di denaro, 
ricezione di denaro, verifica delle ultime operazioni effettuate (estratto conto).

### 2.1 Contenuti e Motivazioni
Attualmente l'azienda ePortafoglio non ha un servizio di HB, i suoi clienti possono effettuare
le operazioni sui propri conti personali soltanto attraverso l'utilizzo di un terminale ATM 
presente all'esterno delle sedi fisiche della Banca o attraverso lo sportello della Banca stessa.
Per venire incontro alle esigenze del cliente e per raggiungere i relativi competitors del settore,
ePortafoglio ha quindi commissionato la realizzazione di questo applicativo.

<a name="sp2.2"></a>

### 2.2 Obbiettivi del Progetto 
Nell'immediato: realizzare un SW che sia in grado di funzionare sulla maggior parte delle piattaforme in 
uso: PC Windows, PC MacOS, smartphone iOS e Android; creare un'ambiente di sistema che permetta di non 
avere ridondanza di dati e che abbia requisiti hardware minimi molto accessibili.
Sul lungo termine: invogliare i clienti ad effettuare più operazioni, in modo tale da aumentare i 
guadagni dell'azienda ePortafoglio tramite le commissioni; attirare nuovi clienti offrendo un
applicativo accattivante.

<a name="p3"></a>

## 3. Richieste

| Priorità | Significato | 
| --------------- | ----------- | 
| M | **Mandatorio:**   |
| D | **Desiderabile:** |
| O | **Opzionale:**    |
| E | **Futura Espansione:** |

<a name="sp3.1"></a>
### 3.1 Soggetti
Client: ePortafoglio, in quanto committente del progetto globale.
Users: Clienti della banca ePortafoglio, Funzionari della banca ePortafoglio

<a name="sp3.2"></a>
### 3.2 Requisiti Funzionali

| ID | Descrizione | Priorità |
| --------------- | ----------- | ---------- | 
| 1.0 |  Per accedere al SW, Cliente deve avere almeno 1 conto bancario ePortafoglio intestato a  sè |M|
| 1.1 |  Cliente può inviare denaro - nel limite della disponibilità del proprio conto  |M|
| 1.2 |  Cliente può visualizzare le operazioni svolte sul proprio conto negli ultimi 30 giorni |M|
| 1.3 |  Cliente può bloccare la propria carta Bancomat (e.g. in caso di furto o smarrimento) |M|
| 1.4 |  Cliente può effettuare ricariche telefoniche su un numero di telefono a sua scelta |E|
| 1.5 |  Cliente può creare un file PDF dal registro delle ultime operazioni svolte |E|
| 2.0 |  Funzionario può creare un nuovo conto e associarlo ad una persona fisica |M|
| 2.1 |  Funzionario può modificare i dati anagrafici relativi ad un conto esistente |M|
| 2.3 |  Funzionario può bloccare un conto esistente (e.g. in caso di operazioni sospette o su richiesta del cliente) |M|
| 2.4 |  Funzionario può chiudere un conto esistente (e.g. su richiesta del cliente) |M|
| 2.5 |  Funzionario può bloccare la carta Bancomat associata ad un conto esistente (e.g. in caso di operazioni sospette o su richiesta del cliente)  |M|

<a name="sp3.3"></a>
### 3.2 Requisiti non funzionali 
 
| ID | Descrizione | Priorità |
| --------------- | ----------- | ---------- | 
| 1.0 | Il SW deve poter gestire un numero di almeno 20000000 utenti in contemporanea |M|
| 1.1 | Il SW deve essere compatibile con PC Windows e PC MacOS |M|
| 2.1 | Il SW dovrebbe poter essere compatibile con smartphone iOS e Android |D|
| 3.1 | Il SW dovrebbe essere accessibile a persone ipovedenti |O|
| 3.2 | Il SW dovrebbe essere disponibile in inglese, francese, tedesco, spagnolo |O|
