---
title: CriticalSectionTraits-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
dev_langs:
- C++
helpviewer_keywords:
- CriticalSectionTraits structure
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5534173d594b8fc09ceca8ec44a1c1223bc550b2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33870550"
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
|`Type`|Ein `typedef` , einen Zeiger zu einem kritischen Abschnitt definiert. `Type` wird definiert als `typedef CRITICAL_SECTION* Type;`.|  
  
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