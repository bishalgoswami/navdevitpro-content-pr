---
title: "Add Method"
ms.author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 03/28/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 620f0e32-eadc-43e9-8f6e-8fc0b12c3aaf
caps.latest.revision: 9
manager: edupont
author: SusanneWindfeldPedersen
---

# Add Method
Adds a new property to a JsonObject.

```
[Ok := ] JsonObject.Add(Key, Value)
```

## Parameters
*Key*  
Type: String

*Value*  
Type: JsonToken | JsonObject | JsonValue | JsonArray | Boolean | Char | Byte | Integer | BigInteger | Decimal | Duration | String | Date | Time | DateTime


## Return Value
Type: Boolean

**true** if the operation was successful; otherwise, **false**.

If you omit this optional return value and if the select does not execute successfully, then a run-time error occurs.

## Remarks
The operation will fail if the object already contains a property with the given key.

## See Also
[Getting Started](newdev-get-started.md)  
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)