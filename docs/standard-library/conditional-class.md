---
title: conditional-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::conditional
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
ms.openlocfilehash: b8f0f69cc1e4f6966bc9ccb63fe529436295badd
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457326"
---
# <a name="conditional-class"></a>conditional-Klasse

Wählt einen von zwei Typen, abhängig von der angegebenen Bedingung.

## <a name="syntax"></a>Syntax

```cpp
template <bool B, class T1, class T2>
struct conditional;

template <bool _Test, class _T1, class _T2>
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```

### <a name="parameters"></a>Parameter

*B*\
Der Wert, der den ausgewählten Typ bestimmt.

*T1*\
Das Typergebnis, wenn B „true“ ist.

*T2*\
Das Typergebnis, wenn B „false“ ist.

## <a name="remarks"></a>Hinweise

Die `conditional<B, T1, T2>::type` typedef-Vorlage wird als *T1* ausgewertet, wenn *b* als **true**ausgewertet wird, und wird zu *T2* ausgewertet, wenn *b* als **false**ausgewertet wird.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
