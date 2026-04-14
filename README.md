# TRACCIA

Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
ogni Corso può essere tenuto da diversi Insegnanti;
ogni Corso prevede più appelli d'Esame;
ogni Studente è iscritto ad un solo Corso di Laurea;
ogni Studente può iscriversi a più appelli di Esame;
per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.
Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.

# ENTITA'

`Dipartimenti`

`Corso di laurea`

`Corso (materia)`

`Insegnanti`

`Appelli d'esame`

`Studente `

`Voto`

# RELAZIONI:

Un DIPARTIMENTO può avere più CORSI DI LAUREA ma un CORSO DI LAUREA ha un solo  DIPARTIMENTO. //One to many OK

Un CORSO DI LAUREA può avere più CORSI e un CORSO può essere presente in più CORSI DI LAUREA.  //Many to Many OK

Un CORSO può avere più INSEGNANTI e OGNI INSEGNANTE può avere più di un CORSO. //Many to Many OK

Un CORSO può avere più APPELLI D'ESAME un APPELLO D'ESAME  ha un solo CORSO. //One to many OK

Uno STUDENTE è iscritto ad un CORSO DI LAUREA ma un CORSO DI LAUREA ha più STUDENTI. //One to many OK

Uno STUDENTE può iscriversi a più APPELLI D'ESAME e un APPELLO D'ESAME può avere più STUDENTI. //Many to Many

Uno STUDENTE può avere più di un VOTO e un VOTO può essere dato a più STUDENTI //Many to Many

# TABELLE


# TABLE NAME: Dipartimenti

    -ID - INT - PRIMARY_KEY AUTO_INCREMENT
    -nome_dipartimento - VARCHAR(100) - NOTNULL -INDICE
    -descrizione - TEXT - DEFAULT('')
    -codice_dipartimento - SMALLINT - NOTNULL -INDICE


# TABLE NAME: Corsi di laurea
    -ID INT - PRIMARY_KEY AUTO_INCREMENT
    -nome_corso_laurea - VARCHAR(256) - NOTNULL - INDICE
    -durata - TINYINT - NOTNULL
    -livello - VARCHAR(100) - NOTNULL
    -codice_dipartimento_id


# TABLE NAME: Corsi
    -ID - INT - PRIMARY_KEY AUTO_INCREMENT
    -nome_corso - VARCHAR(256) - NOTNULL 


# TABLE NAME: Insegnanti
    -ID - INT - PRIMARY_KEY AUTO_INCREMENT
    -nome - VARCHAR(20) - NOTNULL - INDICE
    -cognome - VARCHAR(20) - NOTNULL - INDICE
    -email - VARCHAR(50) - DEFAULT('') 
    

# TABLE NAME: Appelli esami
    -ID INT - PRIMARY_KEY AUTO_INCREMENT INDEX
    -data_esame - DATE - NOTNULL
    -insegnante_id
    -corso_id
    -email_id

# TABLE NAME: Studenti
    -ID INT - PRIMARY_KEY AUTO_INCREMENT INDEX
    -nome - VARCHAR(20) - NOTNULL - INDICE
    -cognome - VARCHAR(20) - NOTNULL - INDICE
    -matricola - SMALLINT - NOTNULL - INDICE

# TABLE NAME: Voti
    -ID INT - PRIMARY_KEY AUTO_INCREMENT INDEX
    -voto - TINYINT - NOTNULL
    -esito - TINYINT - NOTNULL


# TABELLE PONTE

# TABLE NAME : Corsi di laurea / Corsi
    -ID INT - PRIMARY_KEY AUTO_INCREMENT INDEX
    -nome_corso_laurea_id
    -nome_corso_id


# TABLE NAME : Corsi / Insegnanti
    -ID INT - PRIMARY_KEY AUTO_INCREMENT INDEX
    -corso_id
    -insegnanti_id


# TABLE NAME: Studenti / Appelli d'esame
    -ID INT - PRIMARY_KEY AUTO_INCREMENT INDEX
    -studenti_id
    appelli_d'esame_id


# TABLE NAME: Studente / Voto
    -ID INT - PRIMARY_KEY AUTO_INCREMENT INDEX
    -studente_id
    -voto_id
    -esito_id