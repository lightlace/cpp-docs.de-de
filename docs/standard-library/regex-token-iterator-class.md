---
title: "regex_token_iterator-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "regex_token_iterator"
  - "std.tr1.regex_token_iterator"
  - "std::tr1::regex_token_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex_token_iterator-Klasse [TR1]"
ms.assetid: a213ba48-8e4e-4b6b-871a-2637acf05f15
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# regex_token_iterator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Iteratorklasse für Teilübereinstimmungen.  
  
## Syntax  
  
```  
template<class BidIt, class Elem = iterator_traits<BidIt>::value_type,  
    class RXtraits = regex_traits<Elem> >  
        class regex_token_iterator {  
public:  
    typedef basic_regex<Elem, RXtraits> regex_type;  
    typedef sub_match<BidIt> value_type;  
    typedef std::forward_iterator_tag iterator_category;  
    typedef std::ptrdiff_t difference_type;  
    typedef const sub_match<BidIt> *pointer;  
    typedef const sub_match<BidIt>& reference;  
  
    regex_token_iterator();  
    regex_token_iterator(BidIt first, BidIt last,  
        const regex_type& re, int submatch = 0,  
        regex_constants::match_flag_type f = regex_constants::match_default);  
    regex_token_iterator(BidIt first, BidIt last,  
        const regex_type& re, const std::vector<int> submatches,  
        regex_constants::match_flag_type f = regex_constants::match_default);  
    template<std::size_t N>  
    regex_token_iterator(BidIt first, BidIt last,  
        const regex_type& re, const int (&submatches)[N],  
        regex_constants::match_flag_type f = regex_constants::match_default);  
  
    bool operator==(const regex_token_iterator& right);  
    bool operator!=(const regex_token_iterator& right);  
    const basic_string<Elem>& operator*();  
    const basic_string<Elem> *operator->();  
    regex_token_iterator& operator++();  
    regex_token_iterator& operator++(int);  
private:  
    regex_iterator<BidIt, Elem, RXtraits> it; // exposition only  
    vector<int> subs;                         // exposition only  
    int pos;                                  // exposition only  
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
 Die Vorlagenklasse beschreibt ein Objekt mit einem konstanten Forward\-Iterator. Vom Konzept her enthält sie ein `regex_iterator`\-Objekt, das in der Klasse verwendet wird, um in einer Zeichenfolge nach Übereinstimmungen eines regulären Ausdrucks zu suchen. In der Klasse werden Objekte des Typs `sub_match<BidIt>` extrahiert, die den Teilübereinstimmungen entsprechen, die durch die Indexwerte im gespeicherten Vektor `subs` für jede Übereinstimmung des regulären Ausdrucks gekennzeichnet sind.  
  
 Der Indexwert \-1 kennzeichnet die Zeichenfolge, die unmittelbar nach dem Ende der vorherigen Übereinstimmung des regulären Ausdrucks oder, wenn es keine vorherige Übereinstimmung eines regulären Ausdrucks gab, am Anfang der Zeichenfolge beginnt und sich, ohne es zu enthalten, bis zum ersten Zeichen der aktuellen Übereinstimmung des regulären Ausdrucks oder bis zum Ende der Zeichenfolge erstreckt, wenn es keine aktuelle Übereinstimmung gibt. Jeder andere Indexwert `idx` kennzeichnet die Inhalte der Erfassungsgruppe, die in `it.match[idx]` enthalten ist.  
  
## Anforderungen  
 **Header:** \<regex\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_token\_iterator](../standard-library/regex-token-iterator-class.md)   
 [regex\_iterator\-Klasse](../standard-library/regex-iterator-class.md)