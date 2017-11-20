---
title: 'CriticalSection:: Lock-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
dev_langs: C++
helpviewer_keywords: Lock method
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4df91ea9030ca4917f246bc05be1ba059673680e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="criticalsectionlock-method"></a>CriticalSection::Lock-Methode
Wartet auf den Besitz des Objekts angegebenen kritischen Abschnitts. Gibt die Funktion, wenn der aufrufende Thread den Besitz gewährt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
SyncLock Lock();  
  
   static SyncLock Lock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cs`  
 Ein benutzerdefiniertes kritischen Abschnitt-Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Sperrobjekt, das verwendet werden kann, um den aktuellen kritischen Abschnitt zu entsperren.  
  
## <a name="remarks"></a>Hinweise  
 Die erste **Sperre** Funktion wirkt sich auf das aktuelle Objekt von kritischen Abschnitts. Die zweite **Sperre** Funktion wirkt sich auf ein benutzerdefiniertes kritischen Abschnitts.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [CriticalSection-Klasse](../windows/criticalsection-class.md)