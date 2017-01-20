---
title: "money_base-Klasse"
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
  - "locale/std::money_base"
  - "money_base"
  - "std::money_base"
  - "std.money_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "money_base-Klasse"
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
caps.latest.revision: 19
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# money_base-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Klasse beschreibt eine Enumeration und ein Strukturcommon auf alle Spezialisierungen der Vorlagenklasse [moneypunct](../standard-library/moneypunct-class.md).  
  
## Syntax  
  
```  
struct money_base : public locale::facet  
{  
    enum  
    {  
        symbol = '$',  
        sign = '+',  
        space = ' ',  
        value = 'v',  
        none = 'x'  
    };  
    typedef int part;  
    struct pattern  
    {  
        char field[_PATTERN_FIELD_SIZE];  
    };  
    money_base(  
        size_t _Refs = 0  
    );  
    ~money_base();  
};  
```  
  
## Hinweise  
 Die Enumeration **part** werden die möglichen Werte in den Elementen des Arrayfelds im Strukturmuster.  Die Werte von **part** sind:  
  
-   **keine**, von null oder mehr Leerzeichen übereinstimmt oder nichts generieren.  
  
-   **sign**, um einen positiven oder negativen Vorzeichens übereinstimmt oder zu generieren.  
  
-   **space**, von null oder mehr Leerzeichen übereinstimmt oder ein Leerzeichen generieren.  
  
-   **Symbol**, um eines Währungssymbols zu vergleichen oder zu generieren.  
  
-   **Wert**, um eines Währungswerts übereinstimmt oder zu generieren.  
  
## Anforderungen  
 **Header:** \<Gebietsschema\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)