---
title: SRWLockSharedTraits-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
dev_langs:
- C++
helpviewer_keywords:
- SRWLockSharedTraits structure
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 50bcfc728a2f228e4fa8444fe41cc25c3ff449a2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602245"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits-Struktur

Beschreibt die allgemeinen Merkmale der `SRWLock` Klasse in freigegebene sperren.

## <a name="syntax"></a>Syntax

```cpp
struct SRWLockSharedTraits;
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`Type`|Synonym für einen Zeiger auf die [SRWLOCK](../windows/srwlock-class.md) Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[SRWLockSharedTraits::GetInvalidValue-Methode](../windows/srwlocksharedtraits-getinvalidvalue-method.md)|Ruft eine **SRWLockSharedTraits** -Objekt, das immer ungültig ist.|
|[SRWLockSharedTraits::Unlock-Methode](../windows/srwlocksharedtraits-unlock-method.md)|Exklusive Kontrolle über den angegebenen Versionen `SRWLock` Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`SRWLockSharedTraits`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Wrappers::HandleTraits-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)