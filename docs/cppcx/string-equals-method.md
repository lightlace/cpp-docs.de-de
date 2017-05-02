---
title: "String::Equals-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Equals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Equals"
ms.assetid: b0c78419-242d-4d38-93e3-ff2818412624
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Equals-Methode
Gibt an, ob die angegebene Zeichenfolge über den gleichen Wert wie das aktuelle Objekt verfügt.  
  
## Syntax  
  
```cpp  
  
bool String::Equals(Object^ str);  
  
bool String::Equals(String^ str);  
  
```  
  
#### Parameter  
 `str`  
 Das zu vergleichende Objekt.  
  
## Rückgabewert  
 `true`, wenn `str` gleich dem aktuellen Objekt ist, andernfalls `false`.  
  
## Hinweise  
 Diese Methode entspricht der [String::CompareOrdinal\-Methode](../cppcx/string-compareordinal-method.md). In der ersten Überladung wird erwartet, dass der Parameter `str` zu einem String^\-Objekt umgewandelt werden kann.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** vccorlib.h  
  
## Siehe auch  
 [Platform::String\-Klasse](../cppcx/platform-string-class.md)