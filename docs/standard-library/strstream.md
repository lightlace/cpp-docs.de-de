---
title: '&lt;strstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <strstream>
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
ms.openlocfilehash: ecf8499a07f03c00588e7b7fd83b8d41a23e8e7a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459085"
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;

Definiert mehrere Klassen, die Iostreams-Vorgänge für Sequenzen unterstützen, die in einem zugeordneten Array von **char** -Objekten gespeichert sind. Solche Sequenzen sind leicht in und aus C-Zeichenfolgen zu konvertieren.

## <a name="requirements"></a>Anforderungen

**Header:** \<strstream>

**Namespace:** std

## <a name="remarks"></a>Hinweise

Objekte vom Typ `strstream` arbeiten mit `char` *, die C-Zeichenfolgen darstellen. Verwenden Sie [\<sstream>](../standard-library/sstream.md) zum Arbeiten mit Objekten des Typs [basic_string](../standard-library/basic-string-class.md).

> [!NOTE]
> Die Klassen in \<"strinstream >" sind veraltet. Verwenden Sie stattdessen die Klassen \<in sstream->.

## <a name="members"></a>Member

### <a name="classes"></a>Klassen

|||
|-|-|
|[strstreambuf-Klasse](../standard-library/strstreambuf-class.md)|Die Klasse beschreibt einen Streampuffer, der die Übertragung von Elementen in eine und aus einer Sequenz von Elementen steuert, die in einem **char** -Array Objekt gespeichert sind.|
|[istrstream-Klasse](../standard-library/istrstream-class.md)|Die Klasse beschreibt ein Objekt, das die Extraktion von Elementen und codierten Objekten aus einem Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.|
|[ostrstream-Klasse](../standard-library/ostrstream-class.md)|Die Klasse beschreibt ein Objekt, das die Einfügung von Elementen und codierten Objekten in einen Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.|
|[strstream-Klasse](../standard-library/strstream-class.md)|Die Klasse beschreibt ein Objekt, das die Einfügung und Extraktion von Elementen und codierten Objekten mit einem Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.|

### <a name="functions"></a>Funktionen

```cpp
void freeze(bool freezefl = true);
char* str();
int pcount();
```

## <a name="see-also"></a>Siehe auch

[\<strstream>](../standard-library/strstream.md)\
[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)\
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)
