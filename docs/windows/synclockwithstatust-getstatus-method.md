---
title: 'Synclockwithstatust:: GetStatus-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
dev_langs:
- C++
helpviewer_keywords:
- GetStatus method
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a54cab831d3e3180a28f892fcf37c7351c22bc33
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014961"
---
# <a name="synclockwithstatustgetstatus-method"></a>SyncLockWithStatusT::GetStatus-Methode
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
DWORD GetStatus() const;  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Das Ergebnis eines Vorgangs warten auf das Objekt, das basierend auf den **SyncLockWithStatusT** Klasse, z. B. eine [Mutex](../windows/mutex-class1.md) oder [Semaphor](../windows/semaphore-class.md). 0 (null) gibt an, dass es sich bei der "Wait"-Vorgang auf den signalisierten Zustand zurückgegeben; Andernfalls ist einen anderen Status aufgetreten, z. B. Timeoutwert verstrichen.  
  
## <a name="remarks"></a>Hinweise  
 Ruft den Wartestatus "des aktuellen **SyncLockWithStatusT** Objekt.  
  
 Die GetStatus()-Funktion ruft den Wert des zugrunde liegenden [Status_](../windows/synclockwithstatust-status-data-member.md) -Datenmember. Bei der ein Objekt auf Grundlage der **SyncLockWithStatusT** Klasse führt einen Vorgang, der das Objekt zuerst wartet darauf, dass das Objekt verfügbar sind. Das Ergebnis des Wartevorgangs befindet sich in der `status_` -Datenmember. Mögliche Werte für die `status_` Datenmember sind die Rückgabewerte des Wartevorgangs. Weitere Informationen finden Sie auf die Rückgabewerte von der `WaitForSingleObjectEx()` -Funktion in der MSDN Library.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Siehe auch  
 [SyncLockWithStatusT-Klasse](../windows/synclockwithstatust-class.md)