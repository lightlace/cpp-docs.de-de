---
title: is_trivial-Klasse | Microsoft-Dokumentation
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
- type_traits/std::is_trivial
dev_langs:
- C++
helpviewer_keywords:
- is_trivial
ms.assetid: 6beb11d4-2f38-4c7e-9959-ca5d26250df7
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7f6da587ec523db28b133f4219d5c35faa11734a
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="istrivial-class"></a>is_trivial-Klasse

Testet, ob der Typ ein einfacher Typ ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_trivial;
```

### <a name="parameters"></a>Parameter

`T` Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist „true“, wenn der Typ `T` ein einfacher Typ ist; andernfalls „false“. Einfache Typen sind skalare Typen, belanglos kopierbare Klassentypen, Arrays dieser Typen und cv-qualifizierte Versionen dieser Typen.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
