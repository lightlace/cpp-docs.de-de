---
title: is_copy_assignable-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_copy_assignable
ms.assetid: 3ae6bca1-85fb-4829-9ee9-0183b081ff50
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65ac9dc44da5126673ee1f0699f5a5dd9dcb87e1
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960780"
---
# <a name="iscopyassignable-class"></a>is_copy_assignable-Klasse

Testet, ob der Typ durch Zuweisung kopiert werden kann.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>Parameter

*Ty* der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* ist eine Klasse, die ein Kopierzuweisungsoperator verwendet, andernfalls er false enthält. Entspricht is_assignable\<Ty&, const Ty&>.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
