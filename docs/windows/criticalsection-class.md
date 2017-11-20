---
title: Critical_section-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::CriticalSection
dev_langs: C++
helpviewer_keywords: CriticalSection class
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 89587f87bd71d2688bba2c128d28c01212b50b71
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="criticalsection-class"></a>CriticalSection-Klasse
Stellt ein kritisches Abschnittsobjekt dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CriticalSection;  
```  
  
## <a name="members"></a>Member  
  
### <a name="constructor"></a>Konstruktor  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CriticalSection::CriticalSection-Konstruktor](../windows/criticalsection-criticalsection-constructor.md)|Initialisiert ein Synchronisierungsobjekt, das ein Mutex-Objekt ähnelt, jedoch kann von nur die Threads eines einzelnen Prozesses verwendet werden.|  
|[CriticalSection::~CriticalSection-Destruktor](../windows/criticalsection-tilde-criticalsection-destructor.md)|Hebt die Initialisierung und das aktuelle CriticalSection-Objekt zerstört.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CriticalSection::TryLock-Methode](../windows/criticalsection-trylock-method.md)|Versucht, einen kritischen Abschnitt ohne Blockierung zu geben. Wenn der Aufruf erfolgreich ist, übernimmt der aufrufende Thread den Besitz der kritische Abschnitt.|  
|[CriticalSection::Lock-Methode](../windows/criticalsection-lock-method.md)|Wartet auf den Besitz des Objekts angegebenen kritischen Abschnitts. Gibt die Funktion, wenn der aufrufende Thread den Besitz gewährt wird.|  
|[CriticalSection::IsValid-Methode](../windows/criticalsection-isvalid-method.md)|Gibt an, ob der aktuelle kritische Abschnitt gültig ist.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CriticalSection::cs_-Datenmember](../windows/criticalsection-cs-data-member.md)|Deklariert einen kritischen Abschnitt Datenmember.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CriticalSection`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)