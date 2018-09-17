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
ms.openlocfilehash: 6e9c1ab3ceb4965450f89de3b483915d693b5100
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711645"
---
# <a name="underlyingtype-class"></a>underlying_type-Klasse

Erzeugt für einen Enumerationstyp den zugrunde liegenden ganzzahligen Typ.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der zu ändernde Typ.

## <a name="remarks"></a>Hinweise

Die `type` TypeDef-Member der Vorlagenklasse benennt den zugrunde liegenden ganzzahligen Typ *T*Wenn *T* ist ein Enumerationstyp, andernfalls gibt es keinen TypeDef-Member ist `type`.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
