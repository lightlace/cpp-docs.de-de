---
title: EventSource-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource
dev_langs:
- C++
helpviewer_keywords:
- EventSource class
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b2d466b317927cd8de259637450b68b6aaf13bd5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876513"
---
# <a name="eventsource-class"></a>EventSource-Klasse
Stellt ein nicht-agile-Ereignis. EventSource-Memberfunktionen hinzufügen, entfernen und Ereignishandler aufrufen. Verwenden Sie für agile-Ereignisse [AgileEventSource](agileeventsource-class.md). 
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename TDelegateInterface>  
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
 [Microsoft:: wrl-Namespace](../windows/microsoft-wrl-namespace.md)
[AgileEventSource-Klasse](agileeventsource-class.md)