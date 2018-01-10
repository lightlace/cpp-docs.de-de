---
title: 'Synclockwithstatust:: GetStatus-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
dev_langs: C++
helpviewer_keywords: GetStatus method
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 181735766e62aa1bf8c306bd425c6e6b03b2066d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="synclockwithstatustgetstatus-method"></a>SyncLockWithStatusT::GetStatus-Methode
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
DWORD GetStatus() const;  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Das Ergebnis einer "Wait"-Vorgang für das Objekt, das die SyncLockWithStatusT-Klasse, wie z. B. basiert eine [Mutex](../windows/mutex-class1.md) oder [Semaphore](../windows/semaphore-class.md). 0 (null) gibt an, dass der "Wait"-Vorgang mit dem Zustand "signalisiert" zurückgegeben; Andernfalls ist einen anderen Zustand aufgetreten, z. B. Timeoutwert ist verstrichen.  
  
## <a name="remarks"></a>Hinweise  
 Ruft den Wait-Status des aktuellen SyncLockWithStatusT-Objekts ab.  
  
 Die GetStatus()-Funktion ruft den Wert des zugrunde liegenden [Status_](../windows/synclockwithstatust-status-data-member.md) -Datenmember. Wenn ein Objekt basierend auf der SyncLockWithStatusT-Klasse einen Vorgang ausführt, wartet das Objekt zuerst für das Objekt verfügbar ist. Das Ergebnis dieses Wartevorgangs wird gespeichert, der `status_` -Datenmember. Die möglichen Werte für die `status_` Datenmember sind die Rückgabewerte des Wartevorgangs. Weitere Informationen finden Sie unter die Rückgabewerte der **WaitForSingleObjectEx()** Funktion in der MSDN Library.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Siehe auch  
 [SyncLockWithStatusT-Klasse](../windows/synclockwithstatust-class.md)