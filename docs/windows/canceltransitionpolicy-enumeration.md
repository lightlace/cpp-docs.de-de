---
title: CancelTransitionPolicy-Enumeration | Microsoft Docs
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
ms.openlocfilehash: 64f588e67066fed690271aa7d78fcbe726c67177
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860345"
---
# <a name="canceltransitionpolicy-enumeration"></a>CancelTransitionPolicy-Enumeration
Gibt an, wie ein asynchroner Vorgang, den Übergang zu einem abgeschlossenen Zustand des Versuchs abgeschlossen oder Verhalten sich Fehler in Bezug auf eine Clientanforderung Zustand "abgebrochen".  
  
## <a name="syntax"></a>Syntax  
  
```  
enum CancelTransitionPolicy;  
```  
  
## <a name="members"></a>Member  
  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`RemainCanceled`|Wenn der asynchrone Vorgang derzeit in einer Clientanforderung Zustand "abgebrochen" ist, bedeutet dies, dass es sich im Zustand "abgebrochen" im Gegensatz zu den Übergang zu einer Terminal abgeschlossen oder den Status "Fehler" verbleibt.|  
|`TransitionFromCanceled`|Wenn der asynchrone Vorgang derzeit in einer Clientanforderung Zustand "abgebrochen" ist, gibt dies an, dass Zustand übergehen sollten von dem Zustand, den abschließenden Zustand "abgebrochen" abgeschlossen oder Fehler, wie durch den Aufruf bestimmt, die dieses Flag nutzt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)