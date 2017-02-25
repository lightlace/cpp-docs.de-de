---
title: "sub_match-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sub_match"
  - "std::tr1::sub_match"
  - "std.tr1.sub_match"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sub_match-Klasse [TR1]"
ms.assetid: 804e2b9e-d16a-4c4c-ac60-024e0b2dd0e8
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# sub_match-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt eine Teilübereinstimmung.  
  
## Syntax  
  
```  
template<class BidIt>  
    class sub_match  
        : public std::pair<BidIt, BidIt> {  
public:  
    bool matched;  
    int compare(const sub_match& right) const;  
    int compare(const basic_string<value_type>& right) const;  
    int compare(const value_type *right) const;  
    difference_type length() const;  
    operator basic_string<value_type>() const;  
    basic_string<value_type> str() const;  
    typedef typename iterator_traits<BidIt>::value_type value_type;  
    typedef typename iterator_traits<BidIt>::difference_type difference_type;  
    typedef BidIt iterator;  
    };  
```  
  
#### Parameter  
 `BidIt`  
 Der Itertatortyp für Teilübereinstimmungen.  
  
## Hinweise  
 Die Vorlagenklasse beschreibt ein Objekt, das eine Folge von Zeichen kennzeichnet, die mit einer Erfassungsgruppe in einem Aufruf von [regex\_match\-Funktion](../Topic/regex_match%20Function.md) oder [regex\_search\-Funktion](../Topic/regex_search%20Function.md) übereinstimmten. Objekte des Typs [match\_results\-Klasse](../standard-library/match-results-class.md) enthalten ein Array dieser Objekte, eines für jede Erfassungsgruppe im regulären Ausdruck, der in der Suche verwendet wurde.  
  
 Gab es keine Übereinstimmung mit der Erfassungsgruppe, ist das `matched`\-Datenmember des Objekts gleich „false“, und die beiden Iteratoren `first` und `second` \(geerbt von der Basisklasse `std::pair`\) gleich sind. Gab es eine Übereinstimmung mit der Erfassungsgruppe, ist `matched` gleich „true“, der Iterator `first` zeigt auf das erste Zeichen in der Zielsequenz, die mit der Erfassungsgruppe übereinstimmte, und der Iterator `second` zeigt auf die erste Position hinter dem letzten Zeichen in der Zielsequenz, die mit der Erfassungsgruppe übereinstimmte. Für eine Übereinstimmung der Länge 0 \(null\) gilt Folgendes: Der Member `matched` enthält „true“, die beiden Iteratoren sind gleich, und beide zeigen auf die Position der Übereinstimmung.  
  
 Eine Übereinstimmung der Länge 0 \(null\) kann auftreten, wenn eine Erfassungsgruppe ausschließlich aus einer Assertion oder aus einer Wiederholung besteht, die 0 \(null\) Wiederholungen zulässt. Zum Beispiel:  
  
 „^“ stimmt mit der Zielsequenz „a“ überein; das `sub_match`\-Objekt, das der Erfassungsgruppe 0 entspricht, enthält Iteratoren, die beide auf das erste Zeichen in der Sequenz zeigen.  
  
 „b\(a\*\)b“ stimmt mit der Zielsequenz „bb“ überein; das `sub_match`\-Objekt, das der Erfassungsgruppe 1 entspricht, enthält Iteratoren, die beide auf das zweite Zeichen in der Sequenz zeigen.  
  
## Anforderungen  
 **Header:** \<regex\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<regex\>](../standard-library/regex.md)   
 [sub\_match](../standard-library/sub-match-class.md)   
 [regex\_match\-Funktion](../Topic/regex_match%20Function.md)   
 [regex\_search\-Funktion](../Topic/regex_search%20Function.md)