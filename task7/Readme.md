# Task 7 – Creating and Using SQL Views

## Objective
The goal of this task is to learn how to create and use **SQL views** to simplify complex queries, enhance security, and promote reusable SQL logic.

---

## Database Schema
We use two tables:

**Customers**
| Column        | Type         |
|---------------|--------------|
| CustomerID    | INT (PK)     |
| CustomerName  | VARCHAR(100) |
| Country       | VARCHAR(50)  |

**Orders**
| Column        | Type          |
|---------------|---------------|
| OrderID       | INT (PK)      |
| OrderDate     | DATE          |
| CustomerID    | INT (FK)      |
| Amount        | DECIMAL(10,2) |

---

## Views Created

### 1. `CustomerTotalAmount`
Shows each customer along with their **total spending**.

```sql
CREATE VIEW CustomerTotalAmount AS
SELECT 
    C.CustomerID,
    C.CustomerName,
    SUM(O.Amount) AS TotalAmount
FROM Customers C
LEFT JOIN Orders O ON C.CustomerID = O.CustomerID
GROUP BY C.CustomerID, C.CustomerName;
