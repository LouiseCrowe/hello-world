# hello-world
First GitHub Repository

CREATCREATE TABLE `Product` (
  `Product ID` INT,
  `Product Name` VARCHAR2,
  `Product Descrption` VARCHAR2,
  `Price` FLOAT,
  `Quantity` INT,
  KEY `Primary` (`Product ID`)
);

CREATE TABLE `Order` (
  `Order ID` INT,
  `Customer ID` INT,
  `Product ID` INT,
  `Price` FLOAT,
  `Quantity` INT,
  `Date` DATE,
  KEY `Primary` (`Order ID`),
  KEY `Foreign` (`Customer ID`, `Product ID`)
);

CREATE TABLE `Customer` (
  `Customer ID` INT,
  `Customer First Name` VARCHAR2,
  `Customer Last Name` VARCHAR2,
  `Customer Email` VARCHAR2,
  `Customer Address` VARCHAR2,
  `Order ID` INT,
  `Payment ID` INT,
  KEY `Primary` (`Customer ID`),
  KEY `Foreign` (`Order ID`, `Payment ID`)
);

au_id JOIN titles ON titleauthor.title_id = titles.title_id WHERE titles.price > 20;

-- 6. Join authors with titles and publishers, and show only the authors who have written for more than one publisher
SELECT authors.au_id, authors.au_fname, authors.au_lname FROM authors JOIN titleauthor ON authors.au_id = titleauthor.au_id JOIN titles ON titleauthor.title_id = titles.title_id GROUP BY authors.au_id HAVING COUNT(DISTINCT titles.pub_id) > 1;

-- 7. Join authors with titles and publishers, and show the total number of titles per publisher for each author
SELECT authors.au_id, authors.au_fname, authors.au_lname, publishers.pub_name, COUNT(titles.title_id) FROM authors JOIN titleauthor ON authors.au_id = titleauthor.au_id JOIN titles ON titleauthor.title_id = titles.title_id JOIN publishers ON titles.pub_id = publishers.pub_id GROUP BY authors.au_id, publishers.pub_id;

-- 8. Join authors with titles and publishers, and show the average price of books per publisher for each author
SELECT authors.au_id, authors.au_fname, authors.au_lname, publishers.pub_name, AVG(titles.price) FROM authors JOIN titleauthor ON authors.au_id = titleauthor.au_id JOIN titles ON titleauthor.title_id = titles.title_id JOIN publishers ON titles.pub_id = publishers.pub_id GROUP BY authors.au_id, publishers.pub_id;

