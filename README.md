# Part 1: Insert info about Primary Keys, constraints, etc. here
# Part 2: Insert info about method of populating database here.
# Part 3: Referential constraints:
## a.i
- INSERT INTO COURSE_SECTION
VALUES(12, 2, 6, 2, 2, 'MTWRF', '10:00 AM', '11:30 AM', 5, 35);
- Error Code: 1062. Duplicate entry '12' for key 'PRIMARY'
- Constraint Violation: Primary Key of given value already exists
## a.ii
- INSERT INTO COURSE_SECTION
VALUES(12, 2, 6, 2, 2, 'MTWRF', '9:00 AM', '10:30 AM', 6, 35);
- Error Code: 1062. Duplicate entry '12' for key 'PRIMARY'
- Constraint Violation: Primary Key of given value already exists
## a.iii
- INSERT INTO COURSE_SECTION
VALUES(2, 1, 4, 2, 3, 'TR', '9:30 AM', '10:45 AM', 4, 35);
- Error Code: 1062. Duplicate entry '2' for key 'PRIMARY'
- Constraint Violation: Primary Key of given value already exists
## b.i
- INSERT INTO Faculty
VALUES(4, 'Brown', 'Colin', 'D', 11, '3253456789', 'Assistant', 4, 9871);
- Error Code: 1062. Duplicate entry '4' for key 'PRIMARY'
- Constraint Violation: Primary Key of given value already exists
## b.ii.
- INSERT INTO Faculty VALUES(6, 'Reeves', 'Bob', 'S', 15, '3256789012', 'Full',  null, 1234);
- Error Code: 1452. Cannot add or update a child row: a foreign key constraint fails (`lipscomb_final_project`.`faculty`, CONSTRAINT `faculty_ibfk_1` FOREIGN KEY (`Loc_ID`) REFERENCES `location` (`Loc_ID`))
- Constraint Violation: Foreign Key referenced does not exist
## b.iii.
- INSERT INTO Faculty VALUES(6, 'Reeves', 'Bob', 'S', 10, '3256789012', 'Assistant', 7, 1234);
- Error Code: 1452. Cannot add or update a child row: a foreign key constraint fails (`lipscomb_final_project`.`faculty`, CONSTRAINT `faculty_ibfk_2` FOREIGN KEY (`F_Super`) REFERENCES `faculty` (`F_ID`) ON DELETE SET NULL ON UPDATE CASCADE)
- Constraint Violation: Foreign Key Referenced does not exist
## b.iv.
- INSERT INTO Faculty VALUES(6, 'Reeves', 'Bob', 'S', 10, '3255678901', 'Assistant', 2, 1234);
- Error Code: ?
- Constraint Violation: ?
## c
- INSERT INTO COURSE
VALUES(4, 'CS 120', 'Intro. to Programming in C++', 3);
- Error Code: 1062. Duplicate entry '4' for key 'PRIMARY'
- Constraint Violation: Primary Key of given value already exists
## d
- DELETE FROM LOCATION WHERE Loc_ID = 11;
- Error Code: 1451. Cannot delete or update a parent row: a foreign key constraint fails (`lipscomb_final_project`.`faculty`, CONSTRAINT `faculty_ibfk_1` FOREIGN KEY (`Loc_ID`) REFERENCES `location` (`Loc_ID`))
- Constraint Violation: Loc_ID serves as parent of Faculty and cannot be deleted while a Faculty row references it
## e
- DELETE FROM TERM WHERE Term_ID = 4;
- Error Code: ?
- Constraint Violation: ?
