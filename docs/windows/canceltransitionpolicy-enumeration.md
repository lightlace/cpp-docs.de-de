---
title: CancelTransitionPolicy-Enumeration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
dev_langs:
- C++
helpviewer_keywords:
- CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: abc49a62e1cc9fb4abdc56b329b8fa057edebde7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583516"
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

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)