---
title: "char_traits&lt;char32_t&gt;-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "string/std::char_traits<char_32t>"
  - "char_traits<char32_t>"
  - "std.char_traits<char_32t>"
  - "std::char_traits<char_32t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<char32_t>-Klasse"
ms.assetid: c0315466-45d0-4a99-b83e-3b1dbfbfbbc3
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# char_traits&lt;char32_t&gt;-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Struktur, die eine Spezialisierung der Vorlagenstruktur **char\_traits \<CharType\>** auf ein Element des Typs `char32_t` ist.  
  
## Syntax  
  
```  
template<> struct char_traits<char32_t>;  
```  
  
## Hinweise  
 Spezialisierung nicht zulässig der Struktur, um Bibliotheksfunktionen zu nutzen, die Objekte dieses Typs `char32_t` bearbeiten.  
  
## Anforderungen  
 **Header:** \<Zeichenfolge\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<string\>](../standard-library/string.md)   
 [char\_traits\-Struktur](../standard-library/char-traits-struct.md)