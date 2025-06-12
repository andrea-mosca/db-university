1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql
SELECT `students`.*
FROM `degrees`

INNER JOIN `students`
ON `degrees`.`id` = `students`.`degree_id`

WHERE `degrees`.`name` = "Corso di Laurea in Economia";
```

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
   Neuroscienze

```sql
SELECT `degrees`.*
FROM `departments`

INNER JOIN `degrees`
ON `departments`.`id`=`degrees`.`department_id`

WHERE `departments`.`name`= "Dipartimento di Neuroscienze" AND `degrees`.`level`= "magistrale";
```

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql
SELECT `courses`.*
FROM `teachers`

INNER JOIN `course_teacher`
ON `teachers`.`id`=`course_teacher`.`teacher_id`

INNER JOIN `courses`
ON `courses`.`id`=`course_teacher`.`course_id`

WHERE `teachers`.`id`= 44;
```

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
   sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
   nome

```sql
SELECT `students`.*,
`departments`.`name` AS `department_name`,
`degrees`.`id` AS `degree_id`,
`degrees`.`name` AS `degree_name`,
`degrees`.`level` AS `degree_level`,
`degrees`.`address` AS `degree_address`,
`degrees`.`email` AS `degree_email`,
`degrees`.`website` AS `degree_website`

FROM `students`

INNER JOIN `degrees`
ON `students`.`degree_id`=`degrees`.`id`

INNER JOIN `departments`
ON `departments`.`id`=`degrees`.`department_id`

ORDER BY `students`.`surname`, `students`.`name`
```

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```sql
SELECT `degrees`.*,
`courses`.`id` AS `course_id`,
`courses`.`name` AS `course_name`,
`courses`.`cfu` AS `course_cfu`,
`courses`.`website` AS `course_website`,
`teachers`.`name` AS `teacher_name`
FROM `degrees`

INNER JOIN `courses`
ON `degrees`.`id`= `courses`.`degree_id`

INNER JOIN `course_teacher`
ON `courses`.`id`= `course_teacher`.`course_id`

INNER JOIN `teachers`
ON `teachers`.`id`= `course_teacher`.`teacher_id`
```

6. Selezionare tutti i docenti che insegnano nel Dipartimento di
   Matematica (54)

```sql

```

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
   per ogni esame, stampando anche il voto massimo. Successivamente,
   filtrare i tentativi con voto minimo 18

```sql

```
