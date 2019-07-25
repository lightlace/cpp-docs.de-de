---
title: is_trivially_copy_assignable-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
ms.openlocfilehash: c0019257a032d3becc268513336ed59e58a2e1d5
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447995"
---
# <a name="istriviallycopyassignable-class"></a>is_trivially_copy_assignable-Klasse

Testet, ob der Typ einen trivialen Kopierzuweisungsoperator aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist "true", wenn der Typ " *T* " eine Klasse ist, die einen trivialen Kopier Zuweisungs Operator aufweist; andernfalls "false".

Ein Zuweisungskonstruktor für eine Klasse *t* ist trivial, wenn er implizit bereitgestellt wird. die Klasse *t* verfügt über keine virtuellen Funktionen, die Klasse *t* verfügt über keine virtuellen Basen, die Klassen aller nicht statischen Datenmember des Klassen Typs haben triviale Zuweisung. Operatoren und die Klassen aller nicht statischen Datenmember des Typarray der Klasse haben triviale Zuweisungs Operatoren.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
