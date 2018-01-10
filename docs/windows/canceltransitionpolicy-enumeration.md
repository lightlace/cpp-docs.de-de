---
title: CancelTransitionPolicy-Enumeration | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
dev_langs: C++
helpviewer_keywords: CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 14c3016d767e38e032a745a5957fa93d51f2dae8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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