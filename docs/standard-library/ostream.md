---
title: '&lt;ostream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <ostream>
- ostream/std::<ostream>
- std::<ostream>
helpviewer_keywords:
- ostream header
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
ms.openlocfilehash: e8084fcbbeb2f1526107584058fc227bbd514d39
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582585"
---
# <a name="ltostreamgt"></a>&lt;ostream&gt;

Definiert die Vorlagenklasse [basic_ostream](../standard-library/basic-ostream-class.md), die Einfügungen für die iostreams vermittelt. Der Header definiert auch mehrere verwandte Manipulatoren. Dieser Header wird in der Regel von einem der anderen iostreams-Header für Sie eingefügt. Sie müssen ihn nur selten direkt einfügen.)

## <a name="syntax"></a>Syntax

```cpp
#include <ostream>

```

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[ostream](../standard-library/ostream-typedefs.md#ostream)|Erstellt einen Typ aus `basic_ostream` , das speziell auf **Char** und `char_traits` auf **Char**.|
|[wostream](../standard-library/ostream-typedefs.md#wostream)|Erstellt einen Typ aus `basic_ostream` , das speziell auf **"wchar_t"** und `char_traits` auf **"wchar_t"**.|

### <a name="manipulators"></a>Manipulatoren

|||
|-|-|
|[endl](../standard-library/ostream-functions.md#endl)|Beendet eine Zeile und leert den Puffer.|
|[ends](../standard-library/ostream-functions.md#ends)|Beendet eine Zeichenfolge.|
|[flush](../standard-library/ostream-functions.md#flush)|Leert den Puffer.|
|[swap](../standard-library/ostream-functions.md#swap)|Tauscht die Werte des linken `basic_ostream`-Objektparameters gegen diejenigen des rechten `basic_ostream`-Objektparameters aus.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator<<](../standard-library/ostream-operators.md#op_lt_lt)|Schreibt verschiedene Typen in den Stream.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[basic_ostream](../standard-library/basic-ostream-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer steuert.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>
