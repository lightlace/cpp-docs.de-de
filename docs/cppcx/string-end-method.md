---
title: "String::End-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::End"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::End"
ms.assetid: c02ad0db-d35d-45f4-9b2a-cfc76716358e
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::End-Methode
Gibt einen Zeiger nach dem Ende der aktuellen Zeichenfolge zurück.  
  
## Syntax  
  
```cpp  
  
char16* End()  
```  
  
## Rückgabewert  
 Ein Zeiger zur Übergabe des Endes der aktuellen Zeichenfolge.  
  
## Hinweise  
 End\(\) gibt Begin\(\)\+Length zurück.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** vccorlib.h  
  
## Siehe auch  
 [Platform::String\-Klasse](../cppcx/platform-string-class.md)