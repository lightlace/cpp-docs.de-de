---
title: add_lvalue_reference-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_lvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- is_lvalue_reference class
- is_lvalue_reference
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c3dc413835dfcbb04594e356ef86bc06da7aa8f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="islvaluereference-class"></a>is_lvalue_reference-Klasse

Testet, ob es sich beim Typ um einen lvalue-Verweis handelt.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_lvalue_reference;
```

### <a name="parameters"></a>Parameter

`Ty` Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz dieses Typprädikats ist TRUE, wenn der `Ty`-Typ ein Verweis auf ein Objekt oder eine Funktion ist; andernfalls FALSE. Beachten Sie, dass es sich beim `Ty`-Typ möglicherweise nicht um einen rvalue-Verweis handelt. Weitere Informationen zu Rvalues finden Sie unter [Rvalue-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
