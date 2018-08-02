---
title: CriticalSection-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CriticalSection class
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0b8aa37f6ac12cad91fa02a2387c95911227319d
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466136"
---
# <a name="criticalsection-class"></a>CriticalSection-Klasse
Stellt ein kritisches Abschnittsobjekt dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CriticalSection;  
```  
  
## <a name="members"></a>Member  
  
### <a name="constructor"></a>Konstruktor  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CriticalSection::CriticalSection-Konstruktor](../windows/criticalsection-criticalsection-constructor.md)|Initialisiert ein Synchronisierungsobjekt, das ist vergleichbar mit dem ein Mutex-Objekt, aber nur die Threads eines einzelnen Prozesses verwendet werden kann.|  
|[CriticalSection::~CriticalSection-Destruktor](../windows/criticalsection-tilde-criticalsection-destructor.md)|Hebt die Initialisierung und zerstört die aktuelle **CriticalSection** Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CriticalSection::TryLock-Methode](../windows/criticalsection-trylock-method.md)|Versucht, einen kritischen Abschnitt ohne Blockierung zu geben. Wenn der Aufruf erfolgreich ist, übernimmt der aufrufende Thread den kritischen Abschnitt.|  
|[CriticalSection::Lock-Methode](../windows/criticalsection-lock-method.md)|Wartet auf den Besitz des Objekts angegebenen kritischen Abschnitt. Gibt die Funktion zurück, wenn der aufrufende Thread den Besitz gewährt wird.|  
|[CriticalSection::IsValid-Methode](../windows/criticalsection-isvalid-method.md)|Gibt an, ob der aktuelle kritische Abschnitt gültig ist.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CriticalSection::cs_-Datenmember](../windows/criticalsection-cs-data-member.md)|Deklariert einen Datenmember des kritischen Abschnitts.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CriticalSection`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)