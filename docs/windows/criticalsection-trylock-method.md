---
title: 'CriticalSection:: TryLock-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
dev_langs:
- C++
helpviewer_keywords:
- TryLock method
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b4ee99d82212d0d6cdd610b4565bd9292a0265dc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883951"
---
# <a name="criticalsectiontrylock-method"></a>CriticalSection::TryLock-Methode
Versucht, einen kritischen Abschnitt ohne Blockierung zu geben. Wenn der Aufruf erfolgreich ist, übernimmt der aufrufende Thread den Besitz der kritische Abschnitt.  
  
## <a name="syntax"></a>Syntax  
  
```  
SyncLock TryLock();  
  
static SyncLock TryLock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cs`  
 Ein benutzerdefiniertes kritischen Abschnitt-Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Wert ungleich NULL, wenn der kritische Abschnitt erfolgreich eingegeben wird oder der aktuelle Thread besitzt bereits den kritischen Abschnitt. 0 (null), wenn ein anderer Thread den kritischen Abschnitt bereits besitzt.  
  
## <a name="remarks"></a>Hinweise  
 Die erste **TryLock** Funktion wirkt sich auf das aktuelle Objekt von kritischen Abschnitts. Die zweite **TryLock** Funktion wirkt sich auf ein benutzerdefiniertes kritischen Abschnitts.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [CriticalSection-Klasse](../windows/criticalsection-class.md)