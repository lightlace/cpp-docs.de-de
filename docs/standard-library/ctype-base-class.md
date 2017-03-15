---
title: "ctype_base-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "locale/std::ctype_base"
  - "std.ctype_base"
  - "ctype_base"
  - "std::ctype_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ctype_base-Klasse"
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# ctype_base-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Klasse dient als Basisklasse für Aspekte der Vorlagenklasse [C](../standard-library/ctype-class.md).  Eine Basisklasse für die Cklasse, die verwendet wird, um die Enumerationstypen zu definieren, die verwendet werden, um Zeichen entweder der gesamten Bereiche individuell oder innerhalb oder \- Klasse zu testen.  
  
## Syntax  
  
```  
struct ctype_base : public locale::facet  
{  
    enum  
    {  
        alnum, alpha, cntrl, digit, graph,  
        lower, print, punct, space, upper,  
        xdigit  
    };  
    typedef short mask;  
    ctype_base(  
        size_t _Refs = 0  
    );  
    ~ctype_base();  
};  
```  
  
## Hinweise  
 Sie definiert eine Enumerationsmaske.  Jede Enumerationskonstante kennzeichnet eine andere Weise, Zeichen \- Klasse, wie durch die Funktionen mit ähnlichen Namen definiert, die in der Kopfzeile \<ctype.h deklariert werden.\>  Die Konstanten sind:  
  
-   **space** \(Funktion [isspace](../Topic/isspace.md)\)  
  
-   **print** \(Funktion [isprint](../Topic/isprint.md)\)  
  
-   **cntrl** \(Funktion [iscntrl](../Topic/iscntrl.md)\)  
  
-   **upper** \(Funktion [isupper](../Topic/isupper.md)\)  
  
-   **lower** \(Funktion [islower](../Topic/islower.md)\)  
  
-   **digit** \(Funktion [isdigit](../Topic/isdigit.md)\)  
  
-   **punct** \(Funktion [ispunct](../Topic/ispunct.md)\)  
  
-   **xdigit** \(Funktion [isxdigit](../Topic/isxdigit.md)\)  
  
-   **Alpha** \(Funktion [isalpha](../Topic/isalpha.md)\)  
  
-   **alnum** \(Funktion [isalnum](../Topic/isalnum.md)\)  
  
-   **graph** \(Funktion [isgraph](../Topic/isgraph.md)\)  
  
 Sie können eine Kombination von Klassifizierungen durch O\-Ring kennzeichnen diese Konstanten.  Insbesondere ist immer true \(\=\= dass **alnumAlpha** ``&#124; **digit**\) und **graph** \(\=\=**alnum**``&#124; **punct**\).  
  
## Anforderungen  
 **Header:** \<Gebietsschema\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)