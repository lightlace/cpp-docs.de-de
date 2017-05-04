---
title: "Type::GetTypeCode-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Type::GetTypeCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Type::GetTypeCode-Methode"
ms.assetid: 20c30432-91a3-400e-b9d6-eba265daaefc
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Type::GetTypeCode-Methode
Ruft einen der eingebauten Typen aus der Kategorie der numerischen Typen ab.  
  
## Syntax  
  
```cpp  
Platform::TypeCode GetTypeCode();  
```  
  
## Rückgabewert  
 Einer der Platform::TypeCode\-Enumierationswerte.  
  
## Hinweise  
 Das Äquivalent der GetTypeCode\(\)\-Membermethode ist die `typeid`\-Eigenschaft.  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Platform::ValueType\-Klasse](../cppcx/platform-valuetype-class.md)