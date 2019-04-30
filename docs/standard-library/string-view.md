---
title: '&lt;string_view&gt;'
ms.date: 04/18/2019
helpviewer_keywords:
- string_view header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: 8952416cf37fc4d8d281d6ced9b8264495ec3799
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346978"
---
# <a name="ltstringviewgt"></a>&lt;string_view&gt;

Definiert die Klassenvorlage `basic_string_view` und verwandte Typen und Operatoren. (Erfordert die Compileroption [Std: c ++ 17](../build/reference/std-specify-language-standard-version.md) oder höher.)

## <a name="syntax"></a>Syntax

```cpp
#include <string_view>
```

## <a name="remarks"></a>Hinweise

Die vorlagenspezialisierungen String_view-Produktfamilie bietet eine effiziente Möglichkeit, ein nur-Lese ausnahmesicher, nicht Besitzer Handle an die Zeichendaten von Zeichenfolge-ähnliche Objekte mit dem ersten Element der Sequenz an Position 0 (null) übergeben. Ein Funktionsparameter Typ `string_view` (eine typedef für `basic_string_view<char>`) können z. B. Argumente akzeptieren `std::string`, **Char\***, oder einer anderen Zeichenfolge-ähnliche Klasse schmale Zeichen für die eine implizite die Konvertierung in `string_view` definiert ist. Auf ähnliche Weise einen Parameter vom `wstring_view`, `u16string_view` oder `u32string_view` lässt alle Zeichenfolgen-Datentyp, der für die eine implizite Konvertierung definiert ist. Weitere Informationen finden Sie unter [Basic_string_view Klasse](../standard-library/basic-string-view-class.md).

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[string_view](../standard-library/string-view-typedefs.md#string_view)|Eine Spezialisierung der Klassenvorlage `basic_string_view` mit Elementen des Typs **Char**.|
|[wstring_view](../standard-library/string-view-typedefs.md#wstring_view)|Eine Spezialisierung der Klassenvorlage `basic_string_view` mit Elementen des Typs **"wchar_t"**.|
|[u16string_view](../standard-library/string-view-typedefs.md#u16string_view)|Eine Spezialisierung der Klassenvorlage `basic_string_view` mit Elementen des Typs `char16_t`.|
|[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)|Eine Spezialisierung der Klassenvorlage `basic_string_view` mit Elementen des Typs `char32_t`.|

### <a name="operators"></a>Operatoren

Die \<String_view > Operatoren vergleichen können `string_view` Objekte auf Objekte konvertiert werden kann. alle Zeichenfolgentypen.

|Operator|Beschreibung|
|-|-|
|[Operator!=](../standard-library/string-view-operators.md#op_neq)|Testet, ob das Objekt links vom Operator ungleich dem Objekt rechts vom Operator ist.|
|[operator==](../standard-library/string-view-operators.md#op_eq_eq)|Testet, ob das Objekt links vom Operator gleich dem Objekt rechts vom Operator ist.|
|[operator<](../standard-library/string-view-operators.md#op_lt)|Testet, ob das Objekt links vom Operator kleiner als ist das Objekt auf der rechten Seite.|
|[operator<=](../standard-library/string-view-operators.md#op_lt_eq)|Testet, ob das Objekt links vom Operator kleiner oder gleich dem Objekt auf der rechten Seite ist.|
|[operator<\<](../standard-library/string-view-operators.md#op_lt_lt)|Eine Vorlagenfunktion, die Fügt eine `string_view` in einen Ausgabestream.|
|[operator>](../standard-library/string-view-operators.md#op_gt)|Testet, ob das Objekt links vom Operator größer als das Objekt auf der rechten Seite ist.|
|[operator>=](../standard-library/string-view-operators.md#op_gt_eq)|Testet, ob das Objekt links vom Operator größer oder gleich dem Objekt auf der rechten Seite ist.|

### <a name="literals"></a>Literale

|Operator|Beschreibung|
|-|-|
|[sv](../standard-library/string-view-operators.md#op_sv)|Erstellt eine `string_view`, `wstring_view`, `u16string_view`, oder `u32string_view` je nach Art des Zeichenfolgenliterals an das sie angefügt ist.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[basic_string_view-Klasse](../standard-library/basic-string-view-class.md)|Eine Klassenvorlage, die eine schreibgeschützte Ansicht in eine Sequenz von beliebigen zeichenartigen Objekten bereitstellt.|
|[hash](string-view-hash.md)|Function-Objekt, das einen Hashwert für eine String_view erzeugt.|

## <a name="requirements"></a>Anforderungen

- **Header:** \<string_view>

- **Namespace:** std

- **Compileroption:** Std: c ++ 17 (oder höher)

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
