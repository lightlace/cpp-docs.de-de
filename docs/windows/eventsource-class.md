---
title: EventSource-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::EventSource
dev_langs: C++
helpviewer_keywords: EventSource class
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 705260547d5a42b463d61b79c38592874f9dfa19
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="eventsource-class"></a>EventSource-Klasse
Stellt ein Ereignis dar. EventSource-Memberfunktionen hinzufügen, entfernen und Ereignishandler aufrufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<  
   typename TDelegateInterface  
>  
class EventSource;  
```  
  
#### <a name="parameters"></a>Parameter  
 `TDelegateInterface`  
 Die Schnittstelle, ein Delegat, der einen Ereignishandler darstellt.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[EventSource::EventSource-Konstruktor](../windows/eventsource-eventsource-constructor.md)|Initialisiert eine neue Instanz der EventSource-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[EventSource::Add-Methode](../windows/eventsource-add-method.md)|Fügt den Ereignishandler, die durch die Schnittstelle des angegebenen Delegaten dargestellt wird, auf den Satz der Ereignishandler für das aktuelle EventSource-Objekt.|  
|[EventSource::GetSize-Methode](../windows/eventsource-getsize-method.md)|Ruft die Anzahl der Ereignishandler, die dem aktuellen EventSource-Objekt zugeordnet|  
|[EventSource::InvokeAll-Methode](../windows/eventsource-invokeall-method.md)|Ruft die jeder Ereignishandler, die dem aktuellen EventSource-Objekt, das mit den angegebenen Argumenttypen und -Argumente zugeordnet.|  
|[EventSource::Remove-Methode](../windows/eventsource-remove-method.md)|Löscht den Ereignishandler, dargestellt durch das angegebene Ereignistoken für die Registrierung aus dem Satz von Ereignishandlern, die dem aktuellen EventSource-Objekt zugeordnet.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[EventSource::addRemoveLock_-Datenmember](../windows/eventsource-addremovelock-data-member.md)|Synchronisiert den Zugriff auf die [Targets_](../windows/eventsource-targets-data-member.md) Array beim Hinzufügen, entfernen oder Ereignishandler aufrufen.|  
|[EventSource::targets_-Datenmember](../windows/eventsource-targets-data-member.md)|Ein Array von ein oder mehrere Ereignishandler.|  
|[EventSource::targetsPointerLock_-Datenmember](../windows/eventsource-targetspointerlock-data-member.md)|Synchronisiert den Zugriff auf interne Datenmember, sogar wenn Ereignishandler für diese Ereignisquelle hinzugefügt werden, entfernt oder aufgerufen.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `EventSource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)