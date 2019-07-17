---
title: '&lt;strstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <strstream>
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
ms.openlocfilehash: 212223f98db09097e596fc6fe2ddd31bbe16e6b7
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245369"
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;

Definiert mehrere Klassen, die Iostreams-Vorgänge für Sequenzen, die in einem reservierten Array des gespeicherten unterstützen **Char** Objekt. Solche Sequenzen sind leicht in und aus C-Zeichenfolgen zu konvertieren.

## <a name="requirements"></a>Anforderungen

**Header:** \<strstream>

**Namespace:** std

## <a name="remarks"></a>Hinweise

Objekte vom Typ `strstream` arbeiten mit `char` *, die C-Zeichenfolgen darstellen. Verwenden Sie [\<sstream>](../standard-library/sstream.md) zum Arbeiten mit Objekten des Typs [basic_string](../standard-library/basic-string-class.md).

> [!NOTE]
> Die Klassen im \<Strstream > sind veraltet. Beachten Sie, mithilfe der Klassen im \<Sstream > stattdessen.

## <a name="members"></a>Member

### <a name="classes"></a>Klassen

|||
|-|-|
|[strstreambuf-Klasse](../standard-library/strstreambuf-class.md)|Die Klasse beschreibt einen Streampuffer, der die Übertragung von Elementen in eine bzw. aus einer Sequenz von Elementen, die in gespeicherten steuert eine **Char** Array-Objekt.|
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

[\<strstream>](../standard-library/strstream.md)<br/>
[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
