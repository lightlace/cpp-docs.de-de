---
title: add_lvalue_reference-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_lvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- is_lvalue_reference class
- is_lvalue_reference
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d21fcc27b5b4f92b690d8fae7669a18a5fcc1c46
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964937"
---
# <a name="islvaluereference-class"></a>is_lvalue_reference-Klasse

Testet, ob es sich beim Typ um einen lvalue-Verweis handelt.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_lvalue_reference;
```

### <a name="parameters"></a>Parameter

*Ty* der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz dieses typprädikats ist true, wenn der Typ *Ty* ist ein Verweis auf ein Objekt oder eine Funktion ist, andernfalls "false". Beachten Sie, dass *Ty* möglicherweise nicht in ein Rvalue-Verweis. Weitere Informationen zu „rvalues“ finden Sie unter [Rvalue Reference Declarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md) (Rvalue-Verweisdeklarator: &&).

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
