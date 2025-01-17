---
title: "READ Function (Query)"
description: This article describes how the READ function (Query) reads data from a row in the resulting dataset of a query.
ms.custom: na
ms.date: 06/04/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 79cd4af3-5881-47b6-aa3f-a522635d634f
caps.latest.revision: 15
manager: edupont
---
# READ Function (Query)
Reads data from a row in the resulting dataset of a query.  
  
 The following code shows the syntax of the **READ** function. *Query* is a variable of the Query data type that specifies the query object.  
  
## Syntax  
  
```  
[Ok :=] Query.READ  
```  
  
## Return Value  
 Type: Boolean  
  
 **true** if a row in the resulting dataset was retrieved; otherwise, **false**.  
  
## Remarks  
 When the **READ** function is called, the next row in the dataset query is retrieved. While in the reading state, values of columns in the row can be accessed by calling *Query.ColumnName*, where *Query* is the query type variable that specifies the query object and *ColumnName* is the column of the query.  
  
 To read a row in the dataset, you must call the **OPEN** function before the **READ** function. After the **READ** function call, columns can be accessed as shown in the following code example.  
  
```  
query.OPEN;  
query.READ;  
query.ColumnName  
  
```  
  
 You can call the **READ** function multiple times after the **OPEN** function to read consecutive rows in the dataset. The first **READ** function call retrieves the first row from the resulting dataset and each subsequent **READ** function retrieves the next row from the dataset. For example, the second **READ** function call retrieves the second row, the third **READ** function call retrieves the third row, and so on.  
  
```  
Query.OPEN;  
// Reads the first row in the dataset.  
Query.READ;   
// Accesses a column in the first row of the dataset.  
Query.ColumnName  
// Reads the second row in the dataset.  
Query.READ;   
// Accesses a column in the first row of the dataset.  
Query.ColumnName  
```  
  
> [!NOTE]  
>  If the **READ** function is called and there are no more rows in the dataset, then the **READ** function returns **false**.  
  
## Example  
 The following example demonstrates how to use the **READ** function on a query. The example code sets filters on the query, opens the query, and then reads the dataset. For each row in the dataset, a message box is displayed that contains the values of the columns in the row.  
  
 This example requires that you do the following:  
  
- Create a query called **Customer\_SalesQuantity** that is links table **18 Customer** with table  **37 Sales Lines** from the [!INCLUDE[demolong](includes/demolong_md.md)]. Include columns for the **Name** and **No.** fields from the Customer table and the **Quantity** field from Sales Lines table.  
  
   For step-by-step instructions for creating this query, see [Walkthrough: Creating a Query to Link Two Tables](Walkthrough--Creating-a-Query-to-Link-Two-Tables.md).  
  
- Create the following variable and text constant.  
  
  |Variable name|DataType|Subtype|  
  |-------------------|--------------|-------------|  
  |MyQuery|Query|Customer\_SalesQuantity|  
  
  |Text constant name|ENU Value|  
  |------------------------|---------------|  
  |Text000|Customer name = %1, Quantity = %2|  
  
  The following C/AL code opens the query, reads each row of dataset, and then displays a message that has the content of the row. You can add the code to a codeunit, and then run the codeunit to see the results.  
  
```  
// Sets a filter to display only sales quantities greater than 20.  
MyQuery.SETFILTER(Quantity, '>20');   
// Runs the query.  
MyQuery.OPEN;  
// Reads each row in the dataset and displays message with column values.  
// Stops reading when there are no more rows remaining in the dataset (READ is FALSE).  
WHILE MyQuery.READ DO  
BEGIN  
  MESSAGE(Text000, MyQuery.Name, MyQuery.Quantity);   
END;  
// Closes the query.  
MyQuery.CLOSE;  
```