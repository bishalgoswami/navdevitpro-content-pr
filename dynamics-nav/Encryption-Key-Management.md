---
title: "Encryption Key Management"
description: This article provides an overview of encryption key management, best practices, and ENCRYPTIONKEYEXISTS versus ENCRYPTIONENABLED.
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: f4b8f77c-a3b2-405e-8bc4-fb2168830ed3
caps.latest.revision: 3
manager: edupont
---
# Encryption Key Management
The process of encrypting and decrypting data requires a key. An encryption key is typically a random string of bits generated specifically to scramble and unscramble data. Encryption keys are created by using algorithms designed to make sure that each key is unique and unpredictable. The keys that are used by [!INCLUDE[navnow](includes/navnow_md.md)] are generated by the .NET Framework Data Protection API.  
  
 Each [!INCLUDE[navnow](includes/navnow_md.md)] tenant supports having a single encryption key. To use the encryption methods, a key must be created. There are two ways of doing this; either by importing a key or by creating a key. The **CREATEENCRYPTIONKEY** method will create an encryption key in a system that does not have a key present. Alternatively, if a key exists, you can use the **IMPORTENCRYPTIONKEY** method to introduce a key to a keyless system.  
  
> [!WARNING]  
>  **CREATEENCRYPTIONKEY** will fail if the key already exists, you must then call **DELETEENCRYPTIONKEY** to clear the state. **IMPORTENCRYPTIONKEY** will throw a warning if a key already exists, regardless of if the key is present on the system or not.  
  
## Best Practices  
 These are some best practices we recommend that you follow:  
  
-   Make sure to always backup your key and store it securely. Use the **EXPORTENCRYPTIONKEY** method and keep the output file in a secure location.  
  
-   Use the [!INCLUDE[navnow](includes/navnow_md.md)] permission system to restrict access to encryption key logic.  
  
-   Be aware of the difference between the **ENCRYPTIONKEYEXISTS** and **ENCRYPTIONENABLED** functions. For more information, see below.  
  
### ENCRYPTIONKEYEXISTS versus ENCRYPTIONENABLED  
 The encryption key is stored in a file in a directory that the [!INCLUDE[nav_server](includes/nav_server_md.md)] has access to. When a key is created or imported, data is recorded in the tenant table registering that encryption has now been enabled. Any subsequent calls to **ENCRYPTIONENABLED** will return true after the tenant table has been updated with this information. However, if the encryption file is deleted, then **ENCRYPTIONENABLED** will continue to return true. Use the **ENCRYPTIONKEYEXISTS** function to perform a file system check to see whether the key is present.  
  
## See Also  
 [Cryptography Overview](Cryptography-Overview.md)   
 [Encryption Functions](Encryption-Functions.md)