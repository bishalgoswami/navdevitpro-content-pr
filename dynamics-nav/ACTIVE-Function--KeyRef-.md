---
title: "ACTIVE Function (KeyRef)"
description: "The ACTIVE Function (KeyRef) indicates whether the key is enabled. This article describes its syntax, property/return value, and example."
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 244d2346-f51a-444c-8de0-80a201c8ce18
caps.latest.revision: 11
manager: edupont
---
# ACTIVE Function (KeyRef)
Indicates whether the key is enabled.  
  
## Syntax  
  
```  
  
Ok := KeyRef.ACTIVE  
```  
  
#### Parameters  
 *KeyRef*  
 Type: KeyRef  
  
 The keyref that refers to a key.  
  
## Property Value/Return Value  
 Type: Boolean  
  
 **true** if the key is enabled; otherwise, **false**.  
  
## Example  
 The following example uses the `KeyRef.ACTIVE` function to determine whether a key in a record is enabled. The table with ID 18 \(the Customer table\) is open with a reference to table 18. The [KEYINDEX Function \(RecordRef\)](KEYINDEX-Function--RecordRef-.md) function retrieves the first key in the record and the `varKeyRef.ACTIVE` function returns a Boolean value that indicates whether the retrieved key is enabled. The Boolean value is displayed in a message box. This example requires that you create the following variables in the **C/AL Globals** window.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|RecRef|RecordRef|  
|varKeyRef|KeyRef|  
|IsActive|Boolean|  
  
```  
  
RecRef.OPEN(18);  
varKeyRef := RecRef.KEYINDEX(1);  
IsActive := varKeyRef.ACTIVE;  
MESSAGE('Is the key active =  %1 ', IsActive);  
```  
  
## See Also  
 [KeyRef Data Type](KeyRef-Data-Type.md)