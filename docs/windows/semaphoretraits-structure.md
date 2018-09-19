---
title: SemaphoreTraits-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits
dev_langs:
- C++
helpviewer_keywords:
- SemaphoreTraits structure
ms.assetid: eddb8576-d063-409b-9201-cc87ca5d111e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5919b84a8b7b0b24588958198da89271d2a20119
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601819"
---
# <a name="semaphoretraits-structure"></a>SemaphoreTraits-Struktur

Definiert die allgemeinen Merkmale einer **Semaphor** Objekt.

## <a name="syntax"></a>Syntax

```cpp
struct SemaphoreTraits : HANDLENullTraits;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[SemaphoreTraits::Unlock-Methode](../windows/semaphoretraits-unlock-method.md)|Releases-Steuerelement eine gemeinsam genutzte Ressource.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HANDLENullTraits`

`SemaphoreTraits`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Wrappers::HandleTraits-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)