---
title: is_trivially_copy_assignable-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 688252b4b361357f4dba862574ce6698d61b7c86
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102758"
---
# <a name="istriviallycopyassignable-class"></a>is_trivially_copy_assignable-Klasse

Testet, ob der Typ einen trivialen Kopierzuweisungsoperator aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ist eine Klasse, die einen trivialen Kopierzuweisungsoperator, andernfalls er false enthält.

Ein Zuweisungskonstruktor für eine Klasse *T* ist trivial, wenn er implizit angegeben ist. die Klasse *T* verfügt über keine virtuellen Funktionen, die Klasse *T* hat keine virtuellen Basen, die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Zuweisungsoperatoren und die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Zuweisungsoperatoren.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
