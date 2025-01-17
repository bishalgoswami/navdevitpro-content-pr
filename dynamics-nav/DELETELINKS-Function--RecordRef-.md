---
title: "DELETELINKS Function (RecordRef)"
description: "The DELETELINKS Function (RecordRef) deletes all of the links that have been added to a record."
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 8caf7298-009d-47b6-ae43-3268a47f1ce2
caps.latest.revision: 10
manager: edupont
---
# DELETELINKS Function (RecordRef)
Deletes all of the links that have been added to a record.  
  
## Syntax  
  
```  
  
RecordRef.DELETELINKS  
```  
  
#### Parameters  
 *RecordRef*  
 Type: RecordRef  
  
 The record in the table where the links should be deleted from.  
  
## Example  
 The following example deletes all links from a customer record in the Customer table. The code starts by opening table 18 \(Customer\) as a RecordRef variable that is named CustomerRecref. The [FIELD Function \(RecordRef\)](FIELD-Function--RecordRef-.md) creates a FieldRef variable that is named MyFieldRef for the first field in the table \(No.\). `MyFieldRef.VALUE` selects record 01121212 from the No. field. This record is initialized in the CustomerNum variable. The [FIND Function \(RecordRef\)](FIND-Function--RecordRef-.md) searches for record 01121212. If the record is found, the DELETELINKS function deletes all the links in the record. A message that states that the links are deleted is displayed in a message box. You can verify that the links are deleted in the **Links** FactBox on the Customer List or Customer Card pages. This example requires that you create the following variables and text constants in the **C/AL Globals** window.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|CustomerNum|Integer|  
|CustomerRecref|RecordRef|  
|MyFieldRef|FieldRef|  
  
|Text constant name|DataType|ENU value|  
|------------------------|--------------|---------------|  
|Text000|Text|All the links for customer %1 have been deleted.|  
|Text001|Text|The customer cannot be found.|  
  
```  
  
CustomerNum := '01121212';  
CustomerRecref.OPEN(18);  
MyFieldRef := CustomerRecref.FIELD(1);  
MyFieldRef.VALUE := CustomerNum;  
IF CustomerRecref.FIND('=') THEN BEGIN  
  CustomerRecref.DELETELINKS;  
  MESSAGE(Text000, CustomerNum);  
END  
ELSE  
  MESSAGE(Text001);  
```  
  
## See Also  
 [RecordRef Data Type](RecordRef-Data-Type.md)