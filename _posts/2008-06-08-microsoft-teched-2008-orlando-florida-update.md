---
title: 'Microsoft Tech*Ed 2008, Orlando Florida (Update)'
author: admin
layout: post
permalink: /2008/06/08/microsoft-teched-2008-orlando-florida-update/
short-url:
  - http://bit.ly/dQxmpH
categories:
  - Delphi
  - Microsoft Sql Server 2008
  - science
  - technology
  - Uncategorized
  - Visual Studio 2008
tags:
  - Bill Gates
  - Data Analysis
  - MERGE
  - Microsoft
  - SQL server 2008
  - techEd 2008
  - Visual Studio 2008
---
**I predict that SQL server 2008 is going to be a huge hit.** It has been designed for performance and scalability from the start.

Some of the new features:

  * Table Valued Parameters &#8211; stored procedures will accept a table parameter.  ADO.NET has been modified so from C#, etc you can create a new variable called &#8216;**SqlDBType.Structure**&#8216; and pass this onto your stored procedures.  This is huge!  No more temporary tables, or cursors to emulate the same behavior.  
    `CREATE TYPE CustomersTableType AS TABLE (NAME VARCHAR(25), LASTNAME VARCHAR(25));<br />
CREATE PROCEDURE UpdateCustomers(@CUSTOMERS CustomersTableType REAONLY)<br />
AS<br />
BEGIN<br />
INSERT INTO CUSTOMERS (NAME, LASTNAME)<br />
SELECT NAME, LASTNAME FROM @CUSTOMERS;<br />
END;`
  * New date/time data types: date, time, and also same times but time zone aware  
    `DATE - holds date from 1/1/1 to 12/31/9999<br />
TIME - holds timeaccurate up to 100 nanoseconds<br />
DATETIMEOFFSET - time zone aware.  Stores value in UTC format<br />
DATETIME2 - holds date & time with larger precision`
  * New geo-spatial (latitude/longitude) data types -SQL server understand natively coordinates so you can create **location aware **applications.  For instance, get me all the customers within a 10 miles radius  
    <!--more-->

  * Data Analysis Services &#8211; Cubes have been enhanced &#8211; New ISO-compliant subclauses in GROUP BY clause (grouping sets, cube and rollup)
  * Multiple groupings in the same query
  * Data Analysis Services &#8211; New Tools Enhanced (Attribute Relationship Designer, Dimension Wizard and Dimension Editor)
  * new MERGE statement &#8211; Combines INSERT, UPDATE and DELETE operations based on conditional logic.  This is such a powerful statement due that it allows you to easily &#8220;merge&#8221; or synchronized two datasets.  
    `<strong>MERGE INTO</strong> CUSTOMERS C<br />
USING TransactionTable T ON T.OrderID = C.OrderID<br />
<strong>WHEN MATCHED</strong> THEN UPDATE<br />
SET C.Quantity = T.Quantity<br />
<strong>WHEN NOT MATCHED</strong> THEN INSERT (OrderID, Quantity)<br />
VALUES (T.OrderID, T.Quantity)`
  * Big performance gain and enhancements on Grouping Sets
  * New Table Types (user defined table types) &#8211; can define indexes and constraints  
    `CREATE TYPE CustomersTableType AS TABLE (NAME VARCHAR(25), LASTNAME VARCHAR(25));`
  * Common Table Expressions  (CTE)- I guess they do exist in SQL server 2005 but I was not aware of this.  You can define a pseudo table on the fly.  
    `USE AdventureWorks;<br />
GO<br />
WITH Sales_CTE (SalesPersonID, NumberOfOrders, MaxDate)<br />
AS<br />
(<br />
SELECT SalesPersonID, COUNT(*), MAX(OrderDate)<br />
FROM Sales.SalesOrderHeader<br />
GROUP BY SalesPersonID<br />
)<br />
SELECT E.EmployeeID, OS.NumberOfOrders, OS.MaxDate,<br />
E.ManagerID, OM.NumberOfOrders, OM.MaxDate<br />
FROM HumanResources.Employee AS E<br />
JOIN Sales_CTE AS OS<br />
ON E.EmployeeID = OS.SalesPersonID<br />
LEFT OUTER JOIN Sales_CTE AS OM<br />
ON E.ManagerID = OM.SalesPersonID<br />
ORDER BY E.EmployeeID;<br />
`
  * Large Use-Defined Types (UDTs) not limited to 8k like in SQL Server 2005; Analogous to VarBinary(MAX)
  * No CURSORS!! I was very surprise to see this one.  Now, it appears that if you want performance you are better off using tables variables.
  * Better store for semi-structured data
  * Multiple inserts via single INSERT statement  
    `INSERT INTO CUSTOMERS (NAME, LASTNAME) VALUES ('JOHN',SMITH'),('RAFA','NADAL'),('BILL','GATES);`
  * Variable declaration / assignment &#8211; with the DECLARE statement you will be able to declare a variable and also assign a value to it.  
    `DECLARE @NAME VARCHAR(25) = N'BILL GATES';<br />
DECLARE @I INT = 0, @J INT = 5;`

I am quite impress with all these new features.  There are even more improvements but I don&#8217;t recall all of them.  I will blog my experiences when I install the beta version of SQL server 2008 and my experiences trying to use it with Delphi.

## Related Articles:

ADO.NET Entity Framework 101</p> 

</a>