---
title: '&lt;regex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <regex>
helpviewer_keywords:
- regex header
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
ms.openlocfilehash: 0a4728008130119ed9a01334efb2fea2a4ac0639
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50627343"
---
# <a name="ltregexgt"></a>&lt;regex&gt;

Definiert eine Vorlagenklasse, um [reguläre Ausdrücke (C++)](../standard-library/regular-expressions-cpp.md) sowie einige Vorlagenklassen und Funktionen zu analysieren, um Text nach Übereinstimmungen mit einem Objekt zu durchsuchen, das einen regulären Ausdruck enthält.

## <a name="syntax"></a>Syntax

```cpp
#include <regex>
```

## <a name="remarks"></a>Hinweise

Um ein Objekt für einen regulären Ausdruck zu erstellen, verwenden Sie die Vorlagenklasse [basic_regex-Klasse](../standard-library/basic-regex-class.md) oder eine ihrer Spezialisierungen, [regex](../standard-library/regex-typedefs.md#regex) und [wregex](../standard-library/regex-typedefs.md#wregex), zusammen mit den Syntaxflags des Typs [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type).

Um Text nach Übereinstimmungen mit Objekt eines regulären Ausdrucks zu suchen, verwenden Sie die Vorlagenfunktionen [Regex_match](../standard-library/regex-functions.md#regex_match) und [Regex_search](../standard-library/regex-functions.md#regex_search)zusammen mit den übereinstimmungsflags des Typs [regex_constants::match_ Flag_type](../standard-library/regex-constants-class.md#match_flag_type). Diese Funktionen geben Ergebnisse zurück, indem sie die Vorlagenklasse [match_results-Klasse](../standard-library/match-results-class.md) und deren Spezialisierungen, [cmatch](../standard-library/regex-typedefs.md#cmatch), [wcmatch](../standard-library/regex-typedefs.md#wcmatch), [smatch](../standard-library/regex-typedefs.md#smatch) und [wsmatch](../standard-library/regex-typedefs.md#wsmatch) zusammen mit der Vorlagenklasse [sub_match-Klasse](../standard-library/sub-match-class.md) und deren Spezialisierungen, [csub_match](../standard-library/regex-typedefs.md#csub_match), [wcsub_match](../standard-library/regex-typedefs.md#wcsub_match), [ssub_match](../standard-library/regex-typedefs.md#ssub_match) und [wssub_match](../standard-library/regex-typedefs.md#wssub_match) verwenden.

Um Text zu ersetzen, die Objekt für einen regulären Ausdruck übereinstimmt, verwenden Sie die Vorlagenfunktion [Regex_replace](../standard-library/regex-functions.md#regex_replace)zusammen mit den übereinstimmungsflags des Typs [regex_constants:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type).

Um mehrere Übereinstimmungen eines Objekts für einen regulären Ausdruck zu durchlaufen, verwenden Sie die Vorlagenklassen [regex_iterator-Klasse](../standard-library/regex-iterator-class.md) und [regex_token_iterator-Klasse](../standard-library/regex-token-iterator-class.md) oder eine von deren Spezialisierungen [cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator), [sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator), [wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator), [wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator), [cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator), [sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator), [wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator) oder [wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator) zusammen mit den Übereinstimmungsflags des Typs [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#match_flag_type).

Um die Details der Grammatik regulärer Ausdrücke zu ändern, schreiben Sie eine Klasse, in der die Merkmale des regulären Ausdrucks implementiert sind.

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[basic_regex](../standard-library/basic-regex-class.md)|Umschließt einen regulären Ausdruck.|
|[match_results](../standard-library/match-results-class.md)|Enthält eine Sequenz von Teilübereinstimmungen.|
|[regex_constants](../standard-library/regex-constants-class.md)|Enthält zusammengestellte Konstanten.|
|[regex_error](../standard-library/regex-error-class.md)|Meldet einen ungültigen regulären Ausdruck.|
|[regex_iterator](../standard-library/regex-iterator-class.md)|Durchläuft Übereinstimmungsergebnisse.|
|[regex_traits](../standard-library/regex-traits-class.md)|Beschreibt die Merkmale von Elementen zum Abgleichen.|
|[regex_traits\<char>](../standard-library/regex-traits-char-class.md)|Beschreibt die Merkmale von **Char** für den Abgleich.|
|[regex_traits<wchar_t>](../standard-library/regex-traits-wchar-t-class.md)|Beschreibt die Merkmale von **"wchar_t"** für den Abgleich.|
|[regex_token_iterator](../standard-library/regex-token-iterator-class.md)|Durchläuft Teilübereinstimmungen.|
|[sub_match](../standard-library/sub-match-class.md)|Beschreibt eine Teilübereinstimmung.|

### <a name="type-definitions"></a>Typdefinitionen

|||
|-|-|
|[cmatch](../standard-library/regex-typedefs.md#cmatch)|Die Typdefinition für **Char** `match_results`.|
|[cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator)|Die Typdefinition für **Char** `regex_iterator`.|
|[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator)|Die Typdefinition für **Char** `regex_token_iterator`.|
|[csub_match](../standard-library/regex-typedefs.md#csub_match)|Die Typdefinition für **Char** `sub_match`.|
|[regex](../standard-library/regex-typedefs.md#regex)|Die Typdefinition für **Char** `basic_regex`.|
|[smatch](../standard-library/regex-typedefs.md#smatch)|Typdefinition für `string` `match_results`.|
|[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator)|Typdefinition für `string` `regex_iterator`.|
|[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator)|Typdefinition für `string` `regex_token_iterator`.|
|[ssub_match](../standard-library/regex-typedefs.md#ssub_match)|Typdefinition für `string` `sub_match`.|
|[wcmatch](../standard-library/regex-typedefs.md#wcmatch)|Die Typdefinition für **"wchar_t"** `match_results`.|
|[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator)|Die Typdefinition für **"wchar_t"** `regex_iterator`.|
|[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)|Die Typdefinition für **"wchar_t"** `regex_token_iterator`.|
|[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match)|Die Typdefinition für **"wchar_t"** `sub_match`.|
|[wregex](../standard-library/regex-typedefs.md#wregex)|Die Typdefinition für **"wchar_t"** `basic_regex`.|
|[wsmatch](../standard-library/regex-typedefs.md#wsmatch)|Typdefinition für `wstring` `match_results`.|
|[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator)|Typdefinition für `wstring` `regex_iterator`.|
|[wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator)|Typdefinition für `wstring` `regex_token_iterator`.|
|[wssub_match](../standard-library/regex-typedefs.md#wssub_match)|Typdefinition für `wstring` `sub_match`.|

### <a name="functions"></a>Funktionen

|Funktion|Beschreibung|
|-|-|
|[regex_match](../standard-library/regex-functions.md#regex_match)|Gleicht einen regulären Ausdruck exakt ab.|
|[regex_replace](../standard-library/regex-functions.md#regex_replace)|Ersetzt übereinstimmende reguläre Ausdrücke.|
|[regex_search](../standard-library/regex-functions.md#regex_search)|Sucht nach einer Übereinstimmung mit einem regulären Ausdruck.|
|[swap](../standard-library/regex-functions.md#swap)|Tauscht `basic_regex`- oder `match_results`-Objekte.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator==](../standard-library/regex-operators.md#op_eq_eq)|Vergleich von verschiedenen Objekten: gleich.|
|[Operator!=](../standard-library/regex-operators.md#op_neq)|Vergleich von verschiedenen Objekten: ungleich.|
|[operator<](../standard-library/regex-operators.md#op_lt)|Vergleich von verschiedenen Objekten: kleiner als.|
|[operator\<=](../standard-library/regex-operators.md#op_gt_eq)|Vergleich von verschiedenen Objekten: kleiner als oder gleich.|
|[operator>](../standard-library/regex-operators.md#op_gt)|Vergleich von verschiedenen Objekten: größer als.|
|[operator>=](../standard-library/regex-operators.md#op_gt_eq)|Vergleich von verschiedenen Objekten: größer als oder gleich.|
|[operator<<](../standard-library/regex-operators.md#op_lt_lt)|Fügt ein `sub_match`-Objekt in einem Stream ein.|

## <a name="see-also"></a>Siehe auch

[Reguläre Ausdrücke (C++)](../standard-library/regular-expressions-cpp.md)<br/>
[regex_constants-Klasse](../standard-library/regex-constants-class.md)<br/>
[regex_error-Klasse](../standard-library/regex-error-class.md)<br/>
[\<regex>-Funktionen](../standard-library/regex-functions.md)<br/>
[regex_iterator-Klasse](../standard-library/regex-iterator-class.md)<br/>
[\<regex>-Operatoren](../standard-library/regex-operators.md)<br/>
[regex_token_iterator-Klasse](../standard-library/regex-token-iterator-class.md)<br/>
[regex_traits-Klasse](../standard-library/regex-traits-class.md)<br/>
[\<regex>-Typdefinitionen](../standard-library/regex-typedefs.md)<br/>
