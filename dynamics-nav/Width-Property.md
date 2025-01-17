---
title: "Width Property"
description: Learn how the Width property sets the width of the control. Width is set as a number of characters and must be a fixed number when specified.
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 59701d5d-65f8-42e8-9b1b-8c47709cf4bc
caps.latest.revision: 22
manager: edupont
---
# Width Property
Sets the width of the control. Width is set as a number of characters and must be a fixed number when specified.  
  
## Applies To  
  
-   Page Fields  
  
-   Table Fields  
  
## Remarks  
 For controls, the width specifies the width of the column. Static controls in the heading inherit the width from the column control.  
  
 For example, use the **Width** property in the [!INCLUDE[rtc](includes/rtc_md.md)] to set decimals so that they do not take up too much space in a grid.  
  
 For controls on the [!INCLUDE[rtc](includes/rtc_md.md)] you always have the option of resizing column width in the UI, but when running the [!INCLUDE[nav_web](includes/nav_web_md.md)] the **Width** property can be set to a fixed number to increase readability.