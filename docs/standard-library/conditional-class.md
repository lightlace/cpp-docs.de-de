---
title: conditional-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::conditional
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
ms.openlocfilehash: be81a1bc32f2f86f1d79970868933bddb8dc3620
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523018"
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

*B*<br/>
Der Wert, der den ausgewählten Typ bestimmt.

*T1*<br/>
Das Typergebnis, wenn B „true“ ist.

*T2*<br/>
Das Typergebnis, wenn B „false“ ist.

## <a name="remarks"></a>Hinweise

Der TypeDef-Member von Vorlage `conditional<B, T1, T2>::type` ergibt *T1* beim *B* ergibt **"true"**, und ergibt *T2* beim  *B* ergibt **"false"**.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
