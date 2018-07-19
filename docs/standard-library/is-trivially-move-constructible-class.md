---
title: is_trivially_move_constructible-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 316ffdee4905ff8a35baef7137ff7f28a2846786
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958191"
---
# <a name="istriviallymoveconstructible-class"></a>is_trivially_move_constructible-Klasse

Testet, ob der Typ einen trivialen Bewegungskonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Parameter

*Ty* der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* ist eine Klasse, die einen trivialen bewegungskonstruktor, andernfalls er false enthält.

Ein bewegungskonstruktor für eine Klasse *Ty* ist trivial wenn:

Er wird implizit deklariert.

die Parametertypen entsprechen den einer impliziten Deklaration

die Klasse *Ty* verfügt über keine virtuellen Funktionen

die Klasse *Ty* hat keine virtuellen Basen

die Klasse verfügt über keine flüchtigen nicht statischen Datenmember

alle direkten Basisklassen der Klasse *Ty* haben triviale bewegungskonstruktoren

die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Bewegungskonstruktoren

die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Bewegungskonstruktoren

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
