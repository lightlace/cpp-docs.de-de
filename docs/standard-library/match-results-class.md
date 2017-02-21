---
title: "match_results-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.match_results"
  - "match_results"
  - "std::tr1::match_results"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "match_results-Klasse [TR1]"
ms.assetid: b504fdca-e5dd-429d-9960-6e27c9167fa6
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# match_results-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Enthält eine Sequenz von Teilübereinstimmungen.  
  
## Syntax  
  
```  
template<class BidIt,  
    class Alloc = allocator<typename iterator_traits<BidIt>::value_type> >  
    class match_results {  
public:  
    explicit match_results(const Alloc& alloc = Alloc());  
    match_results(const match_results& right);  
  
    match_results& operator=(const match_results& right);  
  
    difference_type position(size_type sub = 0) const;  
    difference_type length(size_type sub = 0) const;  
    string_type str(size_type sub = 0) const;  
    const_reference operator[](size_type n) const;  
  
    const_reference prefix() const;  
    const_reference suffix() const;  
    const_iterator begin() const;  
    const_iterator end() const;  
  
    template<class OutIt>  
        OutIt format(OutIt out,  
            const string_type& fmt, match_flag_type flags = format_default) const;  
    string_type format(const string_type& fmt,  
        match_flag_type flags = format_default) const;  
  
    allocator_type get_allocator() const;  
    void swap(const match_results& other) throw();  
  
    size_type size() const;  
    size_type max_size() const;  
    bool empty() const;  
  
    typedef sub_match<BidIt> value_type;  
    typedef const typename Alloc::const_reference const_reference;  
    typedef const_reference reference;  
    typedef T0 const_iterator;  
    typedef const_iterator iterator;  
    typedef typename iterator_traits<BidIt>::difference_type difference_type;  
    typedef typename Alloc::size_type size_type;  
    typedef Alloc allocator_type;  
    typedef typename iterator_traits<BidIt>::value_type char_type;  
    typedef basic_string<char_type> string_type;  
    };  
```  
  
#### Parameter  
 `BidIt`  
 Der Itertatortyp für Teilübereinstimmungen.  
  
 `Alloc`  
 Der Typ einer Zuweisung für die Speicherverwaltung.  
  
## Hinweise  
 Die Vorlagenklasse beschreibt ein Objekt, das eine nicht änderbare Sequenz von Elementen vom Typ `sub_match<BidIt>` steuert, die durch eine reguläre Ausdruckssuche generiert wurde. Jedes Element verweist auf die Untersequenz, die mit der Erfassungsgruppe übereinstimmt, die diesem Element entspricht.  
  
## Anforderungen  
 **Header:** \<regex\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<regex\>](../standard-library/regex.md)