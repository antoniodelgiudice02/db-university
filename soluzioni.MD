| TRACCIA                                      | SOLUZIONE                                                    |
| :--------------------------------------------: | :------------------------------------------------------------: |
| Selezionare tutti gli studenti nati nel 1990 | SELECT \* FROM `students` WHERE YEAR (date_of_birth) = 1990; |
| Selezionare tutti i corsi che valgono più di 10 crediti | SELECT * FROM `courses` WHERE cfu > 10;  |
|Selezionare tutti gli studenti che hanno più di 30 anni|SELECT * FROM `students` WHERE 2024 - YEAR (date_of_birth) >= 30; |
|Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea|SELECT * FROM `courses` WHERE period LIKE 'I s%' AND year = 1; |
|Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020|SELECT * FROM `exams` WHERE TIME(`hour`) >= '14:00:00' AND date = '2020-06-20'; |
|Da quanti dipartimenti è composta l'università?| SELECT COUNT(id) FROM `departments`; |
|Quanti sono gli insegnanti che non hanno un numero di telefono?| SELECT COUNT(*) FROM `teachers` WHERE phone IS NULL; |

# GROUP BY
| TRACCIA                                      | SOLUZIONE                                                    |
| :--------------------------------------------: | :------------------------------------------------------------: |
|Contare quanti iscritti ci sono stati ogni anno| SELECT YEAR(enrolment_date), COUNT(enrolment_date) AS 'iscritti' FROM `students` GROUP BY YEAR(enrolment_date); |
|Contare gli insegnanti che hanno l'ufficio nello stesso edificio| SELECT office_address, COUNT(id) AS 'teachers' FROM `teachers` GROUP BY office_address; |
|Calcolare la media dei voti di ogni appello d'esame|SELECT exam_id, AVG(vote) AS 'everage_vote' FROM `exam_student` GROUP BY exam_id; |
|Contare quanti corsi di laurea ci sono per ogni dipartimento|SELECT department_id, COUNT(id) AS 'corso' FROM `degrees` GROUP BY department_id; |