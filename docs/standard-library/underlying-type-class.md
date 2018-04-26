---
title: underlying_type-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- type_traits/std::underlying_type
dev_langs:
- C++
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52bf41cdcb40c88f32adc6d0384bea60f5997286
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="underlyingtype-class"></a>underlying_type-Klasse

Erzeugt für einen Enumerationstyp den zugrunde liegenden ganzzahligen Typ.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>Parameter

`T` Die zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Der typedef-Member `type` der Vorlagenklasse benennt den zugrunde liegenden ganzzahligen Typ von `T`, wenn `T` ein Enumerationstyp ist, andernfalls gibt es keinen typedef-Member `type`.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
