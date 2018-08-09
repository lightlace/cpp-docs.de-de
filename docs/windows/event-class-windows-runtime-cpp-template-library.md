---
title: Event-Klasse (Windows Runtime C++-Vorlagenbibliothek) | Microsoft-Dokumentation
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
ms.openlocfilehash: c07d58f244bf2e7e6c9329196bae7b5bb323ce12
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644163"
---
# <a name="event-class-windows-runtime-c-template-library"></a>Ereignisklasse (C++-Vorlagenbibliothek der Windows-Runtime)
Stellt ein Ereignis dar.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
class Event : public HandleT<HandleTraits::EventTraits>;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Event::Event Constructor (C++-Vorlagenbibliothek der Windows Runtime)](../windows/event-event-constructor-windows-runtime-cpp-template-library.md)|Initialisiert eine neue Instanz der dem **Ereignis** Klasse.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Event::operator=-Operator](../windows/event-operator-assign-operator.md)|Weist dem angegebenen **Ereignis** Verweis auf das aktuelle **Ereignis** Instanz.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `HandleT`  
  
 `Event`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)