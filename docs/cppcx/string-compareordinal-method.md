---
title: "String::CompareOrdinal-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::CompareOrdinal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::CompareOrdinal"
ms.assetid: dd4a7acc-fd23-4f1e-af85-64b9086f63f8
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::CompareOrdinal-Methode
Vergleicht zwei `String`\-Objekte durch Auswertung der numerischen Werte der entsprechenden Zeichen in den beiden Zeichenfolgenwerten, die durch die Objekte dargestellt werden.  
  
## Syntax  
  
```cpp  
  
int CompareOrdinal(  
           String^ str1,   
           String^ str2)  
  
```  
  
#### Parameter  
 `str1`  
 Das erste String\-Objekt.  
  
 `str2`  
 Das zweite String\-Objekt.  
  
## Rückgabewert  
 Eine ganze Zahl, die die lexikalische Beziehung zwischen den beiden Vergleichswerten angibt. In der folgenden Tabelle sind die möglichen Rückgabewerte aufgelistet:  
  
|Wert|Bedingung|  
|----------|---------------|  
|\-1|`str1` ist kleiner als `str2`.|  
|0|`str1` ist gleich `str2`.|  
|1|`str1` ist größer als `str2`.|  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** vccorlib.h  
  
## Siehe auch  
 [Platform::String\-Klasse](../cppcx/platform-string-class.md)