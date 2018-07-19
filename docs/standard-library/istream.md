---
title: '&lt;istream&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- istream/std::<istream>
- <istream>
- std::<istream>
dev_langs:
- C++
helpviewer_keywords:
- istream header
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7000bd30e34836466e9f662f9b6b0dd8f2ecde4c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956553"
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
|[iostream](../standard-library/istream-typedefs.md#iostream)|Ein Typ `basic_iostream` auf **Char**.|
|[istream](../standard-library/istream-typedefs.md#istream)|Ein Typ `basic_istream` auf **Char**.|
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
|[basic_istream](../standard-library/basic-istream-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das steuert, Extrahieren von Elementen und codierten Objekten aus einem Streampuffer mit Elementen des Typs `Elem`, auch bekannt als [Char_type](../standard-library/basic-ios-class.md#char_type), dessen Zeichenmerkmale von der Klasse ermittelt werden `Tr`, auch bekannt als [Traits_type](../standard-library/basic-ios-class.md#traits_type).|

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
