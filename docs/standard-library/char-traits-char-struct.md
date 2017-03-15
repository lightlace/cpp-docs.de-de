---
title: "char_traits&lt;char&gt;-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "string/std::char_traits<char>"
  - "std::char_traits<char >"
  - "char_traits<char >"
  - "std.char_traits<char >"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<char>-Klasse"
ms.assetid: abd9373a-77db-4031-bf4b-f8ac15087581
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# char_traits&lt;char&gt;-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Struktur, die eine Spezialisierung der Vorlagenstruktur **char\_traits \<CharType\>** auf ein Element des Typs `char` ist.  
  
## Syntax  
  
```  
template<> struct char_traits<char>;  
```  
  
## Hinweise  
 Spezialisierung nicht zulässig der Struktur, um Bibliotheksfunktionen zu nutzen, die Objekte dieses Typs `char` bearbeiten.  
  
## Beispiel  
 Siehe die Typdefinitionen und die Memberfunktionen der Vorlagenklasse [char\_traits Klasse](../standard-library/char-traits-struct.md)\<**CharType**\> für die Beispiele, die Elemente des Typs `char` beinhalten.  
  
## Anforderungen  
 **Header:** \<Zeichenfolge\>  
  
 **Namespace:** std