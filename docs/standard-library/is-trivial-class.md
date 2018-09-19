---
title: is_trivial-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivial
dev_langs:
- C++
helpviewer_keywords:
- is_trivial
ms.assetid: 6beb11d4-2f38-4c7e-9959-ca5d26250df7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41c09d35c81d8b9f9b8b2e629eabd1ec9a5ec8d9
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44099576"
---
# <a name="istrivial-class"></a>is_trivial-Klasse

Testet, ob der Typ ein einfacher Typ ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_trivial;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ist ein einfacher Typ ist; andernfalls ist Sie false. Einfache Typen sind skalare Typen, belanglos kopierbare Klassentypen, Arrays dieser Typen und cv-qualifizierte Versionen dieser Typen.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
