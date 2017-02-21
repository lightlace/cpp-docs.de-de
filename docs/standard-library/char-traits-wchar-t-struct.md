---
title: "char_traits&lt;wchar_t&gt;-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.char_traits<wchar_t>"
  - "char_traits<wchar_t>"
  - "string/std::char_traits<wchar_t>"
  - "std::char_traits<wchar_t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<wchar_t>-Klasse"
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# char_traits&lt;wchar_t&gt;-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Klasse, die eine Spezialisierung der Vorlagenstruktur **char\_traits \<CharType\>** auf ein Element des Typs `wchar_t` ist.  
  
## Syntax  
  
```  
template<> struct char_traits<wchar_t>;  
```  
  
## Hinweise  
 Spezialisierung nicht zulässig der Struktur, um Bibliotheksfunktionen zu nutzen, die Objekte dieses Typs `wchar_t` bearbeiten.  
  
## Anforderungen  
 **Header:** \<Zeichenfolge\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [char\_traits\-Struktur](../standard-library/char-traits-struct.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)