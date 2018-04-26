---
title: make_unsigned-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::make_unsigned
dev_langs:
- C++
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aba0421ab55d5cf30b38f69e58123fbd4056d16f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="makeunsigned-class"></a>make_unsigned-Klasse

Macht den Typ oder den kleinsten Typ ohne Vorzeichen größer oder gleich dem Typ.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`T`|Der zu ändernde Typ.|

## <a name="remarks"></a>Hinweise

Eine Instanz des Typmodifizierers enthält einen GeänderteTyp an, wenn der `T` als `is_unsigned<T>` true ist. Andernfalls ist dies der kleinste Datentyp mit Vorzeichen `ST`, für den `sizeof (T) <= sizeof (ST)`.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
