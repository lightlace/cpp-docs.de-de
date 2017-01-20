---
title: "EventTargetArray-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::EventTargetArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EventTargetArray-Klasse"
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# EventTargetArray-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL-Infrastruktur und ist nicht direkt aus dem Code verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class EventTargetArray : public Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<ClassicCom>, IUnknown>;  
```  
  
## <a name="remarks"></a>Hinweise  
 Stellt ein Array der Ereignishandler.  
  
 Die Ereignishandler, die zugeordnet sind ein [EventSource](../windows/eventsource-class.md) Objekt in einen geschützten Member der EventTargetArray-Daten gespeichert werden.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Eventtargetarray:: Eventtargetarray-Konstruktor](../windows/eventtargetarray-eventtargetarray-constructor.md)|Initialisiert eine neue Instanz der EventTargetArray-Klasse.|  
|[EventTargetArray:: ~ EventTargetArray-Destruktor](../windows/eventtargetarray-tilde-eventtargetarray-destructor.md)|Hebt die Initialisierung der aktuellen EventTargetArray-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Eventtargetarray:: Addtail-Methode](../windows/eventtargetarray-addtail-method.md)|Fügt den angegebenen Ereignishandler an das Ende des internen Arrays der Ereignishandler.|  
|[Eventtargetarray:: Begin-Methode](../windows/eventtargetarray-begin-method.md)|Ruft die Adresse des ersten Elements in der Ereignishandler des internen Arrays ab.|  
|[Eventtargetarray:: End-Methode](../windows/eventtargetarray-end-method.md)|Ruft die Adresse des letzten Elements in das interne Array von Ereignishandler ab.|  
|[Eventtargetarray:: Length-Methode](../windows/eventtargetarray-length-method.md)|Ruft die aktuelle Anzahl der Elemente in das interne Array von Ereignishandler ab.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `EventTargetArray`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::wrl::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)