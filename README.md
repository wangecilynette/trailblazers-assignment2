#The CREATE DATABASE creates a new database
CREATE DATABASE edu_institute;

# The CREATE TABLE creates a table alias name students 
# The student_id is set as the Primary Key for the table 
CREATE TABLE students (
student_id INT PRIMARY KEY,
name VARCHAR (50), 
age INT, 
gender CHAR (1), 
enrollment_date DATE, 
program VARCHAR (50)
);

#There are 5 records inserted with diverse information
INSERT INTO students
(name, age, gender, enrollment_dates, program) 
VALUES
('Phionah', 28, 'F', '2024-01-03', 'Computer Science')
('Lynette', 30, 'F', '2024-01-14', 'Data Science')
('Judy', 27, 'F', '2024-01-27', 'Law')
('Jane', 29, 'F', '2024-02-13', 'International Relations')
('Bosii', 31, 'M', '2024-02-18', 'Engineering');

# This query selects all columns (*) for rows where the program is "Data Science." 
SELECT * 
FROM students 
WHERE program = 'Data Science';

# This query counts all the rows in the students table and names the result column as "Total Students."
SELECT COUNT (*) 
FROM students; 

# This query will return a result with a single column named "Today's Date," containing the current date.
SELECT CURRENT_DATE, 
	CAST(NOW() AS today's_date";
    
# This query selects the student names in uppercase using the UPPER function 
# This query includes the enrollment dates on the SELECT clause
SELECT UPPER (name) AS student_names, enrollment_date
FROM students;

# This query will count the number of students in each program
# The query groups the results by program
# The query orders the result in descending order based on the count 
SELECT program, COUNT (*) AS number_of_students
FROM students 
GROUP BY program 
ORDER BY number_of_students DESC; 

# This query selects the name and age columns from the students table
# This query orders the results by age in ascending order (which means the youngest students will appear first)
# This query uses LIMIT 1 to retrieve only the youngest student's information.
SELECT name, age
FROM students 
GROUP BY name 
ORDER BY age ASC 
LIMIT 1; 
