---
title: alignment_of-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::alignment_of
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
ms.openlocfilehash: 5222e70965db69d33ec62039bf9013a52d145705
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456450"
---
# <a name="alignmentof-class"></a>alignment_of-Klasse

Ruft die Ausrichtung des angegebenen Typs ab. Diese Struktur wird in Bezug auf [alignof](../cpp/alignof-and-alignas-cpp.md) implementiert. Verwenden Sie `alignof` direkt, wenn Sie einen Ausrichtungswert einfach abfragen müssen. Verwenden Sie „alignment_of“, wenn Sie eine integrale Konstante benötigen, beispielsweise beim Versenden eines Tags.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>Parameter

*Genossenschaft*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Die typabfrage enthält den Wert der Ausrichtung der typität.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[aligned_storage-Klasse](../standard-library/aligned-storage-class.md)
