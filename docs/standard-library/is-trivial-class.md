---
title: is_trivial-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivial
helpviewer_keywords:
- is_trivial
ms.assetid: 6beb11d4-2f38-4c7e-9959-ca5d26250df7
ms.openlocfilehash: 609fdd9c3d0d00eea607db4aefd31163234a9a00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526853"
---
# <a name="istrivial-class"></a>is_trivial-Klasse

Testet, ob der Typ ein einfacher Typ ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_trivial;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ist ein einfacher Typ ist; andernfalls ist Sie false. Einfache Typen sind skalare Typen, belanglos kopierbare Klassentypen, Arrays dieser Typen und cv-qualifizierte Versionen dieser Typen.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
