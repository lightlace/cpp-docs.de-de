---
title: SRWLockExclusiveTraits-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
dev_langs:
- C++
helpviewer_keywords:
- SRWLockExclusiveTraits structure
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 542ad92aa636c934e3250817931dd7f31d1fe85b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601602"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits-Struktur

Beschreibt die allgemeinen Merkmale der `SRWLock` Klasse im Sperrmodus für exklusive.

## <a name="syntax"></a>Syntax

```cpp
struct SRWLockExclusiveTraits;
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`Type`|Synonym für einen Zeiger auf die [SRWLOCK](../windows/srwlock-class.md) Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[SRWLockExclusiveTraits::GetInvalidValue-Methode](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|Ruft eine **SRWLockExclusiveTraits** -Objekt, das immer ungültig ist.|
|[SRWLockExclusiveTraits::Unlock-Methode](../windows/srwlockexclusivetraits-unlock-method.md)|Exklusive Kontrolle über den angegebenen Versionen `SRWLock` Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`SRWLockExclusiveTraits`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Wrappers::HandleTraits-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)