---
title: 'Semaphoretraits:: Unlock-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 4e0ea808-b70d-43f7-81ef-998c3b34e3a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c9519fb79bf8229578319fc1f3890f5d2e19442a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448277"
---
# <a name="semaphoretraitsunlock-method"></a>SemaphoreTraits::Unlock-Methode

Releases-Steuerelement eine gemeinsam genutzte Ressource.

## <a name="syntax"></a>Syntax

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Handle für ein **Semaphor** Objekt.

## <a name="remarks"></a>Hinweise

Wenn sich "Entsperren"-Vorgangs nicht erfolgreich ist **Unlock()** gibt einen Fehler, der die Ursache des Fehlers angibt.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>Siehe auch

[SemaphoreTraits-Struktur](../windows/semaphoretraits-structure.md)