---
title: 'SRWLOCK:: Trylockexclusive-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
dev_langs:
- C++
helpviewer_keywords:
- TryLockExclusive method
ms.assetid: 661e8b19-3058-4511-8742-c9fbb90412c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 674a7dced019926e6ea07b41641eb42db70c45a0
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013479"
---
# <a name="srwlocktrylockexclusive-method"></a>SRWLock::TryLockExclusive-Methode
Versucht, für eine **SRWLock** Objekt im exklusiven Modus für den aktuellen oder angegebenen **SRWLock** Objekt. Wenn der Aufruf erfolgreich ist, wird der aufrufende Thread den Besitz der Sperre.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
SyncLockExclusive TryLockExclusive();  
  
static SyncLockExclusive TryLockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *lock*  
 Zeiger auf ein **SRWLock** Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei erfolgreicher Ausführung einen **SRWLock** Objekt im exklusiven Modus und der aufrufende Thread übernimmt den Besitz der Sperre. Andernfalls ein **SRWLock** Objekt, dessen Status ungültig ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [SRWLock-Klasse](../windows/srwlock-class.md)