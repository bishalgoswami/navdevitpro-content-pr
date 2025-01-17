---
title: "INSSTR Function (Code, Text)"
description: "This topic describes Microsoft Dynamics Nav 2018's INSSTR function (Code, Text), which inserts a substring into a string."
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 3bb8a610-9398-4e95-9b80-8ca742ab392b
caps.latest.revision: 10
manager: edupont
---
# INSSTR Function (Code, Text)
Inserts a substring into a string.  
  
## Syntax  
  
```  
  
NewString := INSSTR(String, SubString, Position)  
```  
  
#### Parameters  
 *String*  
 Type: Text constant or code  
  
 The string into which you want to insert a substring.  
  
 *SubString*  
 Type: Text constant or code  
  
 The substring that you want to insert into *String*.  
  
 *Position*  
 Type: Integer  
  
 Specifies where to insert *SubString*. *Position* must be greater than or equal to 1.  
  
 If *Position* is greater than the length of *String*, then the result is concatenated and copied to *NewString*.  
  
## Property Value/Return Value  
 Type: Text constant or code  
  
 The result after *SubString* is inserted into *String*.  
  
## Remarks  
 If *SubString* is empty, then *String* is returned unchanged.  
  
 If *Position* is less than 1, an error is returned.  
  
 If *Position* is greater than the length of *String*, *SubString* is added at the end of *String*. For example, `INSSTR("Thomas","AAA",999)` returns 'ThomasAAA'.  
  
## Example  
 This example requires that you create the following variables and text constants in the **C/AL Globals** window.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|Str|Text|60|  
|SubString|Text|60|  
|NewString|Text|60|  
  
|Text constant|ENU value|  
|-------------------|---------------|  
|Text000|Press ENTER to continue.|  
|Text001|or ESC|  
|Text002|The test string before INSSTR is called:>%1\<|  
|Text003|The resulting string after INSSTR is called:>%1\<|  
  
```  
Str := Text000;  
SubString := Text001;  
MESSAGE(Text002, Str);  
NewString := INSSTR(Str, SubString, 13);  
MESSAGE(Text003, NewString);  
```  
  
 The first message window displays the following:  
  
 **The test string before INSSTR is called:**  
  
 **>Press ENTER to continue.\<**  
  
 The second message window displays the following:  
  
 **The resulting string after INSSTR is called:**  
  
 **>Press ENTER or ESC to continue.\<**  
  
## See Also  
 [Code Data Type](Code-Data-Type.md)   
 [Text Data Type](Text-Data-Type.md)