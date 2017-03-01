---
title: regex_constants-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex_constants
- std::regex_constants
- regex/std::regex_constants
- error_collate
- std::regex_constants::error_collate
- regex/std::regex_constants::error_collate
- error_ctype
- std::regex_constants::error_ctype
- regex/std::regex_constants::error_ctype
- error_escape
- std::regex_constants::error_escape
- regex/std::regex_constants::error_escape
- error_backref
- std::regex_constants::error_backref
- regex/std::regex_constants::error_backref
- error_brack
- std::regex_constants::error_brack
- regex/std::regex_constants::error_brack
- error_paren
- std::regex_constants::error_paren
- regex/std::regex_constants::error_paren
- error_brace
- std::regex_constants::error_brace
- regex/std::regex_constants::error_brace
- error_badbrace
- std::regex_constants::error_badbrace
- regex/std::regex_constants::error_badbrace
- error_range
- std::regex_constants::error_range
- regex/std::regex_constants::error_range
- error_space
- std::regex_constants::error_space
- regex/std::regex_constants::error_space
- error_badrepeat
- std::regex_constants::error_badrepeat
- regex/std::regex_constants::error_badrepeat
- error_complexity
- std::regex_constants::error_complexity
- regex/std::regex_constants::error_complexity
- error_stack
- std::regex_constants::error_stack
- regex/std::regex_constants::error_stack
- error_parse
- std::regex_constants::error_parse
- regex/std::regex_constants::error_parse
- error_syntax
- std::regex_constants::error_syntax
- regex/std::regex_constants::error_syntax
- match_default
- std::regex_constants::match_default
- regex/std::regex_constants::match_default
- match_not_bol
- std::regex_constants::match_not_bol
- regex/std::regex_constants::match_not_bol
- match_not_eol
- std::regex_constants::match_not_eol
- regex/std::regex_constants::match_not_eol
- match_not_bow
- std::regex_constants::match_not_bow
- regex/std::regex_constants::match_not_bow
- match_not_eow
- std::regex_constants::match_not_eow
- regex/std::regex_constants::match_not_eow
- match_any
- std::regex_constants::match_any
- regex/std::regex_constants::match_any
- match_not_null
- std::regex_constants::match_not_null
- regex/std::regex_constants::match_not_null
- match_continuous
- std::regex_constants::match_continuous
- regex/std::regex_constants::match_continuous
- match_prev_avail
- std::regex_constants::match_prev_avail
- regex/std::regex_constants::match_prev_avail
- format_default
- std::regex_constants::format_default
- regex/std::regex_constants::format_default
- format_sed
- std::regex_constants::format_sed
- regex/std::regex_constants::format_sed
- format_no_copy
- std::regex_constants::format_no_copy
- regex/std::regex_constants::format_no_copy
- format_first_only
- std::regex_constants::format_first_only
- regex/std::regex_constants::format_first_only
- std::regex_constants::ECMAScript
- regex/std::regex_constants::ECMAScript
- std::regex_constants::basic
- regex/std::regex_constants::basic
- std::regex_constants::extended
- regex/std::regex_constants::extended
- std::regex_constants::awk
- regex/std::regex_constants::awk
- std::regex_constants::grep
- regex/std::regex_constants::grep
- std::regex_constants::egrep
- regex/std::regex_constants::egrep
- std::regex_constants::icase
- regex/std::regex_constants::icase
- std::regex_constants::nosubs
- regex/std::regex_constants::nosubs
- std::regex_constants::optimize
- regex/std::regex_constants::optimize
- std::regex_constants::collate
- regex/std::regex_constants::collate
dev_langs:
- C++
helpviewer_keywords:
- regex_constants class
ms.assetid: 4a69c0ba-c46d-46e4-bd29-6f4efb805f26
caps.latest.revision: 18
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
ms.openlocfilehash: 9330a5c4e1b487880f405478dd7e8838af739c44
ms.lasthandoff: 02/24/2017

---
# <a name="regexconstants-class"></a>regex_constants-Klasse
Namespace für Flags für reguläre Ausdrücke.  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace regex_constants {  
    enum syntax_option_type;  
    enum match_flag_type;  
    enum error_type;  
 }  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Namespace `regex_constants` kapselt mehrere Flagtypen und ihre zugeordneten Flagwerte.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<regex >  
  
 **Namespace:** std  
  
##  <a name="a-nameregexconstantserrortypea--regexconstantserrortype"></a><a name="regex_constants__error_type"></a> regex_constants::error_type  
 Flags für die Berichterstellung bei Syntaxfehlern für reguläre Ausdrücke.  
  
```  
enum error_type
    {    // identify error
    error_collate,
    error_ctype,
    error_escape,
    error_backref,
    error_brack,
    error_paren,
    error_brace,
    error_badbrace,
    error_range,
    error_space,
    error_badrepeat,
    error_complexity,
    error_stack,
    error_parse,
    error_syntax
    };  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein enumerierter Typ, der ein Objekt beschreibt, das Fehlerflags aufnehmen kann. Die unterschiedlichen Flagwerte sind:  
  
 `error_backref`: Der Ausdruck enthielt einen ungültigen Rückverweis.  
  
 `error_badbrace`: Der Ausdruck enthielt eine ungültige Anzahl in einem {}-Ausdruck.  
  
 `error_badrepeat`: Einem Wiederholungsausdruck (in den meisten Kontexten einer von „*“, „“, „+“, „{“) wurde kein Ausdruck vorangestellt.  
  
 `error_brace`: Der Ausdruck enthielt eine nicht übereinstimmende Anzahl von „{' or '}“.  
  
 `error_brack`: Der Ausdruck enthielt eine nicht übereinstimmende Anzahl von „[' or ']“.  
  
 `error_collate`: Der Ausdruck enthielt einen ungültigen Sortierungselementnamen.  
  
 `error_complexity`: Bei einem versuchten Vergleich ist ein Fehler aufgetreten, da dieser zu komplex war.  
  
 `error_ctype`: Der Ausdruck enthielt einen ungültigen Zeichenklassennamen.  
  
 `error_escape`: Der Ausdruck enthielt eine ungültige Escapesequenz.  
  
 `error_paren`: Der Ausdruck enthielt eine nicht übereinstimmende Anzahl von „(' or ')“.  
  
 `error_parse`: Der Ausdruck konnte nicht analysiert werden.  
  
 `error_range`: Der Ausdruck enthielt einen ungültigen Zeichenbereichsbezeichner.  
  
 `error_space`: Beim Analysieren eines regulären Ausdrucks ist ein Fehler aufgetreten, da nicht ausreichend Ressourcen verfügbar waren.  
  
 `error_stack`: Bei einem versuchten Vergleich ist ein Fehler aufgetreten, da nicht ausreichend Arbeitsspeicher verfügbar war.  
  
 `error_syntax`: Beim Analysieren eines Syntaxfehler ist ein Fehler aufgetreten.  
  
 `error_backref`: Der Ausdruck enthielt einen ungültigen Rückverweis.  
  
##  <a name="a-nameregexconstantsmatchflagtypea--regexconstantsmatchflagtype"></a><a name="regex_constants__match_flag_type"></a> regex_constants::match_flag_type  
 Flags für Optionen zum Vergleichen regulärer Ausdrücke.  
  
```  
enum match_flag_type 
    {    // specify matching and formatting rules
    match_default = 0x0000,
    match_not_bol = 0x0001,
    match_not_eol = 0x0002,
    match_not_bow = 0x0004,
    match_not_eow = 0x0008,
    match_any = 0x0010,
    match_not_null = 0x0020,
    match_continuous = 0x0040,
    match_prev_avail = 0x0100,
    format_default = 0x0000,
    format_sed = 0x0400,
    format_no_copy = 0x0800,
    format_first_only = 0x1000,
    _Match_not_null = 0x2000
    };  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist eine „Bitmaske“, die Optionen für den Vergleich einer Textsequenz mit einem regulären Ausdruck und Formatflags beschreibt, die beim Ersetzen von Text verwendet werden. Optionen können mit `|`kombiniert werden.  
  
 Vergleichsoptionen:  
  
 `match_default`  
  
 `match_not_bol`: Die erste Position in der Zielsequenz nicht als Zeilenanfang behandeln.  
  
 `match_not_eol`: Die „past-the-end“-Position in der Zielsequenz nicht als Zeilenende behandeln.  
  
 `match_not_bow`: Die erste Position in der Zielsequenz nicht als Wortanfang behandeln.  
  
 `match_not_eow`: Die „past-the-end“-Position in der Zielsequenz nicht als Wortende behandeln.  
  
 `match_any`: Wenn mehr als eine Übereinstimmung möglich ist, kann jede Übereinstimmung akzeptiert werden.  
  
 `match_not_null`: Eine leere Untersequenz nicht als Übereinstimmung behandeln.  
  
 `match_continuous`: Nur am Anfang der Zielsequenz nach Übereinstimmungen suchen.  
  
 `match_prev_avail` -- `--first` ist ein gültiger Iterator. Ignorieren Sie `match_not_bol` und `match_not_bow`, falls diese festgelegt sind.  
  
 Formatflags:  
  
 `format_default`: ECMAScript-Formatierungsregeln verwenden  
  
 `format_sed`: „sed“-Formatierungsregeln verwenden  
  
 `format_no_copy`: keinen Text kopieren, der nicht mit dem regulären Ausdruck übereinstimmt  
  
 `format_first_only`: nach der ersten Übereinstimmung nicht nach weiteren Übereinstimmungen suchen  
  
##  <a name="a-nameregexconstantssyntaxoptiontypea--regexconstantssyntaxoptiontype"></a><a name="regex_constants__syntax_option_type"></a> regex_constants::syntax_option_type  
 Flags zum Auswählen von Syntaxoptionen.  
  
```  
enum syntax_option_type
    {    // specify RE syntax rules
    ECMAScript = 0x01,
    basic = 0x02,
    extended = 0x04,
    awk = 0x08,
    grep = 0x10,
    egrep = 0x20,
    _Gmask = 0x3F,

    icase = 0x0100,
    nosubs = 0x0200,
    optimize = 0x0400,
    collate = 0x0800
    };  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Bitmaskentyp, der Sprachenspezifizierer und Syntaxmodifikatoren beschreibt, die beim Kompilieren eines regulären Ausdrucks verwendet werden sollen. Optionen können mit `|`kombiniert werden. Es darf immer nur jeweils ein Sprachenspezifizierer verwendet werden.  
  
 Es gibt folgende Sprachenspezifizierer:  
  
 `ECMAScript`: als ECMAScript kompilieren  
  
 `basic`: als BRE kompilieren  
  
 `extended`: als ERE kompilieren  
  
 `awk`: als awk kompilieren  
  
 `grep`: als grep kompilieren  
  
 `egrep`: als egrep kompilieren  
  
 Es gibt folgende Syntaxmodifikatoren:  
  
 `icase`: Beachtung der Groß-/Kleinschreibung für Übereinstimmungen aufheben  
  
 `nosubs`: die Implementierung muss die Inhalte von Erfassungsgruppen nicht nachverfolgen  
  
 `optimize`:die Implementierung muss mehr Wert auf die Geschwindigkeit der Übereinstimmung anstatt die Geschwindigkeit der Kompilierung regulärer Ausdrücke legen  
  
 `collate`: für Übereinstimmungen soll Gebietsschema beachtet werden  
  
## <a name="see-also"></a>Siehe auch  
[\<regex>](../standard-library/regex.md)  
[regex_error-Klasse](../standard-library/regex-error-class.md)  
[\<regex>-Funktionen](../standard-library/regex-functions.md)  
[regex_iterator-Klasse](../standard-library/regex-iterator-class.md)  
[\<regex>-Operatoren](../standard-library/regex-operators.md)  
[regex_token_iterator-Klasse](../standard-library/regex-token-iterator-class.md)  
[regex_traits-Klasse](../standard-library/regex-traits-class.md)  
[\<regex>-Typdefinitionen](../standard-library/regex-typedefs.md)  

