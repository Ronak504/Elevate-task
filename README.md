# 📚 Library Management System – SQL Project

This project implements a fully normalized **Library Management System** using SQL. It manages categories, books, authors, members, and loans — including a many-to-many relationship between books and authors.

---

## 🔹 Domain Chosen
**Library Management System** – A system to track:
- Book inventory and categories
- Author information and relationships to books
- Members and their contact information
- Book loan records including issue and return dates

---

## 🔹 Tables and Relationships

| Table         | Description |
|---------------|-------------|
| **Category**  | Stores categories/genres of books |
| **Book**      | Stores details of books, including title, author field (optional), and foreign key to category |
| **Author**    | Stores author information including name and bio |
| **BookAuthor**| Many-to-many relationship between Book and Author |
| **Member**    | Stores information about library members |
| **Loan**      | Tracks books loaned to members with issue, due, and return dates |

### 🔗 Relationships
- `Book` → `Category`: Many-to-One
- `BookAuthor` → `Book` + `Author`: Many-to-Many
- `Loan` → `Book`: Many-to-One
- `Loan` → `Member`: Many-to-One

---

## 🔹 Normalization Level

The database is normalized up to **Third Normal Form (3NF)**:
- ✅ **1NF**: All fields are atomic and unique.
- ✅ **2NF**: Non-key fields depend on the whole primary key.
- ✅ **3NF**: No transitive dependencies.

---

## 🔹 Query Highlights

### 🔎 View Loan Records with Member, Book, and Author:
```sql
SELECT 
    l.LoanID,
    m.Name AS Member,
    b.Title AS Book,
    a.Name AS Author,
    l.LoanDate,
    l.DueDate,
    l.ReturnDate
FROM Loan l
JOIN Member m ON l.MemberID = m.MemberID
JOIN Book b ON l.BookID = b.BookID
JOIN BookAuthor ba ON b.BookID = ba.BookID
JOIN Author a ON ba.AuthorID = a.AuthorID;
```

---

## 🧰 Tools Used
- MySQL for schema creation and data queries
- dbdiagram.io to visualize the ER diagram

---



---

## 📬 Author
Developed as part of a database design task for learning and practice.

