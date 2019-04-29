---
title: is_rvalue_reference-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_rvalue_reference
helpviewer_keywords:
- is_rvalue_reference class
- is_rvalue_reference
ms.assetid: 40a97072-7b5c-4274-9154-298d3dcf064a
ms.openlocfilehash: ea3be02db2a4a840ed8f8b8a253d7409c26cf759
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413592"
---
# <a name="isrvaluereference-class"></a>is_rvalue_reference-Klasse

Testet, ob es sich beim Typ um einen „rvalue“-Verweis handelt.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_rvalue_reference;
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz dieses typprädikats ist true, wenn der Typ *Ty* ist ein [Rvalue-Verweis](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
