---
title: '&lt;regex&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <regex>
dev_langs:
- C++
helpviewer_keywords:
- regex header
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 248e9ba676b906af62f6804f4939e04158a8e2ef
ms.openlocfilehash: 4e172f8bf72fd528027c333cf411a307aa97d786
ms.lasthandoff: 02/24/2017

---
# <a name="ltregexgt"></a>&lt;regex&gt;
Definiert eine Vorlagenklasse, um [reguläre Ausdrücke (C++)](../standard-library/regular-expressions-cpp.md) sowie einige Vorlagenklassen und Funktionen zu analysieren, um Text nach Übereinstimmungen mit einem Objekt zu durchsuchen, das einen regulären Ausdruck enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <regex>  
```  
  
## <a name="remarks"></a>Hinweise  
 Um ein Objekt für einen regulären Ausdruck zu erstellen, verwenden Sie die Vorlagenklasse [basic_regex-Klasse](../standard-library/basic-regex-class.md) oder eine ihrer Spezialisierungen, [regex](../standard-library/regex-typedefs.md#regex_typedef) und [wregex](../standard-library/regex-typedefs.md#wregex_typedef), zusammen mit den Syntaxflags des Typs [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#regex_constants__syntax_option_type).  
  
 Um Text auf Übereinstimmungen mit einem Objekt für einen regulären Ausdruck zu durchsuchen, verwenden Sie die Vorlagenfunktionen [regex_match-Funktion](../standard-library/regex-functions.md#regex_match_function) und [regex_search-Funktion](../standard-library/regex-functions.md#regex_search_function) zusammen mit den Übereinstimmungsflags des Typs [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#regex_constants__match_flag_type). Diese Funktionen geben Ergebnisse zurück, indem sie die Vorlagenklasse [match_results-Klasse](../standard-library/match-results-class.md) und deren Spezialisierungen, [cmatch](../standard-library/regex-typedefs.md#cmatch_typedef), [wcmatch](../standard-library/regex-typedefs.md#wcmatch_typedef), [smatch](../standard-library/regex-typedefs.md#smatch_typedef) und [wsmatch](../standard-library/regex-typedefs.md#wsmatch_typedef) zusammen mit der Vorlagenklasse [sub_match-Klasse](../standard-library/sub-match-class.md) und deren Spezialisierungen, [csub_match](../standard-library/regex-typedefs.md#csub_match_typedef), [wcsub_match](../standard-library/regex-typedefs.md#wcsub_match_typedef), [ssub_match](../standard-library/regex-typedefs.md#ssub_match_typedef) und [wssub_match](../standard-library/regex-typedefs.md#wssub_match_typedef) verwenden.  
  
 Um Text zu ersetzen, der mit einem Objekt für einen regulären Ausdruck übereinstimmt, verwenden Sie die Vorlagenfunktion [regex_replace-Funktion](../standard-library/regex-functions.md#regex_replace_function) zusammen mit den Übereinstimmungsflags des Typs [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#regex_constants__match_flag_type).  
  
 Um mehrere Übereinstimmungen eines Objekts für einen regulären Ausdruck zu durchlaufen, verwenden Sie die Vorlagenklassen [regex_iterator-Klasse](../standard-library/regex-iterator-class.md) und [regex_token_iterator-Klasse](../standard-library/regex-token-iterator-class.md) oder eine von deren Spezialisierungen [cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator_typedef), [sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator_typedef), [wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator_typedef), [wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator_typedef), [cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator_typedef), [sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator_typedef), [wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator_typedef) oder [wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator_typedef) zusammen mit den Übereinstimmungsflags des Typs [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#regex_constants__match_flag_type).  
  
 Um die Details der Grammatik regulärer Ausdrücke zu ändern, schreiben Sie eine Klasse, in der die Merkmale des regulären Ausdrucks implementiert sind.  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[basic_regex](../standard-library/basic-regex-class.md)|Umschließt einen regulären Ausdruck.|  
|[match_results](../standard-library/match-results-class.md)|Enthält eine Sequenz von Teilübereinstimmungen.|  
|[regex_constants](../standard-library/regex-constants-class.md)|Enthält zusammengestellte Konstanten.|  
|[regex_error](../standard-library/regex-error-class.md)|Meldet einen ungültigen regulären Ausdruck.|  
|[regex_iterator](../standard-library/regex-iterator-class.md)|Durchläuft Übereinstimmungsergebnisse.|  
|[regex_traits](../standard-library/regex-traits-class.md)|Beschreibt die Merkmale von Elementen zum Abgleichen.|  
|[regex_traits\<char>](../standard-library/regex-traits-char-class.md)|Beschreibt die Merkmale von `char` zum Abgleichen.|  
|[regex_traits<wchar_t>](../standard-library/regex-traits-wchar-t-class.md)|Beschreibt die Merkmale von `wchar_t` zum Abgleichen.|  
|[regex_token_iterator](../standard-library/regex-token-iterator-class.md)|Durchläuft Teilübereinstimmungen.|  
|[sub_match](../standard-library/sub-match-class.md)|Beschreibt eine Teilübereinstimmung.|  
  
### <a name="type-definitions"></a>Typdefinitionen  
  
|||  
|-|-|  
|[cmatch](../standard-library/regex-typedefs.md#cmatch_typedef)|Typdefinition für `char``match_results`.|  
|[cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator_typedef)|Typdefinition für `char``regex_iterator`.|  
|[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator_typedef)|Typdefinition für `char``regex_token_iterator`.|  
|[csub_match](../standard-library/regex-typedefs.md#csub_match_typedef)|Typdefinition für `char``sub_match`.|  
|[regex](../standard-library/regex-typedefs.md#regex_typedef)|Typdefinition für `char``basic_regex`.|  
|[smatch](../standard-library/regex-typedefs.md#smatch_typedef)|Typdefinition für `string``match_results`.|  
|[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator_typedef)|Typdefinition für `string``regex_iterator`.|  
|[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator_typedef)|Typdefinition für `string``regex_token_iterator`.|  
|[ssub_match](../standard-library/regex-typedefs.md#ssub_match_typedef)|Typdefinition für `string``sub_match`.|  
|[wcmatch](../standard-library/regex-typedefs.md#wcmatch_typedef)|Typdefinition für `wchar_t``match_results`.|  
|[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator_typedef)|Typdefinition für `wchar_t``regex_iterator`.|  
|[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator_typedef)|Typdefinition für `wchar_t``regex_token_iterator`.|  
|[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match_typedef)|Typdefinition für `wchar_t``sub_match`.|  
|[wregex](../standard-library/regex-typedefs.md#wregex_typedef)|Typdefinition für `wchar_t``basic_regex`.|  
|[wsmatch](../standard-library/regex-typedefs.md#wsmatch_typedef)|Typdefinition für `wstring``match_results`.|  
|[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator_typedef)|Typdefinition für `wstring``regex_iterator`.|  
|[wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator_typedef)|Typdefinition für `wstring``regex_token_iterator`.|  
|[wssub_match](../standard-library/regex-typedefs.md#wssub_match_typedef)|Typdefinition für `wstring``sub_match`.|  
  
### <a name="functions"></a>Funktionen  
  
|||  
|-|-|  
|[regex_match](../standard-library/regex-functions.md#regex_match_function)|Gleicht einen regulären Ausdruck exakt ab.|  
|[regex_replace](../standard-library/regex-functions.md#regex_replace_function)|Ersetzt übereinstimmende reguläre Ausdrücke.|  
|[regex_search](../standard-library/regex-functions.md#regex_search_function)|Sucht nach einer Übereinstimmung mit einem regulären Ausdruck.|  
|[swap](../standard-library/regex-functions.md#swap_function)|Tauscht `basic_regex`- oder `match_results`-Objekte.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator==](../standard-library/regex-operators.md#operator_eq_eq)|Vergleich von verschiedenen Objekten: gleich.|  
|[operator!=](../standard-library/regex-operators.md#operator_neq)|Vergleich von verschiedenen Objekten: ungleich.|  
|[operator<](../standard-library/regex-operators.md#operator_lt_)|Vergleich von verschiedenen Objekten: kleiner als.|  
|[operator\<=](../standard-library/regex-operators.md#operator_lt__eq)|Vergleich von verschiedenen Objekten: kleiner als oder gleich.|  
|[operator>](../standard-library/regex-operators.md#operator_gt_)|Vergleich von verschiedenen Objekten: größer als.|  
|[operator>=](../standard-library/regex-operators.md#operator_gt__eq)|Vergleich von verschiedenen Objekten: größer als oder gleich.|  
|[operator<<](../standard-library/regex-operators.md#operator_lt__lt_)|Fügt ein `sub_match`-Objekt in einem Stream ein.|  
  
## <a name="see-also"></a>Siehe auch  
[Reguläre Ausdrücke (C++)](../standard-library/regular-expressions-cpp.md)  
[regex_constants-Klasse](../standard-library/regex-constants-class.md)  
[regex_error-Klasse](../standard-library/regex-error-class.md)  
[\<regex>-Funktionen](../standard-library/regex-functions.md)  
[regex_iterator-Klasse](../standard-library/regex-iterator-class.md)  
[\<regex>-Operatoren](../standard-library/regex-operators.md)  
[regex_token_iterator-Klasse](../standard-library/regex-token-iterator-class.md)  
[regex_traits-Klasse](../standard-library/regex-traits-class.md)  
[\<regex>-Typdefinitionen](../standard-library/regex-typedefs.md)  




