---
title: regex_error-Klasse
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
ms.openlocfilehash: eed961ea698591935c22fc748ff79583ae636b27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62369617"
---
# <a name="regexerror-class"></a>regex_error-Klasse

Meldet ein ungültiges basic_regex-Objekt.

## <a name="syntax"></a>Syntax

```cpp
class regex_error
: public std::runtime_error
```

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt ein Ausnahmeobjekt, das ausgelöst wurde, um einen Fehler bei der Erstellung oder Verwendung eines `basic_regex` -Objekts zu melden.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[regex_error](#regex_error)|Erstellt das Objekt.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[Code](#code)|Gibt den Fehlercode zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<regex >

**Namespace:** std

## <a name="example"></a>Beispiel

```cpp
// std__regex__regex_error.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex_error paren(std::regex_constants::error_paren);

    try
        {
        std::regex rx("(a");
        }
    catch (const std::regex_error& rerr)
        {
        std::cout << "regex error: "
            << (rerr.code() == paren.code() ? "unbalanced parentheses" : "")
            << std::endl;
        }
    catch (...)
        {
        std::cout << "unknown exception" << std::endl;
        }

    return (0);
    }
```

```Output
regex error: unbalanced parentheses
```

## <a name="code"></a> regex_error::code

Gibt den Fehlercode zurück.

```cpp
regex_constants::error_code code() const;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt den Wert zurück, der an den Konstruktor des Objekts übergeben wurde.

## <a name="regex_error"></a> regex_error::regex_error

Erstellt das Objekt.

```cpp
regex_error(regex_constants::error_code error);
```

### <a name="parameters"></a>Parameter

*error*<br/>
Der Fehlercode.

### <a name="remarks"></a>Hinweise

Der Konstruktor erstellt ein Objekt, das den Wert enthält *Fehler*.

## <a name="see-also"></a>Siehe auch

[\<regex>](../standard-library/regex.md)<br/>
[regex_constants-Klasse](../standard-library/regex-constants-class.md)<br/>
[\<regex>-Funktionen](../standard-library/regex-functions.md)<br/>
[regex_iterator-Klasse](../standard-library/regex-iterator-class.md)<br/>
[\<regex>-Operatoren](../standard-library/regex-operators.md)<br/>
[regex_token_iterator-Klasse](../standard-library/regex-token-iterator-class.md)<br/>
[regex_traits-Klasse](../standard-library/regex-traits-class.md)<br/>
[\<regex>-Typdefinitionen](../standard-library/regex-typedefs.md)<br/>
