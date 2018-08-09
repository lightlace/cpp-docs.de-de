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
ms.openlocfilehash: b64f44e2188848a25e607c53171e25aa721e9bc4
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641365"
---
# <a name="criticalsectiontraitsunlock-method"></a>CriticalSectionTraits::Unlock-Methode
Spezialisiert hat eine `CriticalSection` Vorlage so, dass die It freigeben Besitzer des Objekts angegebenen kritischen Abschnitt unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
inline static void Unlock(  
   _In_ Type cs  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *cs*  
 Ein Zeiger auf ein Objekt des kritischen Abschnitts.  
  
## <a name="remarks"></a>Hinweise  
 Die `Type` Modifizierer ist definiert als `typedef CRITICAL_SECTION* Type;`.  
  
 Weitere Informationen finden Sie unter **Funktion LeaveCriticalSection** in die **Synchronisierungsfunktionen** Teil der Windows-API-Dokumentation.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Siehe auch  
 [CriticalSectionTraits-Struktur](../windows/criticalsectiontraits-structure.md)