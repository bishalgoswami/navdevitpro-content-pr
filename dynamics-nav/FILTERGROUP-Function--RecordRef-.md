---
title: "FILTERGROUP Function (RecordRef)"
description: Details the syntax for the FILTERGROUP Function (RecordRef) which changes the filter group that is being applied to the table.
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 5825ae91-b25d-40e8-8ff3-9b4aca3317ac
caps.latest.revision: 8
---
# FILTERGROUP Function (RecordRef)
Changes the filter group that is being applied to the table. You can also use this function to return the number of the current filtergroup. You cannot return the number of the filtergroup and set a new filtergroup at the same time.  
  
## Syntax  
  
```  
  
[CurrGroup :=] RecordRef.FILTERGROUP([NewGroup])  
```  
  
#### Parameters  
 *RecordRef*  
 Type: RecordRef  
  
 The recordref that is used to identify the table.  
  
 *NewGroup*  
 Type: Integer  
  
## Property Value/Return Value  
 Type: Integer  
  
## Remarks  
 A filtergroup can contain a filter for a RecordRef that has been set earlier with SETFILTER or SETRANGE. The total filter applied is the combination of all the filters set in all the filtergroups.  
  
 This function works the same way as the [FILTERGROUP Function \(Record\)](FILTERGROUP-Function--Record-.md).  
  
## Example  
 The following example determines the filtergroup that is set on the Customer table and then changes filtergroup to 1, which is the filtergroup that is applied globally to the entire application. The code starts by opening the Customer table with a RecordRef variable. The [SETRECFILTER Function \(RecordRef\)](SETRECFILTER-Function--RecordRef-.md) sets the values in the current key of the current record as a record filter. This filter is a standard filtergroup so it has a filtergroup number of 0. Then the FILTERGROUP function returns the number for the filtergroup. This filtergroup is a standard filter so the return value is 0. This value is stored in the varOrigGroup variable and displayed in a message box. The FILTERGROUP function changes the filtergroup to 1, which is the number for the global filtergroup. The new value is stored in the varCurrGroup variable and displayed in a message box. This example requires that you create the following variables and text constants in the **C/AL Globals** window.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|MyRecordRef|RecordRef|  
|varOrigGroup|Integer|  
|varCurrGroup|Integer|  
  
|Text constant name|ENU value|  
|------------------------|---------------|  
|Text000|The original filtergroup is: %1|  
|Text001|The current filtergroup is: %1|  
  
```  
  
MyRecordRef.OPEN(DATABASE::Customer);  
MyRecordRef.SETRECFILTER;  
varOrigGroup := MyRecordRef.FILTERGROUP;  
MESSAGE(Text000, varOrigGroup);  
varCurrGroup := MyRecordRef.FILTERGROUP(1);  
MESSAGE(Text001, varCurrGroup);  
```  
  
## See Also  
 [RecordRef Data Type](RecordRef-Data-Type.md)