---
title: Event-Klasse (Windows Runtime C++-Vorlagenbibliothek) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
dev_langs:
- C++
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 12c9e5bfe01de0a9864ff1e94364e0c42178ad11
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="event-class-windows-runtime-c-template-library"></a>Ereignisklasse (C++-Vorlagenbibliothek der Windows-Runtime)
Stellt ein Ereignis dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class Event : public HandleT<HandleTraits::EventTraits>;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Event::Event Constructor (C++-Vorlagenbibliothek der Windows Runtime)](../windows/event-event-constructor-windows-runtime-cpp-template-library.md)|Initialisiert eine neue Instanz der Ereignisklasse.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Event::operator=-Operator](../windows/event-operator-assign-operator.md)|Weist den angegebenen Ereignisverweis der aktuellen Ereignisinstanz zu.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `HandleT`  
  
 `Event`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)