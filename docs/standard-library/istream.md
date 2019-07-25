---
title: '&lt;istream&gt;'
ms.date: 11/04/2016
f1_keywords:
- istream/std::<istream>
- <istream>
- std::<istream>
helpviewer_keywords:
- istream header
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
ms.openlocfilehash: 0ad27bf849e8d4b9188868b9a29bf423b4cafafa
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458733"
---
# <a name="ltistreamgt"></a>&lt;istream&gt;

Definiert die Vorlagenklasse basic_istream, die Extraktionen für die Iostreams vermittelt, und die Vorlagenklasse basic_iostream, die Einfügungen und Extraktionen vermittelt. Der Header definiert auch einen verknüpften Manipulator. Diese Headerdatei wird in der Regel von einem anderen Iostreams-Header eingeschlossen. Sie müssen sie nur selten direkt einschließen.

## <a name="syntax"></a>Syntax

```cpp
#include <istream>
```

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[iostream](../standard-library/istream-typedefs.md#iostream)|Ein Typ `basic_iostream` , der auf **char**spezialisiert ist.|
|[istream](../standard-library/istream-typedefs.md#istream)|Ein Typ `basic_istream` , der auf **char**spezialisiert ist.|
|[wiostream](../standard-library/istream-typedefs.md#wiostream)|Ein `basic_iostream`-Typ, der auf **wchar** spezialisiert ist.|
|[wistream](../standard-library/istream-typedefs.md#wistream)|Ein `basic_istream`-Typ, der auf **wchar** spezialisiert ist.|

### <a name="manipulators"></a>Manipulatoren

|||
|-|-|
|[ws](../standard-library/istream-functions.md#ws)|Überspringt Leerraum im Datenstrom.|
|[swap](../standard-library/istream-functions.md#istream_swap)|Tauscht zwei Streamobjekte.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator>>](../standard-library/istream-operators.md#op_gt_gt)|Extrahiert von Zeichenfolgen und Zeichen aus dem Stream.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[basic_iostream](../standard-library/basic-iostream-class.md)|Eine Streamklasse für Ein- und Ausgabe.|
|[basic_istream](../standard-library/basic-istream-class.md)|Die Vorlagen Klasse beschreibt ein Objekt, das das Extrahieren von Elementen und codierten Objekten aus einem Streampuffer mit Elementen `Elem`des Typs steuert, der auch als [char_type](../standard-library/basic-ios-class.md#char_type)bezeichnet wird, dessen Zeichen Merkmale `Tr`von der Klasse bestimmt werden. wird als [Traits_type](../standard-library/basic-ios-class.md#traits_type)bezeichnet.|

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)\
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)
