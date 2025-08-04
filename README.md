
# 📚 Library Management System

## 🔹 Domain Chosen:
**Library Management System** — A digital system to manage books, members, book categories, and loan records. It allows tracking of which books belong to which categories, and which books are loaned to which members, along with due and return dates.

## 🔹 Tables and Relationships:

| Table     | Description |
|-----------|-------------|
| **Category** | Stores book categories like Programming, Philosophy, etc. |
| **Book**     | Contains details of each book, including title, author, and the category it belongs to. |
| **Member**   | Represents library members who can borrow books. |
| **Loan**     | Tracks the issue and return of books by members, including loan and due dates. |

### 🔗 Relationships:
- **Book → Category**: Many-to-One (Each book belongs to one category)
- **Loan → Book**: Many-to-One (Each loan refers to one book)
- **Loan → Member**: Many-to-One (Each loan is linked to one member)

## 🔹 Normalization Level:

The database schema is normalized up to **Third Normal Form (3NF)**:
- ✅ **1NF**: All attributes hold atomic (indivisible) values.
- ✅ **2NF**: Non-key attributes are fully functionally dependent on the primary key.
- ✅ **3NF**: No transitive dependency exists; all non-key attributes depend only on the primary key.

This normalization avoids redundancy and ensures data integrity.

## 🔹 Technologies Used:
- SQL (MySQL syntax)
- dbdiagram.io for ER Diagram
