---
title: 'SRWLOCK:: Trylockshared-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
dev_langs:
- C++
helpviewer_keywords:
- TryLockShared method
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7c36657b5c732055260dc77471e109961a66c144
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="srwlocktrylockshared-method"></a>SRWLock::TryLockShared-Methode
Versucht, ein SRWLock-Objekt im freigegebenen Modus für das aktuelle oder angegebene SRWLock-Objekt zu erhalten.  
  
## <a name="syntax"></a>Syntax  
  
```  
WRL_NOTHROW SyncLockShared TryLockShared();  
WRL_NOTHROW static SyncLockShared TryLockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `lock`  
 Zeiger auf ein SRWLock-Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg wird ein SRWLock-Objekt im Modus für gemeinsame Nutzung und der aufrufende Thread den Besitz der Sperre. Andernfalls ein SRWLock-Objekt, deren Zustand ungültig ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [SRWLock-Klasse](../windows/srwlock-class.md)