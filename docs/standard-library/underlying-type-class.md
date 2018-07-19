---
title: underlying_type-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::underlying_type
dev_langs:
- C++
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b3f796d5039900b591c219c840d1aef94d23e8f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957580"
---
# <a name="underlyingtype-class"></a>underlying_type-Klasse

Erzeugt für einen Enumerationstyp den zugrunde liegenden ganzzahligen Typ.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>Parameter

*T*  
 Der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Die `type` TypeDef-Member der Vorlagenklasse benennt den zugrunde liegenden ganzzahligen Typ *T*Wenn *T* ist ein Enumerationstyp, andernfalls gibt es keinen TypeDef-Member ist `type`.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
