---
title: "OutStream.WRITETEXT Function"
description: "This article provides syntax, parameters, property/return value, and a code example of the OutStream.WRITETEXT Function."
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 063d8512-1cb8-4b18-a8f4-90ffccf382dd
caps.latest.revision: 10
---
# OutStream.WRITETEXT Function
Writes text to an OutStream object.  
  
## Syntax  
  
```  
  
[Written := ] OutStream.WriteText([Text[, Length]])  
```  
  
#### Parameters  
 *Text*  
 Type: Text or Code  
  
 The text to write. If you do not specify this, a carriage return and a line feed are written.  
  
 *Length*  
 Type: Integer  
  
 The number of characters to be written.  
  
## Property Value/Return Value  
 Type: Integer  
  
 The number of characters that were written.  
  
## Example  
 This example requires that you create the following variables.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|MyHTMLFile|File|  
|TestOutStream|OutStream|  
  
 This example also requires that the c:\\TestFiles folder exists.  
  
```  
MyHTMLFile.CREATE('c:\TestFiles\main.html');  
MyHTMLFile.CREATEOUTSTREAM(TestOutStream);  
TestOutStream.WRITETEXT('<html>');  
TestOutStream.WRITETEXT;  
TestOutStream.WRITETEXT('<head>');  
TestOutStream.WRITETEXT('<title>My Page</title>');  
TestOutStream.WRITETEXT('</head>');  
TestOutStream.WRITETEXT;  
TestOutStream.WRITETEXT('<P>Hello world!</p>');  
TestOutStream.WRITETEXT;  
TestOutStream.WRITETEXT('</html>');  
MyHTMLFile.CLOSE;  
```  
  
## See Also  
 [InStream and OutStream Data Types](InStream-and-OutStream-Data-Types.md)   
 [OutStream.WRITE Function](OutStream-WRITE-Function.md)