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

    -ID
    -nome_dipartimento
    -descrizione
    -codice_dipartimento


# TABLE NAME: Corsi di laurea
    -ID
    -nome_corso_laurea
    -durata
    -livello
    -codice_dipartimento_id


# TABLE NAME: Corsi
    -ID
    -nome_corso


# TABLE NAME: Insegnanti
    -ID
    -nome
    -cognome
    -email
    

# TABLE NAME: Appelli esami
    -ID
    -data_esame
    -insegnante_id
    -corso

# TABLE NAME: Studenti
    -ID
    -nome
    -cognome
    -matricola

# TABLE NAME: Voti
    -ID
    -voto
    -esito


# TABELLE PONTE

# TABLE NAME : Corsi di laurea / Corsi
    -ID
    -nome_corso_laurea_id
    -nome_corso_id


# TABLE NAME : Corsi / Insegnanti
    -ID
    -corso_id
    -insegnanti_id


# TABLE NAME: Studenti / Appelli d'esame
    -ID
    -studenti_id
    appelli_d'esame_id


# TABLE NAME: Studente / Voto
    -ID
    -studente_id
    -voto_id
    -esito_id