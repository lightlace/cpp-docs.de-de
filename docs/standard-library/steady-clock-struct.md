---
title: "steady_clock-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::steady_clock"
dev_langs: 
  - "C++"
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# steady_clock-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt eine `steady` Uhr dar.  
  
## Syntax  
  
```  
struct steady_clock;  
```  
  
## Hinweise  
 Unter Windows umfasst steady\_clock QueryPerformanceCounter\-Funktion.  
  
 Eine Uhr ist *monoton,*, wenn der von einem ersten Aufruf von `now()` zurückgegebene Wert immer kleiner oder gleich dem Wert ist, der über einen nachfolgenden Aufruf von `now()` zurückgegeben wird.  
  
 Eine Uhr ist *gleichmäßig*, wenn sie *monoton* und die Zeit zwischen den Teilstrichen konstant ist.  
  
 High\_resolution\_clock ist eine Typdef für steady\_clock.  
  
## Öffentliche Funktionen  
  
|Funktion|Beschreibung|  
|--------------|------------------|  
|now|Gibt die aktuelle Uhrzeit als time\_point\-Wert zurück.|  
  
## Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|------------------|  
|`system_clock::is_steady`|Ist `true`.  Eine `steady_clock` ist *gleichmäßig*.|  
  
## Anforderungen  
 **Header:** chrono  
  
 **Namespace:** std::chrono  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)   
 [system\_clock\-Struktur](../standard-library/system-clock-structure.md)