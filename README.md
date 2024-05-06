# Grouping-Data
CREATE DATABASE MyStore;

USE MyStore;

CREATE TABLE Sales (
  ProductID INT PRIMARY KEY,
  Category VARCHAR(50) NOT NULL,
  QuantitySold INT NOT NULL,
  Revenue DECIMAL(10,2) NOT NULL
);
INSERT INTO Sales (ProductID, Category, QuantitySold, Revenue)
VALUES (101, 'Electronics', 20, 1200.00),
       (102, 'Appliances', 15, 2100.00),
       (103, 'Clothing', 30, 800.00),
       (104, 'Electronics', 35, 1750.00),
       (105, 'Furniture', 10, 1500.00),
       (106, 'Appliances', 8, 1400.00),
       (107, 'Clothing', 25, 550.00);
SELECT Category, SUM(QuantitySold) AS TotalQuantitySold, SUM(Revenue) AS TotalRevenue
FROM Sales
GROUP BY Category;
SELECT Category, AVG(Revenue / QuantitySold) AS AverageRevenuePerUnit
FROM Sales
GROUP BY Category;
SELECT Category, SUM(Revenue) AS TotalRevenue
FROM Sales
GROUP BY Category
ORDER BY TotalRevenue DESC
LIMIT 1;
