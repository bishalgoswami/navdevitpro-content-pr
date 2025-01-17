---
title: "Direction Property"
description: "The Direction Property sets the XMLport to import, export, or import and export data in XML format."
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 5ba9f526-82cc-4d2b-bc82-afa34618667f
caps.latest.revision: 6
manager: edupont
---
# Direction Property
Sets the XMLport to import, export, or import and export data in XML format.  
  
## Applies To  
 XMLports  
  
## Property Value  
  
|**Value**|**Description**|  
|---------------|---------------------|  
|**Import**|The XMLPort only imports data.|  
|**Export**|The XMLPort only exports data.|  
|**Both \(default\)**|The XMLPort can import and export data.<br /><br /> If the XMLPort uses a request page, as specified by the [UseRequestPage Property](UseRequestPage-Property.md), then an option appears on the request page that enables the users to choose to import or export data. Note: request pages show when the XMLport is run from Object Designer, and action page, or the Run function in C/AL code. Dooes not show with Export Import finctions<br /><br /> If the XMLPort does not use a request, then XMLPort defaults to **Import**, unless you specify the direction by Import parameter of the run function.|  
  
## Remarks  
  
## See Also  
 [Properties](Properties.md)