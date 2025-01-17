---
title: "FIELDERROR Function (FieldRef)"
description: Details the syntax and code for the FIELDERROR function which stops the execution of the code, causing a run-time error, and creates an error message.
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 7df700bf-2e1f-4b64-b37d-fe2da74b3479
caps.latest.revision: 16
---
# FIELDERROR Function (FieldRef)
Stops the execution of the code, causing a run-time error, and creates an error message for a field.  
  
## Syntax  
  
```  
  
FieldRef.FIELDERROR([Text])  
```  
  
#### Parameters  
 *FieldRef*  
 Type: FieldRef  
  
 Refers to the field for which you want to create an error message.  
  
 *Text*  
 Type: Text or Code  
  
 Use this optional parameter to include the text of the error message. If this parameter is not present, default text will be used.  
  
## Remarks  
 Similar to a run-time error, this function causes any transaction to be aborted automatically.  
  
 This function is like the FIELDERROR Function for the Record data type. For examples, see [FIELDERROR Function \(Record\)](FIELDERROR-Function--Record-.md).  
  
## Example  
 The following example opens table 18 \(Customer\) as a RecordRef variable that is named CustomerRecref. The CustomerName variable is initialized with a blank text. `CustomerRecref.FIELD` creates a FieldRef that is named MyFieldRef for field1 \(No.\) and selects record 30000. Field 2 \(Name\) is then selected for record 30000. If the CustomerName variable is a blank text, then `MyFieldRef.FIELDERROR` is executed and an error message is displayed. The text in Text000 text constant is inserted into the error message that is displayed by [!INCLUDE[navnow](includes/navnow_md.md)]. This example uses the default error message. This example requires that you create the following variables and text constant in the **C/AL Globals** windows.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|CustomerRecref|RecordRef|  
|MyFieldRef|FieldRef|  
|CustomerName|Text|  
  
|Text constant|ENU value|  
|-------------------|---------------|  
|Text000|cannot be blank|  
  
```  
  
CustomerRecref.OPEN(18);  
CustomerName := '';  
MyFieldRef := CustomerRecref.FIELD(1);  
MyFieldRef.VALUE('30000');  
MyFieldRef := CustomerRecref.FIELD(2);  
IF CustomerName = '' THEN  
  MyFieldRef.FIELDERROR(Text000)  
ELSE  
  //Do some processing  
  
```  
  
 This code example displays the following error message:  
  
 **Name cannot be blank in Customer No.=”30000”.**  
  
## Programming Guidelines  
 We recommend the following guidelines for error messages:  
  
- Describe what is wrong and how to solve the problem.  
  
- Write a short descriptive message. Do not use more words than necessary.  
  
- Note that a period is automatically inserted at the end of a FIELDERROR.  
  
- Use a text constant for the *Text* parameter.  
  
  For more information, see [Progress Windows, MESSAGE, ERROR, and CONFIRM Functions](Progress-Windows--MESSAGE--ERROR--and-CONFIRM-Functions.md).  
  
## See Also  
 [FieldRef Data Type](FieldRef-Data-Type.md)