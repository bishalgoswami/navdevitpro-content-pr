---
title: "GETPOSITION Function (Record)"
description: Describes the GETPOSITION function (record) and provides syntax, parameters, return value, and an example.
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 5a5f7b8b-d893-440d-bf2b-8d4e75d96b9c
caps.latest.revision: 14
author: jswymer
---
# GETPOSITION Function (Record)
Gets a string that contains the primary key of the current record.  
  
## Syntax  
  
```  
  
String := Record.GETPOSITION([UseCaptions])  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 The record that contains the primary key.  
  
 *UseCaptions*  
 Type: Boolean 
 
 Indicates whether a reference to the field caption or the field number should be returned.  
 
 The *UseCaptions* parameter is optional. If it is set to **true** \(default value\) or if it is empty, then the returned string contains references to field captions in the table with which the record is associated. If the parameter is set to **false**, then field numbers are used instead.  
  
## Property Value/Return Value  
 Type: Text or code  
  
 The primary key of the current record. The string has the same format as the [SourceTable Property](SourceTable-Property.md) on a page.  
  
## Example  
 The following example uses the **GETPOSITION** function to retrieve the primary key of the current record \(MyRecord\) from the **Customer** table. The primary key is stored in the varPrimaryKey variable and displayed in a message box. This example requires that you create the following variables in the **C/AL Globals** window.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|MyRecord|Record|Customer|  
|varPrimaryKey|Text|Not applicable|  
  
```  
varPrimaryKey := MyRecord.GETPOSITION(TRUE);  
MESSAGE(varPrimaryKey);  
```  
  
## See Also  
 [Record Data Type](Record-Data-Type.md)