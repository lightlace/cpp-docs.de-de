---
title: extent-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::extent
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
ms.openlocfilehash: 0cd53ba8537e706a68ffdcf08df998108266ad20
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457791"
---
# <a name="extent-class"></a>extent-Klasse

Ruft eine Arraydimension ab.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty, unsigned I = 0>
struct extent;
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der abzufragende Typ.

*ICH*\
Das an die Abfrage gebundene Array.

## <a name="remarks"></a>Hinweise

Wenn *Ty* ein Arraytyp mit mindestens *I* Dimensionen ist, enthält die typabfrage die Anzahl der Elemente in der Dimension, die von *i*angegeben wird. Wenn *Ty* kein Arraytyp ist oder der Rang kleiner als *i*ist, *oder wenn der* Wert 0 (null) und " *Ty* " vom `U`Typ "Array mit unbekannter Grenze" ist, enthält die typabfrage den Wert 0.

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

[<type_traits>](../standard-library/type-traits.md)\
[remove_all_extents Class (remove_all_extents-Klasse)](../standard-library/remove-all-extents-class.md)\
[remove_extent Class (remove_extent-Klasse)](../standard-library/remove-extent-class.md)
