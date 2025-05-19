
-- Question 1 🧑‍💼
-- Retrieve firstName, lastName, email, and officeCode from employees
-- Use INNER JOIN to include matching officeCode from offices table
SELECT 
    e.firstName,
    e.lastName,
    e.email,
    e.officeCode
FROM 
    employees e
INNER JOIN 
    offices o ON e.officeCode = o.officeCode;

-- Question 2 🛍️
-- Retrieve productName, productVendor, and productLine from products
-- Use LEFT JOIN to include productLine details from productlines
SELECT 
    p.productName,
    p.productVendor,
    p.productLine
FROM 
    products p
LEFT JOIN 
    productlines pl ON p.productLine = pl.productLine;

-- Question 3 📦
-- Retrieve orderDate, shippedDate, status, and customerNumber for first 10 orders
-- Use RIGHT JOIN to include all orders, even if no matching customer
SELECT 
    o.orderDate,
    o.shippedDate,
    o.status,
    o.customerNumber
FROM 
    customers c
RIGHT JOIN 
    orders o ON c.customerNumber = o.customerNumber
ORDER BY 
    o.orderDate
LIMIT 10;
