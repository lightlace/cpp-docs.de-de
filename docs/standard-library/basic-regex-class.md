---
title: "basic_regex-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::basic_regex"
  - "basic_regex"
  - "std.tr1.basic_regex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_regex-Klasse [TR1]"
ms.assetid: 8a18c6b4-f22a-4cfd-bc16-b4267867ebc3
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# basic_regex-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Umschließt einen regulären Ausdruck.  
  
## Syntax  
  
```  
template<class Elem,  
    class RXtraits = regex_traits<Elem>,  
    class basic_regex {  
public:  
    basic_regex();  
    explicit basic_regex(const Elem *ptr,  
        flag_type flags = ECMAScript);  
    basic_regex(const Elem *ptr, size_type len,  
        flag_type flags = ECMAScript);  
    basic_regex(const basic_regex& right);  
    template<class STtraits, class STalloc>  
        explicit basic_regex(const basic_string<Elem, STtraits, STalloc>& str,  
            flag_type flags = ECMAScript);  
    template<class InIt>  
        explicit basic_regex(InIt first, InIt last,  
            flag_type flags = ECMAScript);  
  
    basic_regex& operator=(const basic_regex& right);  
    basic_regex& operator=(const Elem *ptr);  
    template<class STtraits, class STalloc>  
        basic_regex& operator=(const basic_string<Elem, STtraits, STalloc>& str);  
    basic_regex& assign(const basic_regex& right);  
    basic_regex& assign(const Elem *ptr,  
        flag_type flags = ECMAScript);  
    basic_regex& assign(const Elem *ptr, size_type len,  
        flag_type flags = ECMAScript);  
    template<class STtraits, class STalloc>  
    basic_regex& assign(const basic_string<Elem, STtraits, STalloc>& str,  
        flag_type flags = ECMAScript);  
    template<class InIt>  
        basic_regex& assign(InIt first, InIt last,  
            flag_type flags = ECMAScript);  
  
    locale_type imbue(locale_type loc);  
    locale_type getloc() const;  
    void swap(basic_regex& other) throw();  
    unsigned mark_count() const;  
    flag_type flags() const;  
  
    typedef Elem value_type;  
    typedef regex_constants::syntax_option_type flag_type;  
    typedef typename RXtraits::locale_type locale_type;  
    static const flag_type icase = regex_constants::icase;  
    static const flag_type nosubs = regex_constants::nosubs;  
    static const flag_type optimize = regex_constants::optimize;  
    static const flag_type collate = regex_constants::collate;  
    static const flag_type ECMAScript = regex_constants::ECMAScript;  
    static const flag_type basic = regex_constants::basic;  
    static const flag_type extended = regex_constants::extended;  
    static const flag_type awk = regex_constants::awk;  
    static const flag_type grep = regex_constants::grep;  
    static const flag_type egrep = regex_constants::egrep;  
private:  
    RXtraits traits;    // exposition only  
    };  
```  
  
#### Parameter  
 `Elem`  
 Der zu entsprechende Elementtyp.  
  
 `RXtraits`  
 Merkmalklasse für Elemente.  
  
## Hinweise  
 Die Vorlagenklasse beschreibt ein Objekt, das einen regulären Ausdruck enthält.  Objekte dieser Vorlagenklasse können zusammen mit geeigneten Textzeichenfolgenargumenten an die Vorlagenfunktionen [regex\_match\-Funktion](../Topic/regex_match%20Function.md), [regex\_search\-Funktion](../Topic/regex_search%20Function.md) und [regex\_replace\-Funktion](../Topic/regex_replace%20Function.md) übergeben werden, um nach Text zu suchen, der mit dem regulären Ausdruck übereinstimmt.  Es gibt zwei Spezialisierungen dieser Vorlagenklasse mit den Typdefinitionen [regex\-Typdefinition](../Topic/regex%20Typedef.md) für Elemente des Typs `char` und [wregex\-Typdefinition](../Topic/wregex%20Typedef.md) für Elemente des Typs `wchar_t`.  
  
 Das Vorlagenargument `RXtraits` beschreibt verschiedene wichtige Eigenschaften der Syntax für reguläre Ausdrücke, die von der Vorlagenklasse unterstützt werden.  Eine Klasse, die diese Merkmale des regulären Ausdrucks angibt, muss dieselbe externe Schnittstelle wie ein Objekt der Vorlagenklasse [regex\_traits\-Klasse](../standard-library/regex-traits-class.md) haben.  
  
 Einige Funktionen akzeptieren eine Operandensequenz, die einen regulären Ausdruck definiert.  Sie können eine solche Operandensequenz wie folgt angeben:  
  
 `ptr` – eine auf NULL endende Sequenz \(wie z. B. eine C\-Zeichenfolge für `Elem` des Typs `char`\), die bei `ptr` \(darf kein NULL\-Zeiger sein\) beginnt, wobei das abschließende Element der Wert `value_type()` und nicht Teil der Operandensequenz ist  
  
 `ptr`, `count` – eine Sequenz von `count`\-Elementen, die bei `ptr` \(darf kein NULL\-Zeiger sein\) beginnen  
  
 `str` – die vom `basic_string`\-Objekt `str` angegebene Sequenz  
  
 `first`, `last` – eine Sequenz von Elementen, die durch die Iteratoren `first` und `last` im Bereich `[first, last)` abgegrenzt werden  
  
 `right` – das `basic_regex`\-Objekt `right`  
  
 Diese Memberfunktionen akzeptieren auch ein `flags`\-Argument, das zusätzlich zu den vom Typ `RXtraits` beschriebenen Optionen verschiedene Optionen für die Interpretation des regulären Ausdrucks angibt.  
  
## Anforderungen  
 **Header:** \<regex\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_match\-Funktion](../Topic/regex_match%20Function.md)   
 [regex\_search\-Funktion](../Topic/regex_search%20Function.md)   
 [regex\_replace\-Funktion](../Topic/regex_replace%20Function.md)   
 [regex\-Typdefinition](../Topic/regex%20Typedef.md)   
 [wregex\-Typdefinition](../Topic/wregex%20Typedef.md)   
 [regex\_traits\-Klasse](../standard-library/regex-traits-class.md)