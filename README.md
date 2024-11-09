# SQL
В рамках домашнего задания мной были созданы следующие запросы к MySQL.

1. Выведите имя, фамилию, патронуса всех персонажей, у которых есть patronus и он известен.
   SELECT fname, lname, patronus
   FROM characters
   WHERE patronus IS NOT NULL AND patronus <> '';


3. Выведите фамилию персонажей, у которых последняя буква в фамилии ‘e’.
   SELECT lname
   FROM characters
   WHERE lname LIKE '%e';


5. Посчитайте общий возраст всех персонажей и выведите это на экран.
   SELECT SUM(age) AS total_age
   FROM characters;


7. Выведите имя, фамилию и возраст персонажей по убыванию их возраста.
   SELECT fname, lname, age
   FROM characters
   ORDER BY age DESC;


9. Выведите имя персонажа и возраст, у которых последний находится в диапазоне от 50 до 100 лет.
    SELECT fname, age
    FROM characters
    WHERE age BETWEEN 50 AND 100;


11. Выведите возраст всех персонажей так, чтобы среди них не было тех, у кого он одинаковый.
    SELECT DISTINCT age
    FROM characters;



12. Используя оператор CASE опишите следующую логику:
Выведите имя и фамилию персонажа, а также следующий текстовое сообщение:

Если факультет Gryffindor, то в консоли должно вывестись Godric
Если факультет Slytherin, то в консоли должно вывестись Salazar
Если факультет Ravenclaw, то в консоли должно вывестись Rowena
Если факультет Hufflepuff, то в консоли должно вывестись Helga
Если другая информация, то выводится Muggle

Для сообщения используйте псевдоним Founders.

SELECT fname, lname,
	CASE
		WHEN faculty = 'Gryffindor' THEN 'Godric'
		WHEN faculty = 'Slytherin' THEN 'Salazar'
		WHEN faculty = 'Ravenclaw' THEN 'Rowena'
		WHEN faculty = 'Hufflenpuff' THEN 'Helga'
		ELSE 'Muggle'
        END AS Founders
FROM characters;


13. Используя регулярное выражение найдите фамилии персонажей, которые не начинаются с букв H, L или S и выведите их.
    FROM characters
    WHERE lname REGEXP '^[^HLS].*';







