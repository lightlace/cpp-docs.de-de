---
title: '&lt;string_view&gt;'
ms.date: 04/18/2019
helpviewer_keywords:
- string_view header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: 47924c3d6bd1a2f45cdbac648f4f563c57ce8939
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459115"
---
# <a name="ltstringviewgt"></a>&lt;string_view&gt;

Definiert die Klassen Vorlage `basic_string_view` und verwandte Typen und Operatoren. (Erfordert die Compileroption [Std: c++ 17](../build/reference/std-specify-language-standard-version.md) oder höher.)

## <a name="syntax"></a>Syntax

```cpp
#include <string_view>
```

## <a name="remarks"></a>Hinweise

Die string_view-Familie von Vorlagen Spezialisierungsmöglichkeiten bietet eine effiziente Möglichkeit zum Übergeben eines schreibgeschützten, Ausnahme sicheren, nicht besitzenden Handles an die Zeichendaten beliebiger Zeichen folgen ähnlicher Objekte mit dem ersten Element der Sequenz an Position 0 (null). Ein Funktionsparameter des Typs `string_view` (bei dem es sich um eine typedef für `basic_string_view<char>`handelt) `std::string`kann Argumente wie, **Char\*** oder eine beliebige andere Zeichen folgen ähnliche Klasse von schmalen Zeichen annehmen, für die eine implizite Konvertierung in `string_view`ist definiert. Ebenso kann ein Parameter von `wstring_view` `u16string_view` oder `u32string_view` jeden beliebigen Zeichen Folgentyp akzeptieren, für den eine implizite Konvertierung definiert ist. Weitere Informationen finden Sie unter [basic_string_view-Klasse](../standard-library/basic-string-view-class.md).

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[string_view](../standard-library/string-view-typedefs.md#string_view)|Eine Spezialisierung der Klassen Vorlage `basic_string_view` mit Elementen des Typs **char**.|
|[wstring_view](../standard-library/string-view-typedefs.md#wstring_view)|Eine Spezialisierung der Klassen Vorlage `basic_string_view` mit Elementen des Typs **wchar_t**.|
|[u16string_view](../standard-library/string-view-typedefs.md#u16string_view)|Eine Spezialisierung der Klassen Vorlage `basic_string_view` mit Elementen des Typs. `char16_t`|
|[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)|Eine Spezialisierung der Klassen Vorlage `basic_string_view` mit Elementen des Typs. `char32_t`|

### <a name="operators"></a>Operatoren

Die \<string_view->-Operatoren können-Objekte mit Objekten beliebiger konvertierbarer Zeichen folgen Typen vergleichen `string_view` .

|Operator|Beschreibung|
|-|-|
|[Operator!=](../standard-library/string-view-operators.md#op_neq)|Testet, ob das Objekt links vom Operator ungleich dem Objekt rechts vom Operator ist.|
|[operator==](../standard-library/string-view-operators.md#op_eq_eq)|Testet, ob das Objekt links vom Operator gleich dem Objekt rechts vom Operator ist.|
|[operator<](../standard-library/string-view-operators.md#op_lt)|Testet, ob das Objekt links vom Operator kleiner als das Objekt auf der rechten Seite ist.|
|[operator<=](../standard-library/string-view-operators.md#op_lt_eq)|Testet, ob das Objekt links vom Operator kleiner oder gleich dem Objekt auf der rechten Seite ist.|
|[operator<\<](../standard-library/string-view-operators.md#op_lt_lt)|Eine Vorlagen Funktion, die ein `string_view` -Objekt in einen Ausgabestream einfügt.|
|[operator>](../standard-library/string-view-operators.md#op_gt)|Testet, ob das Objekt links vom Operator größer als das Objekt auf der rechten Seite ist.|
|[operator>=](../standard-library/string-view-operators.md#op_gt_eq)|Testet, ob das Objekt links vom Operator größer oder gleich dem Objekt auf der rechten Seite ist.|

### <a name="literals"></a>Literale

|Operator|Beschreibung|
|-|-|
|[sv](../standard-library/string-view-operators.md#op_sv)|Erstellt eine `string_view`, `wstring_view`, `u16string_view` oder`u32string_view` , abhängig vom Typ des Zeichenfolgenliterals, an das Sie angefügt wird.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[basic_string_view-Klasse](../standard-library/basic-string-view-class.md)|Eine Klassen Vorlage, die eine schreibgeschützte Ansicht in einer Sequenz beliebiger Zeichen ähnlicher Objekte bereitstellt.|
|[hash](string-view-hash.md)|Funktions Objekt, das einen Hashwert für ein string_view-Objekt erzeugt.|

## <a name="requirements"></a>Anforderungen

- **Header:** \<string_view>

- **Namespace:** std

- **Compileroption:** Std: c++ 17 (oder höher)

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)
