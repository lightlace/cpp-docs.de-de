---
title: "&lt;regex&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<regex>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex-Header [TR1]"
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# &lt;regex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert eine Vorlagenklasse, um [Reguläre Ausdrücke \(C\+\+\)](../standard-library/regular-expressions-cpp.md) zu analysieren, sowie einige Vorlagenklassen und Funktionen, um Text nach Übereinstimmungen mit einem Objekt zu durchsuchen, das einen regulären Ausdruck enthält.  
  
## Syntax  
  
```  
#include <regex>  
```  
  
## Hinweise  
 Um ein Objekt für einen regulären Ausdruck zu erstellen, verwenden Sie die Vorlagenklasse [basic\_regex\-Klasse](../standard-library/basic-regex-class.md) oder eine ihrer Spezialisierungen, [regex\-Typdefinition](../Topic/regex%20Typedef.md) und [wregex\-Typdefinition](../Topic/wregex%20Typedef.md), zusammen mit den Syntaxflags des Typs [regex\_constants::syntax\_option\_type](../Topic/regex_constants::syntax_option_type.md).  
  
 Um Text auf Übereinstimmungen mit einem Objekt für einen regulären Ausdruck zu durchsuchen, verwenden Sie die Vorlagenfunktionen [regex\_match\-Funktion](../Topic/regex_match%20Function.md) und [regex\_search\-Funktion](../Topic/regex_search%20Function.md) zusammen mit den Übereinstimmungsflags des Typs [regex\_constants::match\_flag\_type](../Topic/regex_constants::match_flag_type.md).  Diese Funktionen geben Ergebnisse zurück, indem sie die Vorlagenklasse [match\_results\-Klasse](../standard-library/match-results-class.md) und deren Spezialisierungen, [cmatch Typdefinition](../Topic/cmatch%20Typedef.md), [wcmatch\-Typdefinition](../Topic/wcmatch%20Typedef.md), [smatch Typdefinition](../Topic/smatch%20Typedef.md) und [wsmatch Typdefinition](../Topic/wsmatch%20Typedef.md), zusammen mit der Vorlagenklasse [sub\_match\-Klasse](../standard-library/sub-match-class.md) und deren Spezialisierungen, [csub\_match\-Typdefinition](../Topic/csub_match%20Typedef.md), [wcsub\_match\-Typdefinition](../Topic/wcsub_match%20Typedef.md), [ssub\_match\-Typdefinition](../Topic/ssub_match%20Typedef.md) und [wssub\_match Typdefinition](../Topic/wssub_match%20Typedef.md), verwenden.  
  
 Um Text zu ersetzen, der mit einem Objekt für einen regulären Ausdruck übereinstimmt, verwenden Sie die Vorlagenfunktion [regex\_replace\-Funktion](../Topic/regex_replace%20Function.md) zusammen mit den Übereinstimmungsflags des Typs [regex\_constants::match\_flag\_type](../Topic/regex_constants::match_flag_type.md).  
  
 Um mehrere Übereinstimmungen eines Objekts für einen regulären Ausdruck zu durchlaufen, verwenden Sie die Vorlagenklassen [regex\_iterator\-Klasse](../standard-library/regex-iterator-class.md) und [regex\_token\_iterator\-Klasse](../standard-library/regex-token-iterator-class.md) oder eine von deren Spezialisierungen, [cregex\_iterator\-Typdefinition](../Topic/cregex_iterator%20Typedef.md), [sregex\_iterator Typdefinition](../Topic/sregex_iterator%20Typedef.md), [wcregex\_iterator Typdefinition](../Topic/wcregex_iterator%20Typedef.md), [wsregex\_iterator\-Typdefinition](../Topic/wsregex_iterator%20Typedef.md), [cregex\_token\_iterator\-Typdefinition](../Topic/cregex_token_iterator%20Typedef.md), [sregex\_token\_iterator\-Typdefinition](../Topic/sregex_token_iterator%20Typedef.md), [wcregex\_token\_iterator\-Typdefinition](../Topic/wcregex_token_iterator%20Typedef.md) oder [wsregex\_token\_iterator\-Typdefinition](../Topic/wsregex_token_iterator%20Typedef.md), zusammen mit den Übereinstimmungsflags des Typs [regex\_constants::match\_flag\_type](../Topic/regex_constants::match_flag_type.md).  
  
 Um die Details der Grammatik regulärer Ausdrücke zu ändern, schreiben Sie eine Klasse, in der die Merkmale des regulären Ausdrucks implementiert sind.  
  
### Klassen  
  
|||  
|-|-|  
|[basic\_regex](../standard-library/basic-regex-class.md)|Umschließt einen regulären Ausdruck.|  
|[match\_results](../standard-library/match-results-class.md)|Enthält eine Sequenz von Teilübereinstimmungen.|  
|[regex\_constants](../standard-library/regex-constants-class.md)|Enthält zusammengestellte Konstanten.|  
|[regex\_error](../standard-library/regex-error-class.md)|Meldet einen ungültigen regulären Ausdruck.|  
|[regex\_iterator](../standard-library/regex-iterator-class.md)|Durchläuft Übereinstimmungsergebnisse.|  
|[regex\_traits](../standard-library/regex-traits-class.md)|Beschreibt die Merkmale von Elementen zum Abgleichen.|  
|[regex\_traits\<char\>](../standard-library/regex-traits-char-class.md)|Beschreibt die Merkmale von `char` zum Abgleichen.|  
|[regex\_traits\<wchar\_t\>](../standard-library/regex-traits-wchar-t-class.md)|Beschreibt die Merkmale von `wchar_t` zum Abgleichen.|  
|[regex\_token\_iterator](../standard-library/regex-token-iterator-class.md)|Durchläuft Teilübereinstimmungen.|  
|[sub\_match](../standard-library/sub-match-class.md)|Beschreibt eine Teilübereinstimmung.|  
  
### Typdefinitionen  
  
|||  
|-|-|  
|[cmatch](../Topic/cmatch%20Typedef.md)|Typdefinition für `char` `match_results`.|  
|[cregex\_iterator](../Topic/cregex_iterator%20Typedef.md)|Typdefinition für `char` `regex_iterator`.|  
|[cregex\_token\_iterator](../Topic/cregex_token_iterator%20Typedef.md)|Typdefinition für `char` `regex_token_iterator`.|  
|[csub\_match](../Topic/csub_match%20Typedef.md)|Typdefinition für `char` `sub_match`.|  
|[regex](../Topic/regex%20Typedef.md)|Typdefinition für `char` `basic_regex`.|  
|[smatch](../Topic/smatch%20Typedef.md)|Typdefinition für `string` `match_results`.|  
|[sregex\_iterator](../Topic/sregex_iterator%20Typedef.md)|Typdefinition für `string` `regex_iterator`.|  
|[sregex\_token\_iterator](../Topic/sregex_token_iterator%20Typedef.md)|Typdefinition für `string` `regex_token_iterator`.|  
|[ssub\_match](../Topic/ssub_match%20Typedef.md)|Typdefinition für `string` `sub_match`.|  
|[wcmatch](../Topic/wcmatch%20Typedef.md)|Typdefinition für `wchar_t` `match_results`.|  
|[wcregex\_iterator](../Topic/wcregex_iterator%20Typedef.md)|Typdefinition für `wchar_t` `regex_iterator`.|  
|[wcregex\_token\_iterator](../Topic/wcregex_token_iterator%20Typedef.md)|Typdefinition für `wchar_t` `regex_token_iterator`.|  
|[wcsub\_match](../Topic/wcsub_match%20Typedef.md)|Typdefinition für `wchar_t` `sub_match`.|  
|[wregex](../Topic/wregex%20Typedef.md)|Typdefinition für `wchar_t` `basic_regex`.|  
|[wsmatch](../Topic/wsmatch%20Typedef.md)|Typdefinition für `wstring` `match_results`.|  
|[wsregex\_iterator](../Topic/wsregex_iterator%20Typedef.md)|Typdefinition für `wstring` `regex_iterator`.|  
|[wsregex\_token\_iterator](../Topic/wsregex_token_iterator%20Typedef.md)|Typdefinition für `wstring` `regex_token_iterator`.|  
|[wssub\_match](../Topic/wssub_match%20Typedef.md)|Typdefinition für `wstring` `sub_match`.|  
  
### Funktionen  
  
|||  
|-|-|  
|[regex\_match](../Topic/regex_match%20Function.md)|Gleicht einen regulären Ausdruck exakt ab.|  
|[regex\_replace](../Topic/regex_replace%20Function.md)|Ersetzt übereinstimmende reguläre Ausdrücke.|  
|[regex\_search](../Topic/regex_search%20Function.md)|Sucht nach einer Übereinstimmung mit einem regulären Ausdruck.|  
|[swap](../Topic/swap%20Function%20%3Cregex%3E.md)|Tauscht `basic_regex`\- oder `match_results`\-Objekte.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator\=\=](../Topic/operator==%20%3Cregex%3E.md)|Vergleich von verschiedenen Objekten: gleich.|  
|[Operator\!\=](../Topic/operator!=%20%3Cregex%3E.md)|Vergleich von verschiedenen Objekten: ungleich.|  
|[Operator \<](../Topic/operator%3C%20%3Cregex%3E.md)|Vergleich von verschiedenen Objekten: kleiner als.|  
|[Operator \<\=](../Topic/operator%3C=%20%3Cregex%3E.md)|Vergleich von verschiedenen Objekten: kleiner als oder gleich.|  
|[Operator \>](../Topic/operator%3E%20%3Cregex%3E.md)|Vergleich von verschiedenen Objekten: größer als.|  
|[Operator \>\=](../Topic/operator%3E=%20%3Cregex%3E.md)|Vergleich von verschiedenen Objekten: größer als oder gleich.|  
|[Operator \<\<](../Topic/operator%3C%3C%20%3Cregex%3E.md)|Fügt ein `sub_match`\-Objekt in einem Stream ein.|  
  
## Siehe auch  
 [Reguläre Ausdrücke \(C\+\+\)](../standard-library/regular-expressions-cpp.md)