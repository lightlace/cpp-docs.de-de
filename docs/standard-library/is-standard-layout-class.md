---
title: is_standard_layout-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_standard_layout
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
ms.openlocfilehash: 75691c1b09b71580474cc22cdc8382bff55a5e29
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500281"
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

Eine Instanz dieses typprädikats ist true, wenn der Typ *Ty* ist eine Klasse, die ein Standardlayout der Memberobjekte im Arbeitsspeicher, andernfalls er false enthält.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
