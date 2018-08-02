---
title: 'Criticalsectiontraits:: Unlock-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2f66f185692c200ea459b88363143c0cc1af9d55
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466009"
---
# <a name="criticalsectiontraitsunlock-method"></a>CriticalSectionTraits::Unlock-Methode
Spezialisiert auf die Vorlage CriticalSection, damit sie freigeben Besitzer des Objekts angegebenen kritischen Abschnitt unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline static void Unlock(  
   _In_ Type cs  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *cs*  
 Ein Zeiger auf ein Objekt des kritischen Abschnitts.  
  
## <a name="remarks"></a>Hinweise  
 Die *Typ* Modifizierer ist definiert als `typedef CRITICAL_SECTION* Type;`.  
  
 Weitere Informationen finden Sie unter "LeaveCriticalSection-Funktion" im Abschnitt "Synchronisierung Functions" von der Windows-API-Dokumentation.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Siehe auch  
 [CriticalSectionTraits-Struktur](../windows/criticalsectiontraits-structure.md)