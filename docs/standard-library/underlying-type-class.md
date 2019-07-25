---
title: underlying_type-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::underlying_type
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
ms.openlocfilehash: 465383357e6c0306c24fe8325327327c3a3b64c1
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454987"
---
# <a name="underlyingtype-class"></a>underlying_type-Klasse

Erzeugt für einen Enumerationstyp den zugrunde liegenden ganzzahligen Typ.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Der `type` typedef-Member der Vorlagen Klasse benennt den zugrunde liegenden ganzzahligen Typ *t*, wenn *t* ein Enumerationstyp ist. andernfalls gibt es keinen Member `type`typedef.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
