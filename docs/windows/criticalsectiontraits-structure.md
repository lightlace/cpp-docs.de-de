---
title: CriticalSectionTraits-Struktur | Microsoft-Dokumentation
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
ms.openlocfilehash: 8b10d130190308520771e37e97d34238f75670ad
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466682"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits-Struktur
Spezialisiert auf ein CriticalSection-Objekt einen ungültigen kritischen Bereich oder eine Funktion, die einen kritischen Abschnitt release unterstützen.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CriticalSectionTraits;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`Type`|Ein **Typedef** , die einen Zeiger auf einen kritischen Abschnitt definiert. `Type` wird definiert als `typedef CRITICAL_SECTION* Type;`.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CriticalSectionTraits::GetInvalidValue-Methode](../windows/criticalsectiontraits-getinvalidvalue-method.md)|Spezialisiert hat eine `CriticalSection` Vorlage so, dass die Vorlage immer ungültig ist.|  
|[CriticalSectionTraits::Unlock-Methode](../windows/criticalsectiontraits-unlock-method.md)|Spezialisiert hat eine `CriticalSection` Vorlage so, dass die It freigeben Besitzer des Objekts angegebenen kritischen Abschnitt unterstützt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CriticalSectionTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers::HandleTraits-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)