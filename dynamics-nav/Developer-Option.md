---
title: "Developer Option"
description: "The Developer option for Microsoft Dynamics NAV 2018 installs components a developer would typically use to design applications for a customer company."
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 05cf46d7-5fe6-4cb6-929b-72f0a32db1f2
caps.latest.revision: 21
---
# Developer Option
The Developer option is available on the **Choose an installation option** page in [!INCLUDE[navnowlong](includes/navnowlong_md.md)] Setup.  

 The set of components installed with the Developer option includes components a developer would typically use in designing [!INCLUDE[navnow](includes/navnow_md.md)] applications for a customer company.  

> [!WARNING]  
>  The Developer option includes database components and the demo database. Setup cannot install the data file for a database, an .mdf file, if the destination folder or drive is compressed.  

## Installed Components

 When you choose the Developer Environment option, Setup installs the following components:  

- [!INCLUDE[nav_windows](includes/nav_windows_md.md)]  

   For more information, see [Client Types](Client-Types.md).  

- [Development Environment (C/SIDE)](Development-Environment--C-SIDE-.md).  

- [Microsoft Dynamics NAV Server](Microsoft-Dynamics-NAV-Server.md).  

- [SQL Server Database Components](SQL-Server-Database-Components.md), to which you can add the Demo database.  

- Web Server Components. For more information, see [Microsoft Dynamics NAV Web Client](Microsoft-Dynamics-NAV-Web-Client.md).  

- ClickOnce Installer Tools. For more information, see [Deploying Microsoft Dynamics NAV Using ClickOnce](Deploying-Microsoft-Dynamics-NAV-Using-ClickOnce.md).  

- [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)]. For more information, see [Comparing and Merging Application Object Source Files](Comparing-and-Merging-Application-Object-Source-Files.md).  

  You can configure the Developer option to add or remove components by choose the **Customize** link under the Developer option on the **Choose an installation** option pane.  

  Other components that you many want to consider installing include:  

- The [!INCLUDE[navnow](includes/navnow_md.md)] Help Server. For more information, see [Configuring Microsoft Dynamics NAV Help Server](Configuring-Microsoft-Dynamics-NAV-Help-Server.md).  

- [Automated Data Capture System](Automated-Data-Capture-System.md)  

- [Microsoft Office Outlook Add-In](Microsoft-Office-Outlook-Add-In.md)  

> [!NOTE]
> Starting with Dynamics NAV 2018 cumulative update 41 and Dynamics NAV 2017cumulative update 54, the prerequisite SQL Server Native Client is no longer installed by Setup or included on the installation media (DVD). This change doesn't affect the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] installation if you upgrading from an earlier version, because the prerequisite should already have been installed. However, for a clean installation of the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)], you'll have to manually install the SQL Server Native Client; otherwise, you may experience problems connecting the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] to the database. For more information about how to install this prerequisite, see [Installation Notes](deployment.md#installation-notes).

## See Also  
 [How to: Choose Components to Install](How-to--Choose-Components-to-Install.md)   
 [Client Types](Client-Types.md)
