---
title: CancelTransitionPolicy-Enumeration
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
helpviewer_keywords:
- CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
ms.openlocfilehash: cfd8e25f98ec1001a8fbd287eaec12408b9f240e
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335950"
---
# <a name="canceltransitionpolicy-enumeration"></a>CancelTransitionPolicy-Enumeration

Gibt an, wie ein asynchroner Vorgang, den Übergang zu einem abschließenden Zustand Versuchs abgeschlossen ist oder Fehler in Bezug auf eine Clientanforderung Zustand "abgebrochen" Verhalten.

## <a name="syntax"></a>Syntax

```cpp
enum CancelTransitionPolicy;
```

## <a name="members"></a>Member

### <a name="values"></a>Werte

|Name|Beschreibung|
|----------|-----------------|
|`RemainCanceled`|Wenn der asynchrone Vorgang derzeit ein vom Client angefordertes Zustand "abgebrochen" ist, bedeutet dies, dass es sich bei es verbleibt im Zustand "abgebrochen" im Gegensatz zu den Übergang zu einer Terminal abgeschlossen oder der Status "Fehler".|
|`TransitionFromCanceled`|Wenn der asynchrone Vorgang derzeit ein vom Client angefordertes Zustand "abgebrochen" ist, gibt dies an, dass Zustand wechseln sollte von dem Zustand "abgebrochen", den abschließenden Zustand abgeschlossen oder einen Fehler, die durch den Aufruf festgelegt, der dieses Flag verwendet.|

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](microsoft-wrl-namespace.md)