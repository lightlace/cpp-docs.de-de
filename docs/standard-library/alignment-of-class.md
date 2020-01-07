---
title: alignment_of-Klasse
ms.date: 12/11/2019
f1_keywords:
- type_traits/std::alignment_of
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
ms.openlocfilehash: d241848edf57fe4876c35e22f1762abf5d6888fa
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302314"
---
# <a name="alignment_of-class"></a>alignment_of-Klasse

Ruft die Ausrichtung des angegebenen Typs ab. Diese Struktur wird in Bezug auf [alignof](../cpp/alignment-cpp-declarations.md) implementiert. Verwenden Sie " **alignof** " direkt, wenn Sie einen Ausrichtungs Wert einfach Abfragen müssen. Verwenden Sie „alignment_of“, wenn Sie eine integrale Konstante benötigen, beispielsweise beim Versenden eines Tags.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>Parameters

*Ty* -\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Die typabfrage enthält den Wert der Ausrichtung der *typität*.

## <a name="requirements"></a>-Anforderungen

**Header:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[aligned_storage-Klasse](../standard-library/aligned-storage-class.md)
