---
title: "CONVERTSTR Function (Code, Text)"
description: "This document describes the CONVERTSTR function (Code, Text), which converts some characters in a string."
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 1d69a7d9-d448-4ed5-b8b6-a844305bfca4
caps.latest.revision: 10
manager: edupont
---
# CONVERTSTR Function (Code, Text)
Converts some characters in a string.  
  
## Syntax  
  
```  
  
NewString := CONVERTSTR(String, FromCharacters, ToCharacters)  
```  
  
#### Parameters  
 *String*  
 Type: Text constant or code  
  
 The string that you want to convert.  
  
 *FromCharacters*  
 Type: Text constant or code  
  
 The characters that you want to replace. This function is case-sensitive.  
  
 *ToCharacters*  
 Type: Text constant or code  
  
 The new characters with which you want to replace the *FromCharacters*. This function is case-sensitive.  
  
 The length of this string must correspond to the length of *FromCharacters*.  
  
 Each character in *FromCharacters* is replaced with the corresponding character in *ToCharacters*.  
  
## Property Value/Return Value  
 Type: Text constant or code  
  
 The converted string.  
  
## Remarks  
 The characters in the *FromCharacters* parameter are replaced by the characters in the *ToCharacters* parameter.  
  
 If the lengths of the *FromCharacters* and *ToCharacters* strings are not equal, then a run-time error occurs.  
  
 If either the *FromCharacters* or the *ToCharacters* strings are empty, then the source is returned unchanged.  
  
## Example  
 This example requires that you create the following variables and text constants in the C/AL Globals window.  
  
|Variable name|DataType|Length|  
|-------------------|--------------|------------|  
|OriginalString|Text|30|  
|FromChars|Text|30|  
|ToChars|Text|30|  
|NewString|Text|30|  
  
|Text constant|ENU value|  
|-------------------|---------------|  
|Text000|Do you want to leave without saving?|  
|Text001|lws|  
|Text002|LWS|  
|Text003|The original sentence is:\\ %1|  
|Text004|The sentence is converted to:\\ %1|  
  
```  
OriginalString := Text000;  
FromChars := Text001;  
ToChars := Text002;   
NewString := CONVERTSTR(OriginalString, FromChars, ToChars);  
MESSAGE(Text003, OriginalString);  
MESSAGE(Text004, NewString);  
```  
  
 The first message window shows:  
  
 **The original sentence is:**  
  
 **Do you want to leave without saving?**  
  
 The second message window shows:  
  
 **The sentence is converted to:**  
  
 **Do you Want to Leave Without Saving?**  
  
## See Also  
 [Code Data Type](Code-Data-Type.md)   
 [Text Data Type](Text-Data-Type.md)