create database project;
SELECT 
    OrderID,
    Sales_date,
    Productkey,
    CustomerID,
    Quantity,
    OrderStatus,
    Location,
    Discount_Band_Applied
FROM 
    transactions;
select * from transaction project;
DESCRIBE transactions;
ALTER TABLE transactions
CHANGE COLUMN Discount_Band_Applied Discount_Band_Applied text;
DROP TABLE transactions;
SELECT * FROM project.`transaction project`;
SELECT 
    OrderID,
    Sales_date,
    Productkey,
    CustomerID,
    Quantity,
    OrderStatus,
    Location,
    Discount_Band_Applied,
    OrderValueCategory
FROM 
    project.`transaction project`;
    

    
    ALTER TABLE project.`transaction project`
ADD OrderValueCategory VARCHAR(50);

UPDATE project.`transaction project`
SET OrderValueCategory = CASE
    WHEN Quantity > 75 THEN 'High Value Orders'
    WHEN Quantity <= 75 AND Quantity >= 40 THEN 'Average Value Orders'
    WHEN Quantity < 40 THEN 'Low Value Orders'
END;
