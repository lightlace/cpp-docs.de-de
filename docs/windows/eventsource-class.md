---
title: "EventSource-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EventSource-Klasse"
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# EventSource-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt ein Ereignis dar.  EventSource\-Memberfunktionen hinzufügen, entfernen und rufen Ereignishandler auf.  
  
## Syntax  
  
```  
template<  
   typename TDelegateInterface  
>  
class EventSource;  
```  
  
#### Parameter  
 `TDelegateInterface`  
 Die Schnittstelle für einen Delegaten, der einen Ereignishandler darstellt.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[EventSource::EventSource\-Konstruktor](../windows/eventsource-eventsource-constructor.md)|Initialisiert eine neue Instanz der EventSource\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[EventSource::Add\-Methode](../windows/eventsource-add-method.md)|Fügt den Ereignishandler an, der von der angegebenen Delegatschnittstelle das Festlegen von Ereignishandlern für das aktuelle EventSource\-Objekt dargestellt wird.|  
|[EventSource::GetSize\-Methode](../windows/eventsource-getsize-method.md)|Ruft die Anzahl von Ereignishandlern ab, die dem aktuellen EventSource\-Objekt zugeordnet werden|  
|[EventSource::InvokeAll\-Methode](../windows/eventsource-invokeall-method.md)|Ruft jeden Ereignishandler dem aktuellen EventSource\-Objekt mithilfe der angegebenen Argumenttypen und der Argumente auf.|  
|[EventSource::Remove\-Methode](../windows/eventsource-remove-method.md)|Löscht den Ereignishandler, der durch das angegebene Ereignisregistrierungstoken im Satz der Ereignishandler dargestellt wird, die dem aktuellen EventSource\-Objekt zugeordnet werden.|  
  
### Geschützte Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[EventSource::addRemoveLock\_\-Datenmember](../windows/eventsource-addremovelock-data-member.md)|Synchronisiert Zugriff auf das [targets\_](../windows/eventsource-targets-data-member.md) Array, wenn Ereignishandler, Hinzufügen, Entfernen, oder aufgerufen wird.|  
|[EventSource::targets\_\-Datenmember](../windows/eventsource-targets-data-member.md)|Ein Array mehrere Ereignishandler.|  
|[EventSource::targetsPointerLock\_\-Datenmember](../windows/eventsource-targetspointerlock-data-member.md)|Synchronisiert Zugriff auf die internen Datenmember, auch während Ereignishandler für dieses EventSource hinzugefügt, entfernt oder aufgerufen werden.|  
  
## Vererbungshierarchie  
 `EventSource`  
  
## Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)