---
title: EventSource-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: a98d8997ebfb5b21b3e469b2aacca15cde4a5319
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570534"
---
# <a name="eventsource-class"></a>EventSource-Klasse
Stellt ein nicht-agile-Ereignis. **EventSource** Member-Funktionen hinzufügen, entfernen und die Ereignishandler aufruft. Verwenden Sie für agile-Ereignisse [AgileEventSource](agileeventsource-class.md). 
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename TDelegateInterface>  
class EventSource;  
```  
  
### <a name="parameters"></a>Parameter  
 *TDelegateInterface*  
 Die Schnittstelle, ein Delegat, der einen Ereignishandler darstellt.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[EventSource::EventSource-Konstruktor](../windows/eventsource-eventsource-constructor.md)|Initialisiert eine neue Instanz der dem **EventSource** Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[EventSource::Add-Methode](../windows/eventsource-add-method.md)|Fügt den Ereignishandler, die durch die Schnittstelle für die angegebenen Delegaten dargestellt wird, auf den Satz von Ereignishandlern für die aktuelle **EventSource** Objekt.|  
|[EventSource::GetSize-Methode](../windows/eventsource-getsize-method.md)|Ruft die Anzahl der aktuellen zugeordneten Ereignishandler **EventSource** Objekt|  
|[EventSource::InvokeAll-Methode](../windows/eventsource-invokeall-method.md)|Ruft jede Ereignishandler verknüpft ist, mit dem aktuellen **EventSource** -Objekt mit den angegebenen Argumenttypen und der Argumente.|  
|[EventSource::Remove-Methode](../windows/eventsource-remove-method.md)|Löscht den Ereignishandler, die durch das angegebene Ereignis Registrierungstoken dargestellt wird, aus dem Satz von Ereignishandlern verknüpft ist, mit dem aktuellen **EventSource** Objekt.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[EventSource::addRemoveLock_-Datenmember](../windows/eventsource-addremovelock-data-member.md)|Synchronisiert den Zugriff auf die [Targets_](../windows/eventsource-targets-data-member.md) Arrays beim Hinzufügen, entfernen oder Ereignishandler aufrufen.|  
|[EventSource::targets_-Datenmember](../windows/eventsource-targets-data-member.md)|Ein Array von einem oder mehreren Ereignishandlern.|  
|[EventSource::targetsPointerLock_-Datenmember](../windows/eventsource-targetspointerlock-data-member.md)|Synchronisiert den Zugriff auf interne Datenmember, die auch bei der Ereignishandler für diese Ereignisquelle hinzugefügt, entfernt oder aufgerufen.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `EventSource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)  
 [AgileEventSource-Klasse](agileeventsource-class.md)