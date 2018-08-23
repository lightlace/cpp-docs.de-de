---
title: 'Criticalsectiontraits:: Unlock-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 003bb9c845ef8124ade1262a25368d3d4cb34fa6
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606430"
---
# <a name="criticalsectiontraitsunlock-method"></a>CriticalSectionTraits::Unlock-Methode

Spezialisiert hat eine `CriticalSection` Vorlage so, dass die It freigeben Besitzer des Objekts angegebenen kritischen Abschnitt unterstützt.

## <a name="syntax"></a>Syntax

```cpp
inline static void Unlock(
   _In_ Type cs
);
```

### <a name="parameters"></a>Parameter

*cs*  
Ein Zeiger auf ein Objekt des kritischen Abschnitts.

## <a name="remarks"></a>Hinweise

Die `Type` Modifizierer ist definiert als `typedef CRITICAL_SECTION* Type;`.

Weitere Informationen finden Sie unter **Funktion LeaveCriticalSection** in die **Synchronisierungsfunktionen** Teil der Windows-API-Dokumentation.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>Siehe auch

[CriticalSectionTraits-Struktur](../windows/criticalsectiontraits-structure.md)