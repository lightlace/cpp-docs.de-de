---
title: 'SRWLOCK:: Trylockexclusive-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
dev_langs: C++
helpviewer_keywords: TryLockExclusive method
ms.assetid: 661e8b19-3058-4511-8742-c9fbb90412c7
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a23629ae5bc7d1645367019ea38d747779b84b16
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="srwlocktrylockexclusive-method"></a>SRWLock::TryLockExclusive-Methode
Versucht, ein SRWLock-Objekt im exklusiven Modus für das aktuelle oder angegebene SRWLock-Objekt zu erhalten. Wenn der Aufruf erfolgreich ist, wird der aufrufende Thread den Besitz der Sperre.  
  
## <a name="syntax"></a>Syntax  
  
```  
SyncLockExclusive TryLockExclusive();  
  
static SyncLockExclusive TryLockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `lock`  
 Zeiger auf ein SRWLock-Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei Erfolg wird ein SRWLock-Objekt im exklusiven Modus und der aufrufende Thread den Besitz der Sperre. Andernfalls ein SRWLock-Objekt, deren Zustand ungültig ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [SRWLock-Klasse](../windows/srwlock-class.md)