---
title: "regex_traits-Klasse"
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
  - "regex_traits"
  - "std::tr1::regex_traits"
  - "std.tr1.regex_traits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex_traits-Klasse [TR1]"
ms.assetid: bc5a5eed-32fc-4eb7-913d-71c42e729e81
caps.latest.revision: 19
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# regex_traits-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt die Merkmale von Elementen zum Abgleichen.  
  
## Syntax  
  
```  
template<class Elem>  
    struct regex_traits {  
    regex_traits();  
  
    static size_type length(const char_type *str);  
    char_type translate(char_type ch) const;  
    char_type translate_nocase(char_type ch) const;  
    template<class FwdIt>  
        string_type transform(FwdIt first, FwdIt last) const;  
    template<class FwdIt>  
        string_type transform_primary(FwdIt first, FwdIt last) const;  
    template<class FwdIt>  
        char_class_type lookup_classname(FwdIt first, FwdIt last) const;  
    template<class FwdIt>  
        string_type lookup_collatename(FwdIt first, FwdIt last) const;  
    bool isctype(char_type ch, char_class_type cls) const;  
    int value(Elem ch, int base) const;  
    locale_type imbue(locale_type loc);  
    locale_type getloc() const;  
  
    typedef Elem char_type;  
    typedef T6 size_type;  
    typedef basic_string<Elem> string_type;  
    typedef T7 locale_type;  
    typedef T8 char_class_type;  
    };  
```  
  
#### Parameter  
 `Elem`  
 Der zu beschreibende Elementtyp.  
  
## Hinweise  
 Die Vorlagenklasse beschreibt verschiedene Merkmale regulärer Ausdrücke für den Typ `Elem`. Die [basic\_regex\-Klasse](../standard-library/basic-regex-class.md)\-Vorlagenklasse verwendet diese Informationen zum Bearbeiten von Elementen des Typs `Elem`.  
  
 Jedes `regex_traits`\-Objekt enthält ein Objekt des Typs `regex_traits::locale`, das von einigen seiner Memberfunktionen verwendet wird. Das Standardgebietsschema ist eine Kopie von `regex_traits::locale()`. Die Memberfunktion `imbue` ersetzt das lokale Objekt, und die `getloc`\-Memberfunktion gibt eine Kopie des Gebietsschemaobjekts zurück.  
  
## Anforderungen  
 **Header:** \<regex\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_traits](../standard-library/regex-traits-class.md)   
 [Regex\_traits \< Char \>\-Klasse](../standard-library/regex-traits-char-class.md)   
 [regex\_traits\<wchar\_t\>\-Klasse](../standard-library/regex-traits-wchar-t-class.md)