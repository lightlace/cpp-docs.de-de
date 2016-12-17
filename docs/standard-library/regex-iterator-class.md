---
title: "regex_iterator-Klasse"
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
  - "std::tr1::regex_iterator"
  - "std.tr1.regex_iterator"
  - "regex_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex_iterator-Klasse [TR1]"
ms.assetid: 0cfd8fd0-5a95-4f3c-bf8e-6ef028c423d3
caps.latest.revision: 16
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# regex_iterator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Iteratorklasse für Übereinstimmungen.  
  
## Syntax  
  
```  
template<class BidIt, class Elem = iterator_traits<BidIt>::value_type,  
    class RXtraits = regex_traits<Elem> >  
        class regex_iterator {  
public:  
    typedef basic_regex<Elem, RXtraits> regex_type;  
    typedef match_results<BidIt> value_type;  
    typedef std::forward_iterator_tag iterator_category;  
    typedef std::ptrdiff_t difference_type;  
    typedef const match_results<BidIt>* pointer;  
    typedef const match_results<BidIt>& reference;  
  
    regex_iterator();  
    regex_iterator(BidIt first, BidIt last,  
        const regex_type& re,  
        regex_constants::match_flag_type f = regex_constants::match_default);  
  
    bool operator==(const regex_iterator& right);  
    bool operator!=(const regex_iterator& right);  
    const match_results<BidIt>& operator*();  
    const match_results<BidIt> *operator->();  
    regex_iterator& operator++();  
    regex_iterator& operator++(int);  
  
    BidIt begin;                            // exposition only  
    BidIt end;                              // exposition only  
    regex_type *pregex;                     // exposition only  
    regex_constants::match_flag_type flags; // exposition only  
    match_results<BidIt> match;             // exposition only  
    };  
```  
  
#### Parameter  
 `BidIt`  
 Der Itertatortyp für Teilübereinstimmungen.  
  
 `Elem`  
 Der zu entsprechende Elementtyp.  
  
 `RXtraits`  
 Merkmalklasse für Elemente.  
  
## Hinweise  
 Die Vorlagenklasse beschreibt ein Objekt mit einem konstanten Forward\-Iterator. Anschließend extrahiert sie Objekte des Typs `match_results<BidIt>` durch wiederholtes Anwenden seines regulären Ausdrucksobjekts `*pregex` auf die vom Iteratorbereich `[begin, end)` definierte Zeichenfolge.  
  
## Beispiele  
 Beispiele zu regulären Ausdrücken finden Sie in den folgenden Themen:  
  
-   [regex\_match\-Funktion](../Topic/regex_match%20Function.md)  
  
-   [regex\_replace\-Funktion](../Topic/regex_replace%20Function.md)  
  
-   [regex\_search\-Funktion](../Topic/regex_search%20Function.md)  
  
-   [swap\-Funktion](../Topic/swap%20Function%20%3Cregex%3E.md)  
  
## Anforderungen  
 **Header:** \<regex\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_iterator](../standard-library/regex-iterator-class.md)