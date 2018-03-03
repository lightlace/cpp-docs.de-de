---
title: 'Criticalsectiontraits:: Unlock-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f9880364c24b1e2e5889e9e9e2666683c2237f7f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsectiontraitsunlock-method"></a>CriticalSectionTraits::Unlock-Methode
Eine Vorlage CriticalSection spezialisiert, damit sie freigeben Besitzer des Objekts angegebenen kritischen Abschnitt unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline static void Unlock(  
   _In_ Type cs  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cs`  
 Ein Zeiger auf ein kritisches Abschnittsobjekt.  
  
## <a name="remarks"></a>Hinweise  
 Die *Typ* Modifizierer ist definiert als `typedef CRITICAL_SECTION* Type;`.  
  
 Weitere Informationen finden Sie unter "LeaveCriticalSection Function" im Abschnitt "Synchronisierungsfunktionen" der Windows-API-Dokumentation.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Siehe auch  
 [CriticalSectionTraits-Struktur](../windows/criticalsectiontraits-structure.md)