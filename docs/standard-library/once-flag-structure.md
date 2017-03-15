---
title: "once_flag-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mutex/std::once_flag"
dev_langs: 
  - "C++"
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# once_flag-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt `struct` dar, der der Vorlagenfunktion [call\_once](../Topic/call_once%20Function.md) verwendet wird, um, dass Initialisierungscode nur einmal aufgerufen wird, sogar bei Ausführungsthreads sicherzustellen.  
  
## Syntax  
  
```cpp  
struct once_flag  
{  
   constexpr once_flag() noexcept;  
   once_flag(const once_flag&);  
   once_flag& operator=(const once_flag&);  
};  
```  
  
## Hinweise  
 `once_flag` `struct` hat nur einen Standardkonstruktor.  
  
 Objekte des Typs `once_flag` können erstellt werden, aber sie kann nicht kopiert werden.  
  
## Anforderungen  
 **Header:** mutex  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)