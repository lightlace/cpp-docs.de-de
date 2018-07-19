---
title: is_trivial-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivial
dev_langs:
- C++
helpviewer_keywords:
- is_trivial
ms.assetid: 6beb11d4-2f38-4c7e-9959-ca5d26250df7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4eef350723dd8658bfc349495e905466e8179db1
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965918"
---
# <a name="istrivial-class"></a>is_trivial-Klasse

Testet, ob der Typ ein einfacher Typ ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_trivial;
```

### <a name="parameters"></a>Parameter

*T* der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ist ein einfacher Typ ist; andernfalls ist Sie false. Einfache Typen sind skalare Typen, belanglos kopierbare Klassentypen, Arrays dieser Typen und cv-qualifizierte Versionen dieser Typen.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
