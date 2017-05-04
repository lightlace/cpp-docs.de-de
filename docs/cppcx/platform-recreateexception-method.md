---
title: "Platform::ReCreateException-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::ReCreateException"
dev_langs: 
  - "C++"
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::ReCreateException-Methode
Diese Methode ist nur für die interne Verwendung bestimmt und nicht für Benutzercode gedacht. Verwenden Sie stattdessen die [Exception::CreateException\-Methode](../cppcx/exception-createexception-method.md).  
  
## Syntax  
  
```vb  
static Exception^ ReCreateException(int hr)  
```  
  
#### Parameter  
  
## Eigenschaftswert\/Rückgabewert  
 Gibt eine neue Platform::Exception^ basierend auf dem angegebenen HRESULT zurück.  
  
## .NET Framework-Entsprechung  
  
## Anforderungen