---
title: 'Criticalsectiontraits:: Getinvalidvalue-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- GetInvalidValue method
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4a23445cc9df0553a40d4f78a7ce3095a343d5d0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599235"
---
# <a name="criticalsectiontraitsgetinvalidvalue-method"></a>CriticalSectionTraits::GetInvalidValue-Methode

Spezialisiert hat eine **CriticalSection** Vorlage so, dass die Vorlage immer ungültig ist.

## <a name="syntax"></a>Syntax

```cpp
inline static Type GetInvalidValue();
```

## <a name="return-value"></a>Rückgabewert

Gibt immer einen Zeiger auf einen ungültigen kritischen Abschnitt zurück.

## <a name="remarks"></a>Hinweise

Die `Type` Modifizierer ist definiert als `typedef CRITICAL_SECTION* Type;`.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>Siehe auch

[CriticalSectionTraits-Struktur](../windows/criticalsectiontraits-structure.md)