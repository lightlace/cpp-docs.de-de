---
title: is_move_assignable-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_move_assignable
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3af5cbeae84b5b582077f543a39cfe408575bc71
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960055"
---
# <a name="ismoveassignable-class"></a>is_move_assignable-Klasse

Prüft, ob dem Typ eine Verschiebung zugewiesen werden kann.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Parameter

*T* der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Einem Typ kann eine Verschiebung zugewiesen werden, wenn ein rvalue-Verweis auf den Typ einem Verweis auf den Typ zugewiesen werden kann. Das Typprädikat entspricht `is_assignable<T&, T&&>`. Verschieben von zuweisbaren Typen beinhaltet verweisbare skalare Typen und Klassentypen, die entweder vom Compiler generierte oder benutzerdefinierte Bewegungszuweisungsoperatoren haben.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
