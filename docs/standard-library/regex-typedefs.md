---
title: '&lt;regex&gt;-Typdefinition | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cmatch
- std::cmatch
- regex/std::cmatch
- cregex_iterator
- std::cregex_iterator
- regex/std::cregex_iterator
- cregex_token_iterator
- std::cregex_token_iterator
- regex/std::cregex_token_iterator
- csub_match
- std::csub_match
- regex/std::csub_match
- regex
- std::regex
- regex/std::regex
- smatch
- std::smatch
- regex/std::smatch
- sregex_iterator
- std::sregex_iterator
- regex/std::sregex_iterator
- sregex_token_iterator
- std::sregex_token_iterator
- regex/std::sregex_token_iterator
- ssub_match
- std::ssub_match
- regex/std::ssub_match
- wcmatch
- std::wcmatch
- regex/std::wcmatch
- wcregex_iterator
- std::wcregex_iterator
- regex/std::wcregex_iterator
- wcregex_token_iterator
- std::wcregex_token_iterator
- regex/std::wcregex_token_iterator
- wcsub_match
- std::wcsub_match
- regex/std::wcsub_match
- wregex
- std::wregex
- regex/std::wregex
- wsmatch
- std::wsmatch
- regex/std::wsmatch
- wsregex_iterator
- std::wsregex_iterator
- regex/std::wsregex_iterator
- wsregex_token_iterator
- std::wsregex_token_iterator
- regex/std::wsregex_token_iterator
- wssub_match
- std::wssub_match
- regex/std::wssub_match
ms.assetid: e6a69067-106c-4a24-9e08-7c867a3a2260
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 60822dd232399b27ccda3db829b636d817091a2d
ms.lasthandoff: 02/24/2017

---
# <a name="ltregexgt-typedefs"></a>&lt;regex&gt;-Typdefinitionen
||||  
|-|-|-|  
|[cmatch-Typdefinition](#cmatch_typedef)|[cregex_iterator-Typdefinition](#cregex_iterator_typedef)|[cregex_token_iterator-Typdefinition](#cregex_token_iterator_typedef)|  
|[csub_match-Typdefinition](#csub_match_typedef)|[regex-Typdefinition](#regex_typedef)|[smatch-Typdefinition](#smatch_typedef)|  
|[sregex_iterator-Typdefinition](#sregex_iterator_typedef)|[sregex_token_iterator-Typdefinition](#sregex_token_iterator_typedef)|[ssub_match-Typdefinition](#ssub_match_typedef)|  
|[wcmatch-Typdefinition](#wcmatch_typedef)|[wcregex_iterator-Typdefinition](#wcregex_iterator_typedef)|[wcregex_token_iterator-Typdefinition](#wcregex_token_iterator_typedef)|  
|[wcsub_match-Typdefinition](#wcsub_match_typedef)|[wregex-Typdefinition](#wregex_typedef)|[wsmatch-Typdefinition](#wsmatch_typedef)|  
|[wsregex_iterator-Typdefinition](#wsregex_iterator_typedef)|[wsregex_token_iterator-Typdefinition](#wsregex_token_iterator_typedef)|[wssub_match-Typdefinition](#wssub_match_typedef)|  
  
##  <a name="a-namecmatchtypedefa--cmatch-typedef"></a><a name="cmatch_typedef"></a> cmatch-Typdefinition  
 Die Typdefinition für „char match_results“.  
  
```  
typedef match_results<const char*> cmatch;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [match_results-Klasse](../standard-library/match-results-class.md) für Iteratoren des Typs `const char*`.  
  
##  <a name="a-namecregexiteratortypedefa--cregexiterator-typedef"></a><a name="cregex_iterator_typedef"></a> cregex_iterator-Typdefinition  
 Typdefinition für char regex_iterator.  
  
```  
typedef regex_iterator<const char*> cregex_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [regex_iterator-Klasse](../standard-library/regex-iterator-class.md) für Iteratoren des Typs `const char*`.  
  
##  <a name="a-namecregextokeniteratortypedefa--cregextokeniterator-typedef"></a><a name="cregex_token_iterator_typedef"></a> cregex_token_iterator-Typdefinition  
 Typdefinition für char regex_token_iterator  
  
```  
typedef regex_token_iterator<const char*> cregex_token_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [regex_token_iterator-Klasse](../standard-library/regex-token-iterator-class.md) für Iteratoren des Typs `const char*`.  
  
##  <a name="a-namecsubmatchtypedefa--csubmatch-typedef"></a><a name="csub_match_typedef"></a> csub_match-Typdefinition  
 Die Typdefinition für „char sub_match“.  
  
```  
typedef sub_match<const char*> csub_match;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [sub_match-Klasse](../standard-library/sub-match-class.md) für Iteratoren des Typs `const char*`.  
  
##  <a name="a-nameregextypedefa--regex-typedef"></a><a name="regex_typedef"></a> regex-Typdefinition  
 Die Typdefinition für „char basic_regex“.  
  
```  
typedef basic_regex<char> regex;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [basic_regex-Klasse](../standard-library/basic-regex-class.md) für Iteratoren des Typs `char`.  
  
> [!NOTE]
>  High Bit-Zeichen werden bei `regex` unvorhersehbare Ergebnisse haben. Werte außerhalb des Bereichs von 0 bis 127 können zu nicht definiertem Verhalten führen.  
  
##  <a name="a-namesmatchtypedefa--smatch-typedef"></a><a name="smatch_typedef"></a> smatch-Typdefinition  
 Die Typdefinition für „string match_results“.  
  
```  
typedef match_results<string::const_iterator> smatch;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [match_results-Klasse](../standard-library/match-results-class.md) für Iteratoren des Typs `string::const_iterator`.  
  
##  <a name="a-namesregexiteratortypedefa--sregexiterator-typedef"></a><a name="sregex_iterator_typedef"></a> sregex_iterator-Typdefinition  
 Die Typdefinition für „string regex_iterator“.  
  
```  
typedef regex_iterator<string::const_iterator> sregex_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [regex_iterator-Klasse](../standard-library/regex-iterator-class.md) für Iteratoren des Typs `string::const_iterator`.  
  
##  <a name="a-namesregextokeniteratortypedefa--sregextokeniterator-typedef"></a><a name="sregex_token_iterator_typedef"></a> sregex_token_iterator-Typdefinition  
 Typdefinition für string regex_token_iterator.  
  
```  
typedef regex_token_iterator<string::const_iterator> sregex_token_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [regex_token_iterator-Klasse](../standard-library/regex-token-iterator-class.md) für Iteratoren des Typs `string::const_iterator`.  
  
##  <a name="a-namessubmatchtypedefa--ssubmatch-typedef"></a><a name="ssub_match_typedef"></a> ssub_match-Typdefinition  
 Die Typdefinition für „string sub_match“.  
  
```  
typedef sub_match<string::const_iterator> ssub_match;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [sub_match-Klasse](../standard-library/sub-match-class.md) für Iteratoren des Typs `string::const_iterator`.  
  
##  <a name="a-namewcmatchtypedefa--wcmatch-typedef"></a><a name="wcmatch_typedef"></a> wcmatch-Typdefinition  
 Die Typdefinition für „wchar match_results“.  
  
```  
typedef match_results<const wchar_t *> wcmatch;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [match_results-Klasse](../standard-library/match-results-class.md) für Iteratoren des Typs `const wchar_t*`.  
  
##  <a name="a-namewcregexiteratortypedefa--wcregexiterator-typedef"></a><a name="wcregex_iterator_typedef"></a> wcregex_iterator-Typdefinition  
 Die Typdefinition für „wchar_t regex_iterator“.  
  
```  
typedef regex_iterator<const wchar_t*> wcregex_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [regex_iterator-Klasse](../standard-library/regex-iterator-class.md) für Iteratoren des Typs `const wchar_t*`.  
  
##  <a name="a-namewcregextokeniteratortypedefa--wcregextokeniterator-typedef"></a><a name="wcregex_token_iterator_typedef"></a> wcregex_token_iterator-Typdefinition  
 Die Typdefinition für „wchar_t regex_token_iterator“.  
  
```  
typedef regex_token_iterator<const wchar_t*> wcregex_token_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [regex_token_iterator-Klasse](../standard-library/regex-token-iterator-class.md) für Iteratoren des Typs `const wchar_t*`.  
  
##  <a name="a-namewcsubmatchtypedefa--wcsubmatch-typedef"></a><a name="wcsub_match_typedef"></a> wcsub_match-Typdefinition  
 Die Typdefinition für „wchar_t sub_match“.  
  
```  
typedef sub_match<const wchar_t*> wcsub_match;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [sub_match-Klasse](../standard-library/sub-match-class.md) für Iteratoren des Typs `const wchar_t*`.  
  
##  <a name="a-namewregextypedefa--wregex-typedef"></a><a name="wregex_typedef"></a> wregex-Typdefinition  
 Die Typdefinition für „wchar_t basic_regex“.  
  
```  
typedef basic_regex<wchar_t> wregex;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [basic_regex-Klasse](../standard-library/basic-regex-class.md) für Iteratoren des Typs `wchar_t`.  
  
##  <a name="a-namewsmatchtypedefa--wsmatch-typedef"></a><a name="wsmatch_typedef"></a> wsmatch-Typdefinition  
 Die Typdefinition für „wstring match_results“.  
  
```  
typedef match_results<wstring::const_iterator> wsmatch;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [match_results-Klasse](../standard-library/match-results-class.md) für Iteratoren des Typs `wstring::const_iterator`.  
  
##  <a name="a-namewsregexiteratortypedefa--wsregexiterator-typedef"></a><a name="wsregex_iterator_typedef"></a> wsregex_iterator-Typdefinition  
 Die Typdefinition für „wstring regex_iterator“.  
  
```  
typedef regex_iterator<wstring::const_iterator> wsregex_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [regex_iterator-Klasse](../standard-library/regex-iterator-class.md) für Iteratoren des Typs `wstring::const_iterator`.  
  
##  <a name="a-namewsregextokeniteratortypedefa--wsregextokeniterator-typedef"></a><a name="wsregex_token_iterator_typedef"></a> wsregex_token_iterator-Typdefinition  
 Typdefinition für „wstring regex_token_iterator“.  
  
```  
typedef regex_token_iterator<wstring::const_iterator> wsregex_token_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [regex_token_iterator-Klasse](../standard-library/regex-token-iterator-class.md) für Iteratoren des Typs `wstring::const_iterator`.  
  
##  <a name="a-namewssubmatchtypedefa--wssubmatch-typedef"></a><a name="wssub_match_typedef"></a> wssub_match Typdefinition  
 Die Typdefinition für „wstring sub_match“.  
  
```  
typedef sub_match<wstring::const_iterator> wssub_match;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [sub_match-Klasse](../standard-library/sub-match-class.md) für Iteratoren des Typs `wstring::const_iterator`.  
  
## <a name="see-also"></a>Siehe auch  
[\<regex>](../standard-library/regex.md)  
[regex_constants-Klasse](../standard-library/regex-constants-class.md)  
[regex_error-Klasse](../standard-library/regex-error-class.md)  
[\<regex>-Funktionen](../standard-library/regex-functions.md)  
[regex_iterator-Klasse](../standard-library/regex-iterator-class.md)  
[\<regex>-Operatoren](../standard-library/regex-operators.md)  
[regex_token_iterator-Klasse](../standard-library/regex-token-iterator-class.md)  
[regex_traits-Klasse](../standard-library/regex-traits-class.md)  

