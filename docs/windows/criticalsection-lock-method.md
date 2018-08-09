---
title: 'CriticalSection:: Lock-Methode | Microsoft-Dokumentation'
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
ms.openlocfilehash: ee66017edabf80349bf2960f7cb2ca2654c8c4cc
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643578"
---
# <a name="criticalsectionlock-method"></a>CriticalSection::Lock-Methode
Wartet auf den Besitz des Objekts angegebenen kritischen Abschnitt. Gibt die Funktion zurück, wenn der aufrufende Thread den Besitz gewährt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
SyncLock Lock();  
  
   static SyncLock Lock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *cs*  
 Ein Kritischer Abschnitt Benutzer angegebene-Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Sperrobjekt, das verwendet werden kann, um den aktuellen kritischen Abschnitt zu entsperren.  
  
## <a name="remarks"></a>Hinweise  
 Die erste **Sperre** Funktion wirkt sich auf das aktuelle Objekt des kritischen Abschnitts. Die zweite **Sperre** Funktion wirkt sich auf einen vom Benutzer angegebenen kritischen Abschnitt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [CriticalSection-Klasse](../windows/criticalsection-class.md)