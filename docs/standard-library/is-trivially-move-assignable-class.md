---
title: is_trivially_move_assignable-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_move_assignable
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
ms.openlocfilehash: 4b349d328da995105a6217f4ab597da5d7eafc38
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689491"
---
# <a name="is_trivially_move_assignable-class"></a>is_trivially_move_assignable-Klasse

Testet, ob der Typ einen trivialen Verschiebezuweisungsoperator aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Parameter

*Ty* -\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist "true", wenn die *typität* eine Klasse ist, die einen trivialen Verschiebungs Zuweisungs Operator aufweist; andernfalls "false".

Ein Verschiebungs Zuweisungs Operator für eine Klassen- *Ty* ist in folgenden Fällen trivial:

- Er wird impliziert bereitgestellt
- die Klasse *Ty* hat keine virtuellen Funktionen.
- die Klasse *Ty* hat keine virtuellen Basen.
- Die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Verschiebungszuweisungsoperatoren
- Die Klassen aller nicht statischen Datenmember des Typarrays der Klasse haben triviale Verschiebungszuweisungsoperatoren

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
