---
title: 'CriticalSection:: Lock-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3c873494a702802b8ead3dab9cac28557664f618
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
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