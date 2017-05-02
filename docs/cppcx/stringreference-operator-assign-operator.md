---
title: "StringReference::operator=-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::StringReference::operator="
dev_langs: 
  - "C++"
ms.assetid: 03a33467-d65f-4508-bcb4-17d7cc99398f
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# StringReference::operator=-Operator
Weist das angegebene Objekt dem aktuellen `StringReference`\-Objekt zu.  
  
## Syntax  
  
```cpp  
  
   StringReference& operator=(const StringReference& __fstrArg);  
  
StringReference& operator=(const ::default::char16* __strArg);  
  
```  
  
#### Parameter  
 `__fstrArg`  
 Die Adresse eines `StringReference`\-Objekts, das zum Initialisieren des aktuellen `StringReference`\-Objekts verwendet wird.  
  
 `__strArg`  
 Zeiger auf ein Array von char16\-Werten das zum Initialisieren des aktuellen `StringReference`\-Objekts verwendet wird.  
  
## Rückgabewert  
 Ein Verweis auf ein Objekt des Typs `StringReference`.  
  
## Hinweise  
 Da `StringReference` eine Standard\-C\+\+\-Klasse und keine Verweisklasse ist, wird sie nicht im **Objektkatalog** geführt.  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Platform::StringReference\-Klasse](../cppcx/platform-stringreference-class.md)