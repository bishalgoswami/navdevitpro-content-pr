---
title: "RunOnClient Property"
description: Describes the RunOnClient property and provides property values and additional remarks.
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: c75899f7-b01d-407a-9961-44648116a2c8
caps.latest.revision: 6
manager: edupont
---
# RunOnClient Property
Sets whether a .NET object that is defined by a variable is run on the [!INCLUDE[nav_windows](includes/nav_windows_md.md)] or [!INCLUDE[nav_server](includes/nav_server_md.md)].  

## Applies To  
 Variables of the **DotNet** data type.  

## Property Values  
 **Yes** if you want to run the .NET object on the [!INCLUDE[nav_windows](includes/nav_windows_md.md)]; otherwise, **No**. The default is **No**.  

> [!NOTE]  
>  The [!INCLUDE[nav_web](includes/nav_web_md.md)] does not support running the .NET object on the client.  

## Remarks  
 The RunOnClient property is part of .NET interoperability in [!INCLUDE[navnowlong](includes/navnowlong_md.md)] that you can use to expand your solution using .NET assemblies. With .NET interoperability, you can call methods and properties in a class of a .NET assembly from C/AL code by defining a variable for the class. When you set the RunOnClient property to **Yes**, then the class instance that is defined by the variable is instantiated on the [!INCLUDE[nav_windows](includes/nav_windows_md.md)].  

> [!NOTE]  
>  If you set the RunOnClient property to **Yes**, then the .NET assembly that is used by the variable must be installed on the machine that is running the [!INCLUDE[nav_windows](includes/nav_windows_md.md)].  

## See Also  
 [Extending Microsoft Dynamics NAV Using Microsoft .NET Framework Interoperability](Extending-Microsoft-Dynamics-NAV-Using-Microsoft-.NET-Framework-Interoperability.md)   
 [How to: Call .NET Framework Types From C/AL Code](How-to--Call-.NET-Framework-Types-From-C-AL-Code.md)
