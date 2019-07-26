---
title: is_standard_layout-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_standard_layout
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
ms.openlocfilehash: 4f999eaa4a5c1ea7e9672a5efdc6000a4d3d9759
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457418"
---
# <a name="isstandardlayout-class"></a>is_standard_layout-Klasse

Testet, ob der Typ ein Standardlayout ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_standard_layout;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Ty*|Der abzufragende Typ.|

## <a name="remarks"></a>Hinweise

Eine Instanz dieses typprädikats ist "true",  wenn die typität eine Klasse ist, die über ein Standardlayout von Element Objekten im Arbeitsspeicher verfügt, andernfalls "false".

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
