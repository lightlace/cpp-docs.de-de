---
title: extent-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::extent
dev_langs:
- C++
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7fb721b23f473c59051e72edc969e5de38f1c984
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="extent-class"></a>extent-Klasse

Ruft eine Arraydimension ab.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty, unsigned I = 0>
struct extent;
```

### <a name="parameters"></a>Parameter

`Ty` Der abzufragende Typ.

`I` An die Abfrage gebundene Array auf.

## <a name="remarks"></a>Hinweise

Wenn `Ty` ein Arraytyp mit mindestens `I` Dimensionen ist, enthält die Abfrage die Anzahl der Elemente in der durch `I` angegebener Dimension. Wenn `Ty` nicht ein Arraytyp oder sein Rang kleiner als `I` ist, oder wenn `I` 0 und `Ty` vom Datentyp „Array mit unbekannter Grenze `U`“ ist, enthält die Abfrage den Wert 0.

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
