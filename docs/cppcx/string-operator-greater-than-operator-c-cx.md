---
title: "String::operator&gt;-Operator (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::operator>"
ms.assetid: d32ad538-b992-4487-a1d3-ad7ba84dbdff
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::operator&gt;-Operator (C++/CX)
Gibt an, ob der Wert eines Zeichenfolgenobjekts größer als der Wert eines zweiten Zeichenfolgenobjekts ist.  
  
## Syntax  
  
```cpp  
  
bool String::operator>( String^ str1,  
                         String^ str2)  
  
```  
  
#### Parameter  
 `str1`  
 Das erste String\-Objekt.  
  
 `str2`  
 Das zweite String\-Objekt.  
  
## Rückgabewert  
 `true`, wenn der Wert von `str1` größer als der Wert von `str2` ist, andernfalls `false`.  
  
## Hinweise  
 Dieser Operator entspricht einem expliziten Aufruf von [String::CompareOrdinal](../cppcx/string-compareordinal-method.md) bei einem Ergebnis größer als null.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** vccorlib.h  
  
## Siehe auch  
 [Platform::String\-Klasse](../cppcx/platform-string-class.md)