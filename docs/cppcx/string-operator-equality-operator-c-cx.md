---
title: "String::operator==-Operator (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::operator=="
ms.assetid: c804b269-64f9-4bc0-929b-2dfa87bf46ac
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::operator==-Operator (C++/CX)
Gibt an, ob zwei angegebene Zeichenfolgenobjekte denselben Textwert haben.  
  
## Syntax  
  
```cpp  
  
bool String::operator==( String^ str1,  
                         String^ str2)  
  
```  
  
#### Parameter  
 `str1`  
 Das erste zu vergleichende Zeichenfolgenobjekt.  
  
 `str2`  
 Das zweite zu vergleichende Zeichenfolgenobjekt.  
  
## Rückgabewert  
 `true`, wenn der Inhalt von `str1` gleich `str2` ist; andernfalls `false`.  
  
## Hinweise  
 Dieser Operator entspricht der [String::CompareOrdinal\-Methode](../cppcx/string-compareordinal-method.md).  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** vccorlib.h  
  
## Siehe auch  
 [Platform::String\-Klasse](../cppcx/platform-string-class.md)