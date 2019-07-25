---
title: aligned_storage-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::aligned_storage
helpviewer_keywords:
- aligned_storage class
- aligned_storage
ms.assetid: f255e345-1f05-4d07-81e4-017f420839fb
ms.openlocfilehash: 8a4e907faa6175b9e03f5367d09501aaea388bce
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456477"
---
# <a name="alignedstorage-class"></a>aligned_storage-Klasse

Erstellt einen entsprechend ausgerichteten Typ.

## <a name="syntax"></a>Syntax

```cpp
template <std::size_t Len, std::size_t Align>
struct aligned_storage;

template <std::size_t Len, std::size_t Align = alignment_of<max_align_t>::value>
using aligned_storage_t = typename aligned_storage<Len, Align>::type;
```

### <a name="parameters"></a>Parameter

*Nest*\
Die Objektgröße.

*Abzustimmen*\
Die Objektausrichtung.

## <a name="remarks"></a>Hinweise

Das `type` Vorlagenmember-Typdefinition ist ein Synonym für einen POD-Typ  mit Ausrichtungs Ausrichtung und Größen- *len*. *Align* muss `alignment_of<T>::value` bei einem Typ `T`oder der Standardausrichtung gleich sein.

## <a name="example"></a>Beispiel

```cpp
#include <type_traits>
#include <iostream>

typedef std::aligned_storage<sizeof (int),
    std::alignment_of<double>::value>::type New_type;
int main()
    {
    std::cout << "alignment_of<int> == "
        << std::alignment_of<int>::value << std::endl;
    std::cout << "aligned to double == "
        << std::alignment_of<New_type>::value << std::endl;

    return (0);
    }
```

```Output
alignment_of<int> == 4
aligned to double == 8
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[alignment_of-Klasse](../standard-library/alignment-of-class.md)
