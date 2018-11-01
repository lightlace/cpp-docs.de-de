---
title: extent-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::extent
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
ms.openlocfilehash: 716f4fcd90e97eaeb3f56c8429379590d176e1c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428144"
---
# <a name="extent-class"></a>extent-Klasse

Ruft eine Arraydimension ab.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty, unsigned I = 0>
struct extent;
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der abzufragende Typ.

*I*<br/>
Das an die Abfrage gebundene Array.

## <a name="remarks"></a>Hinweise

Wenn *Ty* ist ein Arraytyp, der mindestens über *ich* Dimensionen, die Typabfrage enthält die Anzahl der Elemente in der Dimension, die anhand des *ich*. Wenn *Ty* ist kein Arraytyp oder sein Rang kleiner als *ich*, oder wenn *ich* ist 0 (null) und *Ty* ist vom Typ "Array mit Unbekannter Grenze von `U` ", die Typabfrage enthält den Wert 0.

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__extent.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "extent 0 == "
        << std::extent<int[5][10]>::value << std::endl;
    std::cout << "extent 1 == "
        << std::extent<int[5][10], 1>::value << std::endl;

    return (0);
    }

```

```Output
extent 0 == 5
extent 1 == 10
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_all_extents-Klasse](../standard-library/remove-all-extents-class.md)<br/>
[remove_extent-Klasse](../standard-library/remove-extent-class.md)<br/>
