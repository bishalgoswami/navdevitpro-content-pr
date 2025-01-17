---
title: "GETVIEW Function (Record)"
description: "The GETVIEW Function (Record) gets a string that describes the current sort order, key, and filters on a table."
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: a124767f-1311-4fe8-9312-754f7dc95719
caps.latest.revision: 16
manager: edupont
author: jswymer
---
# GETVIEW Function (Record)
Gets a string that describes the current sort order, key, and filters on a table.  
  
## Syntax  
  
```  
  
String := Record.GETVIEW([UseCaptions])  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 Specifies a record in the table for which you want to get the key and filters.  
  
 *UseCaptions*  
 Type: Boolean  
  
 Indicates whether a field caption or field number should be returned.  
  
 This parameter is optional. If this parameter is **true** \(default value\) or if it is empty, then the returned string contains references to field captions in the table with which the record is associated. If this parameter is **false**, then the returned string contains references to field numbers.  
  
## Property Value/Return Value  
 Type: Text or code  
  
 The current sort order, key, and filters on a table. The string format is the same as the [SourceTableView Property](SourceTableView-Property.md) on pages.  
  
## Remarks  
 If the [SETVIEW Function \(Record\)](SETVIEW-Function--Record-.md) has been executed, then the function will return the value that is set by **SETVIEW**.  
  
## Example  
 The following example uses the **GETVIEW** function to retrieve the key, the current sort order, and the filters that are set on the CustomerRec record in the **Customer** table. The function starts by returning the current key on which the **Customer** table is sorted. No., which is the field caption, is returned because the *UseCaptions* parameter is omitted. The key is stored in the ViewString variable and displayed in a message box. The sort key is then changed to the Name field and a filter that selects records with No. field values between 10000 and 20000 is set by using the [SETVIEW Function \(Record\)](SETVIEW-Function--Record-.md). The function returns the keys, sort order, and filter again. The return value is stored in the ViewString variable and displayed in a message box. The values that are displayed are Name, Addrees, and City, for the WHERE No.= FILTER\(10000…20000\) filter. Finally, the function displays the field numbers instead of the captions because *UseCaptions* is set to **false**. The sort order that is displayed is Field2, Field5 and Field7 instead of the field names. The filter is also displayed. This example requires that you create the following variables in the **C/AL Globals** window.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|CustomerRec|Record|Customer|  
|ViewString|Text|Not applicable|  
  
```  
ViewString := CustomerRec.GETVIEW;  
MESSAGE('The string:%1', ViewString);  
CustomerRec.SETVIEW('SORTING(Name) ORDER(Ascending) WHERE(No.=CONST(10000..20000))');  
ViewString := CustomerRec.GETVIEW;  
MESSAGE('The string:%1', ViewString);  
ViewString := CustomerRec.GETVIEW(FALSE);  
MESSAGE('The string:%1', ViewString);  
```  
  
## See Also  
 [Record Data Type](Record-Data-Type.md)
