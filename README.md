Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
- sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni Corso può essere tenuto da diversi Insegnanti;
- ogni Corso prevede più appelli d'Esame;
- ogni Studente è iscritto ad un solo Corso di Laurea;
- ogni Studente può iscriversi a più appelli di Esame;
- per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.
Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.



- Query 1

SELECT * 
FROM `students` 
WHERE YEAR(`date_of_birth`) = 1990;

- Query 2

SELECT *
FROM `courses`
WHERE `cfu` > 10;

- Query 3

SELECT *
FROM `students`
WHERE TIMESTAMPDIFF(YEAR, `date_of_birth`, CURDATE()) > 30;

- Query 4

SELECT *
FROM courses
WHERE period LIKE 'I semestre'
AND year = 1;

- Query 5

SELECT *
FROM exams
WHERE date LIKE '2020-06-20'
AND hour > '14:00:00';

- Query 6

SELECT *
FROM `degrees`
WHERE `level` LIKE 'magistrale';

- Query 7

SELECT COUNT(*) as quantity_departments
FROM departments;

- Query 8

SELECT COUNT(*) as `no_phone_teachers`
FROM `teachers`
WHERE `phone` IS NULL;

- Query 9

INSERT INTO `students`(`degree_id`, `name`, `surname`, `date_of_birth`, `fiscal_code`, `enrolment_date`, `registration_number`, `email`) VALUES (5,'Gioele','Miscia','1988-07-18','MSCGLI88L18C632F','2024-09-12',44635388,'gioele.miscia@gmail.com')

- Query 10

UPDATE `teachers`
SET `office_number`='126'
WHERE `name` LIKE 'Pietro'
AND `surname` LIKE 'Rizzo'

- Query 11

DELETE
FROM `students`
WHERE `name` LIKE 'Gioele'
AND `surname` LIKE 'Miscia'
AND `date_of_birth` LIKE '1988-07-18';