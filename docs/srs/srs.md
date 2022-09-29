### ePortafoglio - BancApp


**VERSION : 1.0**

**Author**  
Matteo Bonino

**REVISION HISTORY**

| Version    | Date        | Authors      | Notes        |
| ----------- | ----------- | ----------- | ----------- |
|1.0| 29/09 | Matteo Bonino | - |


# Table of Contents

1. [User Case](#p1)
	1. [Diagramma](#sp1.1)
	2. [Attori](#sp1.2) 
	3. [Lista Funzionalità](#sp1.3)
2. [Scenari](#p2)

	0. [Login](#sp2.0)
	1. [Autenticazione](#sp2.1)
	2. [Consulta Lista Corsi](#sp2.2)
	3. [Lista Studenti iscritti al corso](#sp2.3)
	4. [Elenco Esami Attivi Corso](#sp2.4)
	5. [Aggiunta Esame Corso](#sp2.5)
	6. [Consulta Lista Corsi superati con relativa votazione](#sp2.6)
	7. [Consulta Lista Esami a cui è iscritto](#sp2.7)
	8. [Iscrizione Esami](#sp2.8)
	9. [Rimuovere iscrizione ad un Esame](#sp2.9)
	10. [Informazioni Account](#sp2.10)
	11. [Creazione dei dipartimenti](#sp2.11)

<a name="p1"></a>

## 1. User Case

<a name="sp1.1"></a>

### 1.1 Diagramma

![Diagramma UML](https://github.com/MatteoBonino/ePortafoglio/blob/main/docs/srs/imgs/ePortafoglio_BancAPP_URS.png)

<a name="sp1.2"></a>

### 1.2 Attori

| Nome | Descrizione |
| ----------- | ----------- | 
|Cliente| Cliente della banca, già in possesso di almeno 1 conto intestato a sè stesso, interessato a fare operazioni sul proprio conto |
|Funzionario| Utente con maggior controllo sui conti dei clienti della banca |


<a name="sp1.3"></a>

### 1.3 Lista e Funzionalità 
| ID | Nome | Descrizione |
| ----------- | ----------- | ----------- | 
| 1 | Login Cliente | Il Cliente accede con credenziali valide al sistema |
| 2 | Login Funzionario | Il Funzionario accede con credenziali valide al sistema |
| 3 | Inviare denaro | Il Cliente può inviare una somma di denaro ad un altro conto, anche appartenente ad un circuito bancario differente |
| 4 | Visualizzare Estratto Conto (Cliente) | Il Cliente può vedere le operazioni effettuate sul suo conto negli ultimi 30 giorni |
| 5 | Visualizzare Estratto Conto (Funzionario) | Il Funzionario può vedere le operazioni effettuate su qualsiasi conto esistente negli ultimi 30 giorni |
| 6 | Bloccare Bancomat (Cliente | Il Cliente può richiedere il blocco del proprio Bancomat, se associato al suo conto |
| 7 | Bloccare Bancomat (Funzionario | Il Funzionario può bloccare qualsiasi Bancomat associato ad un conto esistente |
| 8 | Creare nuovo conto | Il Funzionario può creare un nuovo conto bancario, associato ad una persona fisica |
| 9 | Modificare Dati Anagrafici | Il Funzionario può modificare i dati anagrafici di un conto già esistente |
| 10 | Bloccare un conto | Il Funzionario può bloccare un conto esistente |
| 11 | Chiudere un conto | Il Funzionario può chiudere un conto esistente |

<a name="p2"></a>

## Scenari

<a name="sp2.1"></a>

### 2.1 Login

| ID: 1 | <u>Login</u> |
| ----------- | ----------- | 
| Attore | Docente, Studente, Amministrazione |
| Tipo | Primario | 
| Precondizione | L'utente ha delle credenziali uniche e personali valide per il sistema |
| Scenario Principale | |
| 1. | L'utente inserisce la sua ID |
| 2. | L'utente inserisce la password |
| 3. | Il Sistema conferma che che la combinazione delle credenziali è valida e corrisponde ad un utente | 
| 4. | Il sistema scarica o aggiorna il certificato di autenticazione |
| Postcondizione: | L'utente ha accesso al sistema |
| 3a | Scenario Alternativo: Autneticazione non valida |
| 1. | Il sistema segnala che non esiste un account per l'ID inserito |
| 2. | Il sistema suggerisce di contattare l'Amministrazione per la creazione di un account |
| 3. | Il sistema ritorna al punto 1 principale |
| 3b | Scenario Alternativo: L'utente inserisce la password non corretta < 3 volte |
| 1. | Il sistema notifica che la password non è valida e invita a digitarla di nuovo |
| 2. | Il sistema incrementa il counter dei fallimenti |
| 3. | Il sistema torna al punto 2 principale |
| 3c | Scenario Alternativo: L'utente inserisce la password non valide per la terza volta |
| 1. | Il sistema notifica che la password è errata per la terza volta |
| 2. | Il sistema blocca l'account e invia una mail di sblocco all'utente |
| 3. | Il sistema invita l'utente ad aggiornare la password dalla mail |

<a name ="sp2.1.1"></a>

| ID: 1.1 | Autenticazione (Opzionale se pre-condizione è semplicemente "avere un certificato valido") |
| ----------- | ----------- | 
| Attore | Docente, Studente, Amministrazione (Principale) |
| Tipo | Secondario | 
| Precondizione | |
| Scenario Principale | |
| 1. | Il sistema controlla che la password ed ID siano valide e corrispondano ad un utente |
| 2. | Il sistema autentica le credenziali |
| 3. | Il sistema rilascia o aggiorna il certificato di autenticazione |
| Postcondizione: | L'utente è autentificato |
|| Scenario Alternativo: Certificato Scaduto |
|| Scenario Alternativo: Certificato Non Valido |


<a name="sp2.2"></a>

### 2.2 Consulta Lista Corsi

| ID: 2 | <b>Consulta Lista Corsi</b> |
| ----------- | ----------- | 
| Attore | Docente (Principale), Studente (Principale) |
| Tipo | Primario |
| Precondizione | L'utente ha un certificato di autenticazione valido; l'utente è autorizzato ad accedere ai corsi |
| Scenario Principale | |
| 1. | L'Utente seleziona l'anno scolastico |
| 2. | Il Sistema riporta i corsi di quell'anno per cui il docente è registrato |
| 3. | L'Utente clicca sul corso che vuole esaminare |
| 4. | Il sistema mostra le informazioni identificative del corso |
| Postcondizione | L'Utente ha accesso alle informazioni del corso specificato |

<a name="sp2.3"></a>

### 2.3 Lista Studenti iscritti al corso

| ID: 3 | <b>Lista Studenti iscritti al corso </b> |
| ----------- | ----------- | 
| Attore | Docente (Principale), Amministrazione (Principale) |
| Tipo | Primario | 
| Precondizione | L'utente ha un certificato di autenticazione valido; Il Docente insegna il corso dell'esame |
| Scenario Principale | |
| 1. | Il Docente seleziona il corso |
| 2. | Il Docente sceglie l'opzione "Mostra Studenti Iscritti" |
| 3. | Il Sistema fornisce l'elenco degli studenti iscritti al corso |
| Postcondizione: | Il docente ha accesso alla lista degli studenti iscritti ad un corso |


<a name="sp2.4"></a>

### 2.4 Elenco Esami Attivi Corso

| ID: 4 | <b>Elenco Esami Attivi Corso</b> |
| ----------- | ----------- | 
| Attore | Docente (Principale) |
| Tipo | Primario | 
| Precondizione | L'utente ha un certificato di autenticazione valido; Il Docente insegna il corso dell'esame |
| Scenario Principale | |
| 1. | Il Docente selezione il corso |
| 2. | Il Docente clicca su opzione "Lista Esami Corso" |
| 3. | Il Sistema mostra la lista degli esami del corso. |
| Postcondizione: | Il Docente visualizza la lista degli esami attivi |

<a name="sp2.5"></a>

### 2.5 Aggiunta Esame Corso

| ID: 5 | <b>Aggiunta Esame Corso</b> |
| ----------- | ----------- | 
| Attore | Docente (Principale) |
| Tipo | Primario | 
| Precondizione | L'utente ha un certificato di autenticazione valido; Il Docente insegna il corso dell'esame |
| Scenario Principale | |
| 1. | L'utente visualizza la lista esami del corso |
| 2. | L'utense sceglie l'opzione "Aggiungi Esame" |
| 3. | L'utente inserisce la data/le date dell'appello |
| 4. | L'utente salva le informazioni |
| 5. | Il Sistema notifica la creazione dell'appello |
| 6. | Il Sistema invia una mail a tutti gli iscritti al corso |
| Postcondizione: | L'esame per il corso è stato creato |


<a name="sp2.6"></a>

### 2.6 Consulta Corsi superati con relativa votazione

| ID: 6 |<b>Consulta Corsi superati con relativa votazione</b>|
| ---------- | ------------|
| Attore | Studente (Principale) |
| Tipo | Primario |
| Precondizione |L'utente ha un certificato di autenticazione valido; Lo studente è iscritto all'università |
| Scenario principale | |
| 1. | L'utente visualizza la lista dei corsi |
| 2. | L'utense sceglie l'opzione "Visualizza corsi superati" |
| 3. | L'utense sceglie l'opzione "Visualizza votazione" del corso desiderato |
| Postcondizione: | Lo studente visualizza la lista dei corsi superati |

<a name="sp2.7"></a>

### 2.7 Consulta Esami a cui è iscritto

| ID: 7 |<b>Consulta Esami a cui è iscritto</b> |
| ---------- | ------------|
| Attore | Studente (Principale)|
| Tipo | Primario|
| Precondizione | L'utente ha un certificato di autenticazione valido; l'utente è autorizzato ad accedere ai corsi |
| Scenario Principale | |
| 1. | L'Utente seleziona l'anno scolastico |
| 2. | Il Sistema riporta gli esami di quell'anno per cui lo studente è iscritto |
| 3. | L'Utente clicca sull'esame che vuole esaminare |
| 4. | Il sistema mostra le informazioni identificative dell'esame |
| Postcondizione | L'Utente ha accesso alle informazioni dell'esame specificato |

<a name="sp2.8"></a>

### 2.8 Iscrizione Esami

| ID: 8 |<b>Iscrizione Esami</b> |
| ---------- | ------------|
| Attore | Studente (Principale)|
| Tipo | Primario|
| Precondizione | L'utente ha un certificato di autenticazione valido; Lo stuente è iscritto al corso dell'esame |
| Scenario Principale | |
| 1. | L'utente visualizza la lista esami del corso |
| 2. | L'utense sceglie l'opzione "Aggiungi Esame" |
| 4. | L'utente visualizza la data/le date dell'appello |
| 5. | L'utente conferma l'iscrizione |
| 6. | Il Sistema notifica all'utente l'iscrizione all'appello |
| 6. | Il Sistema invia una mail al docente del corso |
| Postcondizione: | Lo studente è iscritto all'esame |

<a name="sp2.9"></a>

### 2.9 Rimuovere iscrizione ad un Esame

|ID: 9 |<b>Rimuovere iscrizione ad un Esame</b> |
| ---------- | ------------|
| Attore | Studente (Principale) |
| Tipo | Primario|
| Preconzione | L'utente ha un certificato di autenticazione valido; Lo studente è iscritto al corso dell'esame |
| Scenario Principale | |
| 1. | L'utente visualizza la lista esami del corso |
| 2. | L'utense sceglie l'opzione "Visualizza Esame" |
| 3. | L'utente sceglie l'opzione "Rimuovi Esame" |
| 5. | L'utente conferma la disiscrizione |
| 6. | Il Sistema notifica l'iscrizione all'appello |
| 6. | Il Sistema invia una mail al docente del corso |
| Postcondizione: | Lo studente ha rimosso l'iscritto all'esame |

<a name="sp2.10"></a>

### 2.10 Informazioni Account

| ID: 10 |<b>Informazioni Account</b> |
| ---------- | ------------|
| Attore | Studente (Principale), Docente(Principale) |
| Tipo | Primario|
| Precondizione | L'utente ha un certificato di autenticazione valido; l'utente è iscritto all'università |
| Scenario Principale | |
| 1. | L'utente sceglie l'opzione "visualizza account" |
| 2. | L'utente può consultare le sue informazioni |
| 3. | L'utente può modificare o lasciarle invariate |
| 5. | L'utente salva le informazioni |
| Postcondizione | Lo studente verifica le informazioni di account|

<a name="sp2.11"></a>

### 2.11 Creazione dipartimenti
| ID: 11|<b>Creazione dipartimenti</b> |
| ---------- | ------------|
| Attore | Amministratore (Principale) |
| Tipo | Primario |
| Precondizione | L'utente ha un certificato di autenticazione valido |
| Scenario Principale | |
|1. | L'utente sceglie il modello Dipartimento |
|2. | L'utente per ogni Dipartimento istanzia i relativi Oggetti |
|3. | L'utente salva tutte le informazioni inserite |
|4. | L'utente verifica che i Dipartimenti creati corrispondano a quelli delle direttive di Ateneo |
| Postcondizione | L'utente ha creato un nuovo dipartimento |

