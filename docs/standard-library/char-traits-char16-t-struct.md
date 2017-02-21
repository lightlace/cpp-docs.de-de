---
title: "char_traits&lt;char16_t&gt;-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::char_traits<char16_t>"
  - "std.char_traits<char16_t>"
  - "char_traits<char16_t>"
  - "string/std::char_traits<char16_t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<char16_t>-Klasse"
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# char_traits&lt;char16_t&gt;-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Struktur, die eine Spezialisierung der Vorlagenstruktur **char\_traits \<CharType\>** auf ein Element des Typs `char16_t` ist.  
  
## Syntax  
  
```  
template<> struct char_traits<char16_t>;  
```  
  
## Hinweise  
 Spezialisierung nicht zulässig der Struktur, um Bibliotheksfunktionen nutzen, die Objekte des Typs `char16_t` bearbeiten.  
  
## Anforderungen  
 **Header:** \<Zeichenfolge\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<string\>](../standard-library/string.md)   
 [char\_traits\-Struktur](../standard-library/char-traits-struct.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)