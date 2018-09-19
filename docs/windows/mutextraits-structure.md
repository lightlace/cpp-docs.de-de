---
title: MutexTraits-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
dev_langs:
- C++
helpviewer_keywords:
- MutexTraits structure
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 529265c4b1e5f510a92295a1ceff6d0a012163fe
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42584170"
---
# <a name="mutextraits-structure"></a>MutexTraits-Struktur

Definiert die allgemeinen Merkmale der [Mutex](../windows/mutex-class1.md) Klasse.

## <a name="syntax"></a>Syntax

```cpp
struct MutexTraits : HANDLENullTraits;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[MutexTraits::Unlock-Methode](../windows/mutextraits-unlock-method.md)|Gibt die exklusive Kontrolle über eine freigegebene Ressource frei.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HANDLENullTraits`

`MutexTraits`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Wrappers::HandleTraits-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)