---
title: CriticalSectionTraits-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
dev_langs:
- C++
helpviewer_keywords:
- CriticalSectionTraits structure
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c24d8dea31a87094329276af3ebfaf9f06136adc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits-Struktur
Spezialisiert ein CriticalSection-Objekt, um einen ungültigen kritischen Abschnitt oder eine Funktion zum Freigeben eines kritischen Abschnitts zu unterstützen.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CriticalSectionTraits;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`Type`|Ein `typedef` , einen Zeiger zu einem kritischen Abschnitt definiert. `Type`wird definiert als `typedef CRITICAL_SECTION* Type;`.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CriticalSectionTraits::GetInvalidValue-Methode](../windows/criticalsectiontraits-getinvalidvalue-method.md)|CriticalSection Vorlage spezialisiert, damit, dass die Vorlage immer ungültig ist.|  
|[CriticalSectionTraits::Unlock-Methode](../windows/criticalsectiontraits-unlock-method.md)|Eine Vorlage CriticalSection spezialisiert, damit sie freigeben Besitzer des Objekts angegebenen kritischen Abschnitt unterstützt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CriticalSectionTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers::HandleTraits-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)