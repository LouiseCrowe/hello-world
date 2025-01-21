# hello-world
First GitHub Repository

SELECT film.title, film.language_id, language.name FROM sakila.film 
LEFT JOIN language ON film.language_id = language.language_id
ORDER BY language.language_id desc;

EXERCISE 5
This is the first edit I am going to commit.

-- 1. Join authors with titles based on au_id
SELECT * FROM authors JOIN titleauthor ON authors.au_id = titleauthor.au_id;

-- 2. Join titles with publishers and show only titles, price, and publisher name
SELECT titles.title, titles.price, publishers.pub_name FROM titles JOIN publishers ON titles.pub_id = publishers.pub_id;

-- 3. Join authors with titles and show only authors' names and titles' names
SELECT authors.au_fname, authors.au_lname, titles.title FROM authors JOIN titleauthor ON authors.au_id = titleauthor.au_id JOIN titles ON titleauthor.title_id = titles.title_id;

-- 4. Join authors with titles and show only authors who have written more than one book
SELECT authors.au_id, authors.au_fname, authors.au_lname FROM authors JOIN titleauthor ON authors.au_id = titleauthor.au_id GROUP BY authors.au_id HAVING COUNT(titleauthor.title_id) > 1;

-- 5. Join titles with publishers and authors, and show only authors who have written books with a price greater than 20
SELECT DISTINCT authors.au_id, authors.au_fname, authors.au_lname FROM authors JOIN titleauthor ON authors.au_id = titleauthor.au_id JOIN titles ON titleauthor.title_id = titles.title_id WHERE titles.price > 20;

-- 6. Join authors with titles and publishers, and show only the authors who have written for more than one publisher
SELECT authors.au_id, authors.au_fname, authors.au_lname FROM authors JOIN titleauthor ON authors.au_id = titleauthor.au_id JOIN titles ON titleauthor.title_id = titles.title_id GROUP BY authors.au_id HAVING COUNT(DISTINCT titles.pub_id) > 1;

-- 7. Join authors with titles and publishers, and show the total number of titles per publisher for each author
SELECT authors.au_id, authors.au_fname, authors.au_lname, publishers.pub_name, COUNT(titles.title_id) FROM authors JOIN titleauthor ON authors.au_id = titleauthor.au_id JOIN titles ON titleauthor.title_id = titles.title_id JOIN publishers ON titles.pub_id = publishers.pub_id GROUP BY authors.au_id, publishers.pub_id;

-- 8. Join authors with titles and publishers, and show the average price of books per publisher for each author
SELECT authors.au_id, authors.au_fname, authors.au_lname, publishers.pub_name, AVG(titles.price) FROM authors JOIN titleauthor ON authors.au_id = titleauthor.au_id JOIN titles ON titleauthor.title_id = titles.title_id JOIN publishers ON titles.pub_id = publishers.pub_id GROUP BY authors.au_id, publishers.pub_id;

