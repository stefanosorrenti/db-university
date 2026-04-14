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

Un DIPARTIMENTO può avere più CORSI DI LAUREA ma più CORSO DI LAUREA hanno solo un DIPARTIMENTO. //One to many

Un CORSO DI LAUREA può avere più CORSI e un CORSO può essere presente in più CORSI DI LAUREA.  //Many to Many

Un CORSO può avere più INSEGNANTI e più INSEGNANTI possono avere più di un CORSO. //Many to Many

Un CORSO può avere più APPELLI D'ESAME e gli APPELLI D'ESAME  si riferiscono solo ad UN CORSO. //Many to one

Uno STUDENTE è iscritto ad un CORSO DI LAUREA ma un CORSO DI LAUREA ha più STUDENTI. //One to many

Un STUDENTO può iscriversi a più APPELLI D'ESAME e un APPELLO D'ESAME può avere più STUDENTI.