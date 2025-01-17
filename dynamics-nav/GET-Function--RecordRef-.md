---
title: "GET Function (RecordRef)"
description: Describes the GET function (RecordRef) and provides syntax, parameters, return value, and an example.
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 40384312-1be2-4658-90c2-90a8f6690381
caps.latest.revision: 14
manager: edupont
---
# GET Function (RecordRef)
Gets a record based on the ID of the record.  
  
## Syntax  
  
```  
  
[Ok :=] RecordRef.GET(RecordID)  
```  
  
#### Parameters  
 *RecordRef*  
 Type: RecordRef  
  
 The RecordRef that refers to a table.  
  
 *RecordID*  
 Type: RecordID  
  
 The RecordID that contains the table number and the primary key of the table and is used to identify the record that you want to get.  
  
## Property Value/Return Value  
 Type: Boolean  
  
 **true** if the record was found; otherwise, **false**.  
  
 If you omit this optional return value and if the record cannot be found, then a run-time error occurs. If you include the return value, you must handle any errors.  
  
## Remarks  
 This function always uses the primary key for the table. It ignores any filters that are set, except security filters. Security filters are applied or ignored based on the Security Filter Mode. The current key and filters are not changed after you call this function. For more information, see [Security Filter Modes](Security-Filter-Modes.md).  
  
## Example  
 The following example opens the Customer table with the RecordRef variable, RecRef. The code assigns the first field in the table, which is the No. field, to MyFieldRef variable. The variable is assigned a value of 30000 by using the [FIELD Function \(RecordRef\)](FIELD-Function--RecordRef-.md). The [RECORDID Function \(RecordRef\)](RECORDID-Function--RecordRef-.md) retrieves the record ID of the record that has a value of 30000 in the No. field. The GET function then uses the RecID variable then to retrieves the record. This example requires that you create the following variables in the **C/AL Globals** window.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|RecRef|RecordRef|  
|MyFieldRef|FieldRef|  
|RecID|RecordID|  
  
```  
  
RecRef.OPEN(DATABASE::Customer);  
MyFieldRef := RecRef.FIELD(1);  
MyFieldRef.VALUE := '30000';  
IF RecRef.FIND('=') THEN BEGIN  
  RecID := RecRef.RECORDID;  
  RecRef.GET(RecID);  
END  
```  
  
## See Also  
 [RecordRef Data Type](RecordRef-Data-Type.md)   
 [FILTERGROUP Function \(Record\)](FILTERGROUP-Function--Record-.md)