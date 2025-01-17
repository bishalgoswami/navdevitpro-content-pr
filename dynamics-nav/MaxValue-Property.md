---
title: "MaxValue Property"
description: "The MaxValue Property sets the maximum numeric value for a field. This article describes its application, property value, and remarks."
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: f4d4594a-ef77-4f13-989f-28912b82a3d4
caps.latest.revision: 12
manager: edupont
---
# MaxValue Property
Sets the maximum numeric value for a field.  
  
## Applies To  
  
-   Page Fields  
  
## Property Value  
  
|**Value**|**Description**|  
|---------------|---------------------|  
|**9999**|Integers|  
|**9999.0**|Decimals|  
|**December 31, 9999**|Dates|  
|**23:59:59**|Time|  
  
## Remarks  
 The field setting is checked during validation. Validation occurs only if the field or control value is updated through the UI, for example, if a value is updated on a page or if a field is updated in a table directly. If a field is updated through application code, then the **MaxValue** is not validated.  
  
## See Also  
 [MinValue Property](MinValue-Property.md)   
 [NotBlank Property](NotBlank-Property.md)   
 [Numeric Property](Numeric-Property.md)