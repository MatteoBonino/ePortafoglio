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
- nome provvisorio "BancApp" - che permetta ai clienti di poter eseguire diverse operazioni 
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
Client: Università degli Studi di Genova, Città Metropolitana di Genova, Assessore 
della Cultura
Regulators: un team dedicato alla verifica del rispetto dei regolamenti universitari 
vigenti al fine di garantire massima trasparenza e regolarità delle procedure
Users: studenti e docenti sono in primis coloro che agiranno sul SW; avranno altresì 
accesso anche il personale universitario, amministrativo e direttivo

<a name="sp3.2"></a>
### 3.2 Requisiti Funzionali

| ID | Descrizione | Priorità |
| --------------- | ----------- | ---------- | 
| 0.0 |  Ogni corso deve avere almeno 1 docente e può averne più di 1 |M|
| 1.0 |  Docente potrà visualizzare i corsi di cui è insegnante  |M|
| 1.1 |  Docente potrà indire esami, specificando una data, per ogni corso di cui è insegnante |M|
| 1.2 |  Docente potrà visualizzare la lista degli iscritti ad un esame di cui è insegnante |M|
| 1.3 |  Docente potrà registrare un voto per ogni studente iscritto all'esame di un corso di cui è insegnante |M|
| 1.4 |  Docente potrà visualizzare i voti già assegnati agli studenti di un corso di cui è insegnante |M|
| 1.5 |  Docente potrà cancellare appelli futuri di un corso di cui è insegnante |M|
| 1.6 |  Docente potrà spostare un appello di un corso di cui è insegnante |M|
| 1.7 |  Docente non potrà registrare un voto ad un corso di cui è insegnante se è già presente un voto |M|
| 2.0 |  Studente potrà visualizzare la lista dei corsi a cui è iscritto |M|
| 2.1 |	 Studente potrà visualizzare la lista dei corsi superati, con il relativo voto |M|
| 2.2 |  Studente potrà visualizzare la lista degli esami a cui iscriversi |M|
| 2.3 |  Studente non potrà iscriversi ad un esame superato |M|
| 3.0 |  Segreteria potrà cambiare il voto ad uno studente |M|
| 3.1 |  Segreteria può leggere le segnalazioni fatte da docenti e studenti |M|
| 4.0 |  Studente e Docente possono segnalare eventuali errori |D|
| 5.0 |  Il Sistema deve permettere di estrarre dei files PDF delle liste |D|
| 5.1 |  Il Sistema deve permettere di visualizzare lo stato delle operazioni |O|

<a name="sp3.3"></a>
### 3.2 Requisiti non funzionali 
 
| ID | Descrizione | Priorità |
| --------------- | ----------- | ---------- | 
| 1.0 | Il SW deve poter gestire un numero di almeno 2000000 utenti in contemporanea |M|
| 1.1 | Il SW deve essere compatibile con PC Windows e PC MacOS |M|
| 2.1 | Il SW dovrebbe poter essere compatibile con smartphone iOS e Android |D|
| 3.1 | Il SW dovrebbe essere accessibile a persone ipovedenti |O|
| 3.2 | Il SW dovrebbe essere disponibile in inglese, francese, tedesco, spagnolo |O|
