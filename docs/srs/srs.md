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

	1. [Login](#sp2.1)
	2. [Autenticazione](#sp2.2)
	3. [Inviare Denaro](#sp2.3)
	4. [Visualizza estratto conto (Cliente)](#sp2.4)
	5. [Visualizza estratto conto (Funzionario)](#sp2.5)
	6. [Bloccare Bancomat (Cliente)](#sp2.6)
	7. [Bloccare Bancomat (Funzionario)](#sp2.7)
	8. [Creare un nuovo conto](#sp2.8)
	9. [Modifica dati anagrafici](#sp2.9)
	10. [Bloccare un conto](#sp2.10)
	11. [Chiudere un conto](#sp2.11)

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
| 2 | Autenticazione | Verifica autenticazione
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
| Attore | Cliente, Funzionario |
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

<a name ="sp2.2"></a>

### 2.2 Autenticazione

| ID: 2 | Autenticazione (Opzionale se pre-condizione è semplicemente "avere un certificato valido") |
| ----------- | ----------- | 
| Attore | Cliente, Funzionario |
| Tipo | Secondario | 
| Precondizione | |
| Scenario Principale | |
| 1. | Il sistema controlla che la password ed ID siano valide e corrispondano ad un utente |
| 2. | Il sistema autentica le credenziali |
| 3. | Il sistema rilascia o aggiorna il certificato di autenticazione |
| Postcondizione: | L'utente è autentificato |
|| Scenario Alternativo: Certificato Scaduto |
|| Scenario Alternativo: Certificato Non Valido |

<a name="sp2.3"></a>

### 2.3 Inviare Denaro

| ID: 3 | <b>Inviare Denaro</b> |
| ----------- | ----------- | 
| Attore | Cliente |
| Tipo | Primario |
| Precondizione | L'utente ha un certificato di autenticazione valido |
| Scenario Principale | |
| 1. | L'Utente seleziona un importo |
| 2. | L'Utente inserisce un iban destinario |
| 3. | L'Utente inserisce informazioni accessorie |
| 4. | L'Utente conferma di voler eseguire l'operazione e che i dati siano corretti|
| Postcondizione | Sistema restituisce una schermata coi dati riepilogativi dell'operazione |
| 2a.| Scenario Alternativo: i dati inseriti non sono corretti |
| 1. | Sistema notifica che non ha trovato nessun Iban sul sistema bancario mondiale corrispondente a quello inserito |
| 2. | Sistema restituisce una schermata "Operazione non effettuata, il denaro non è stato inviato" |

<a name="sp2.4"></a>

### 2.4 Visualizzare Estratto Conto (Cliente)

| ID: 4 | <b>Visualizzare Estratto Conto (Cliente)</b> |
| ----------- | ----------- | 
| Attore | Cliente (Principale) |
| Tipo | Primario | 
| Precondizione | L'utente ha un certificato di autenticazione valido |
| Scenario Principale | |
| 1. | L'Utente clicca sull'opzione "Visualizza lista movimenti degli ultimi 30 giorni" |
| Postcondizione: | Sistema restituisce una schermata contenente la lista di movimenti effettuati su quel conto negli ultimi 30 giorni |
| 1a. | Scenario alternativo: non sono stati effettuati movimenti negli ultimi 30 giorni" |
| 1. | Sistema notifica che non sono stati fatti movimenti sul conto negli ultimi 30 giorni |


<a name ="sp2.5"></a>

### 2.5 Visualizzare Estratto Conto (Funzionario)

| ID: 5 | <b>Visualizzare Estratto Conto (Funzionario)</b> |
| ----------- | ----------- | 
| Attore | Cliente (Principale) |
| Tipo | Primario | 
| Precondizione | L'utente ha un certificato di autenticazione valido |
| Scenario Principale | |
| 1. | L'Utente clicca sull'opzione "Visualizza lista movimenti degli ultimi 30 giorni" |
| 2. | Sistema chiede di inserire un codice iban |
| 3. | L'Utente inserisce un codice iban |
| Postcondizione: | Sistema restituisce una schermata contenente la lista di movimenti effettuati su quel conto negli ultimi 30 giorni |
| 3a. | Scenario alternativo: non sono stati effettuati movimenti negli ultimi 30 giorni" |
| 1. | Sistema notifica che non sono stati fatti movimenti sul conto negli ultimi 30 giorni |
| 3b. | Scenario alternativo: l'iban inserito è errato o non presente sul database interno della banca stessa |
| 1. | Sistema notifica che non è stato trovato l'iban inserito |

<a name ="sp2.6"></a>

### 2.6 Bloccare Bancomat (Cliente)

| ID: 6 | <b>Bloccare Bancomat (Cliente)</b> |
| ----------- | ----------- | 
| Attore | Cliente (Principale) |
| Tipo | Primario | 
| Precondizione | L'utente ha un certificato di autenticazione valido |
| Scenario Principale | |
| 1. | L'Utente clicca sull'opzione "Blocca Carta Bancomat" |
| 2. | Sistema chiede "Sei sicuro di voler procedere?" |
| 3. | L'Utente clicca "Si" |
| 4. | Sistema chiede di inserire di nuovo le credenziali (per motivi di sicurezza) |
| 5. | L'Utente inserisce le credenziali |
| Postcondizione: | Sistema restituisce una schermata confermando il blocco della carta Bancomat e le istruzioni per richiedere lo sblocco |
| 1a. | Scenario alternativo: nessuna carta Bancomat è associata al conto del cliente |
| 1. | Sistema notifica che non risulta nessuna carta Bancomat associata al conto del cliente|
| 5a. | Scenario alternativo: le credenziali inserite sono errate |
| 1. | Sistema concede 3 tentativi, superati i quali il conto viene bloccato in automatico per motivi di sicurezza, notificando il cliente attraverso email e sms, |

<a name ="sp2.7"></a>

### 2.7 Bloccare Bancomat (Funzionario)

| ID: 7 | <b>Bloccare Bancomat (Funzionario)</b> |
| ----------- | ----------- | 
| Attore | Funzionario (Principale) |
| Tipo | Primario | 
| Precondizione | L'utente ha un certificato di autenticazione valido |
| Scenario Principale | |
| 1. | L'Utente clicca sull'opzione "Blocca Carta Bancomat" |
| 2. | Sistema chiede di inserire un iban |
| 3. | L'Utente inserisce un codice iban |
| 4. | Sistema chiede "Sei sicuro di voler procedere?" |
| 5. | L'Utente clicca "Si" |
| Postcondizione: | Sistema restituisce una schermata confermando il blocco della carta Bancomat |
| 4a. | Scenario alternativo: nessuna carta Bancomat è associata al conto del cliente |
| 1. | Sistema notifica che non risulta nessuna carta Bancomat associata al conto del cliente|
| 4b. | Scenario alternativo: il codice iban non esiste o non appartiene al circuito interno della banca stessa |
| 1. | Sistema notifica che il codice iban non risulta nel database interno della banca stessa |

<a name="sp2.8"></a>

### 2.8 Creare nuovo conto

| ID: 8 | <b>Creare nuovo conto</b> |
| ----------- | ----------- | 
| Attore | Funzionario (Principale) |
| Tipo | Primario | 
| Precondizione | L'utente ha un certificato di autenticazione valido |
| Scenario Principale | |
| 1. | L'utente seleziona l'opzione "Crea nuovo conto" |
| 2. | L'utente compila un'insieme di campi inserendo i dati anagrafici della persona fisica |
| 3. | Sistema chiede conferma nel procedere alla creazione |
| 4. | L'utente clicca conferma |
| Postcondizione: | Sistema crea un conto a cui associa un Iban libero (ossia non utilizzato da nessun conto nel sistema bancario mondiale) | |


<a name="sp2.9"></a>

### 2.9 Modificare dati anagrafici di un conto

| ID: 9 |<b>Modificare dati anagrafici di un conto</b>|
| ---------- | ------------|
| Attore | Funzionario (Principale) |
| Tipo | Primario |
| Precondizione |L'utente ha un certificato di autenticazione valido |
| Scenario principale | |
| 1. | L'utente seleziona l'opzione "Modifica dati anagrafici" |
| 2. | Sistema chiede di inserire un codice iban appartenente al circuito bancario interno della banca stessa |
| 3. | L'utente inserisce un codice iban |
| 4. | Sistema restituisce la schermata riepilogativa con i dati anagrafici modificabili |
| 5. | L'utente modifica i campi che desidera modificare, dopodiché clicca "Salva modifiche" |
| Postcondizione: | Sistema restituisce il messaggio "Modifiche salvate con successo" |
| 3a. | Scenario alternativo: il codice iban non esiste o non appartiene al circuito interno della banca stessa |
| 1. | Sistema notifica che il codice iban non risulta nel database interno della banca stessa |

<a name="sp2.10"></a>

### 2.10 Bloccare un conto 

| ID: 10 |<b>Bloccare un conto</b>|
| ---------- | ------------|
| Attore | Funzionario (Principale) |
| Tipo | Primario |
| Precondizione |L'utente ha un certificato di autenticazione valido |
| Scenario principale | |
| 1. | L'utente seleziona l'opzione "Blocca un conto" |
| 2. | Sistema chiede di inserire un codice iban appartenente al circuito bancario interno della banca stessa |
| 3. | L'utente inserisce un codice iban |
| Postcondizione: | Sistema restituisce il messaggio "Conto bloccato con successo" |
| 3a. | Scenario alternativo: il codice iban non esiste o non appartiene al circuito interno della banca stessa |
| 1. | Sistema notifica che il codice iban non risulta nel database interno della banca stessa |


<a name="sp2.11"></a>

### 2.11 Chiudere un conto

| ID: 11 |<b>Chiudere un conto</b>|
| ---------- | ------------|
| Attore | Funzionario (Principale) |
| Tipo | Primario |
| Precondizione |L'utente ha un certificato di autenticazione valido |
| Scenario principale | |
| 1. | L'utente seleziona l'opzione "Chiudi un conto" |
| 2. | Sistema chiede di inserire un codice iban appartenente al circuito bancario interno della banca stessa |
| 3. | L'utente inserisce un codice iban |
| Postcondizione: | Sistema restituisce il messaggio "Conto chiuso con successo" |
| 3a. | Scenario alternativo: il codice iban non esiste o non appartiene al circuito interno della banca stessa |
| 1. | Sistema notifica che il codice iban non risulta nel database interno della banca stessa |

