
## **Task 1**:  
Attach the screenshot with 100% on [w3schools SQL quiz](https://www.w3schools.com/sql/sql_quiz.asp).  

![Picture](https://github.com/sashaglk/Learning-SQL/blob/main/SQL%20quiz%20complete.png)

## **Task 2**:  
There is the following table:

Books  
- id (inner key)  
- title  
- author  
- year  
- publisher  

Select the books with the title containing the word "and" whose author has the name starting from "J" or "R" and the publishing year exceeds 2000.  

``SELECT *``  
``FROM Books``  
``WHERE title LIKE '%and%'``  
``    AND author BETWEEN 'J%' AND 'R%'``  
``    AND year > 2000;``  

## **Task 3**:  
There are the following tables:  

Books  
- id (inner key)  
- title  
- author_id (foreign key)  
- year  
- publisher  

Authors:  
- id (inner key)  
- name  
- surname  

Write the same query as in Task 2 on this DB scheme.  

``SELECT *``  
``FROM Books b``  
``JOIN Authors a``  
``    ON b.author_id = a.id``  
``WHERE b.title LIKE '%and%'``   
``    AND a.name BETWEEN 'J%' AND 'R%'``  
``    AND b.year > 2000;``  

## **Task 4**:  
Write a query, the same as in Task 3, but it should result in a single cell with the number of books the query returns, and that's it.  

``SELECT count(*)``  
``FROM Books b``  
``JOIN Authors a``  
``    ON b.author_id = a.id``  
``WHERE b.title LIKE '%and%'``  
``    AND a.name BETWEEN 'J%' AND 'R%'``  
``    AND b.year > 2000;``  

## **Task 5**:  
The same DB structure as in Task 3. Select names and surnames of authors that haven't published any books yet.  

``SELECT a.name, a.surname``  
``FROM Books b``  
``RIGHT JOIN Authors a``  
``    ON b.author_id = a.id``  
``WHERE b.title IS NULL;``  

## **Task 6**:  
Add at least one new record to both tables:  

- Author - Tuve Jansson  
- Book - any of your choice by Tuve Jansson, google it  

``INSERT INTO Author (name, surname)``  
``VALUES ('Tuve', 'Jansson');``  

``INSERT INTO Books (title, year, publisher)``  
``VALUES ('Kometjakten', 1946, 'Ernest Benn Ltd.');``  

## **Task 7**:  
Remove all the books from Books table written by Tuve Jansson.  

``DELETE b``  
``FROM Books b``  
``JOIN Authors a``  
``    ON b.author_id = a.id``  
``WHERE a.name = 'Tuve'``  
``    AND a.surname = 'Jansson';``  

## **Task 8**:  
Update all titles of books by Tuve Jansson to "Mumintroll Saga".  

``UPDATE b``  
``SET b.title = 'Mumintroll Saga'``  
``FROM Books b``  
``JOIN Authors a``  
``    ON b.author_id = a.id``  
``WHERE a.name = 'Tuve'``  
``    AND a.surname = 'Jansson';``  
