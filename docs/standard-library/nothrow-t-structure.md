---
title: "nothrow_t-Struktur"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "nothrow_t"
  - "std.nothrow_t"
  - "std::nothrow_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nothrow_t-Klasse"
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
caps.latest.revision: 20
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# nothrow_t-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Struktur wird als Funktionsparameter \- Operators, der verwendet, um anzugeben neu, ist, dass die Funktion einen NULL\-Zeiger zurückgeben sollte, um einen Zuordnungsfehler gemeldet, anstatt eine Ausnahme auslösen.  
  
## Syntax  
  
```  
struct std::nothrow_t {};  
```  
  
## Hinweise  
 Die Struktur hilft dem Compiler, die richtige Version des Konstruktors auszuwählen.  [nothrow](../Topic/nothrow%20\(%3Cnew%3E\).md) ist ein Synonym für Objekte des Typs `std::nothrow_t`.  
  
## Beispiel  
 Siehe [Operator neu](../Topic/operator%20new%20\(%3Cnew%3E\).md) und [Operator new &#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md) für Beispiele, wie `std::nothrow_t` als Funktionsparameter verwendet wird.  
  
## Anforderungen  
 neu **Header:** \<\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)