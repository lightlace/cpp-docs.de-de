---
title: EventTargetArray-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray
dev_langs:
- C++
helpviewer_keywords:
- EventTargetArray class
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4461004a1681d9095449c51fb9cb3973d5017693
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881308"
---
# <a name="eventtargetarray-class"></a>EventTargetArray-Klasse
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
class EventTargetArray : public Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<ClassicCom>, IUnknown>;  
```  
  
## <a name="remarks"></a>Hinweise  
 Stellt ein Array von Ereignishandlern.  
  
 Die Ereignishandler, die zugeordnet sind ein [EventSource](../windows/eventsource-class.md) Objekt in einem geschützten EventTargetArray-Datenmember gespeichert sind.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[EventTargetArray::EventTargetArray-Konstruktor](../windows/eventtargetarray-eventtargetarray-constructor.md)|Initialisiert eine neue Instanz der EventTargetArray-Klasse.|  
|[EventTargetArray::~EventTargetArray-Destruktor](../windows/eventtargetarray-tilde-eventtargetarray-destructor.md)|Hebt die Initialisierung der aktuellen EventTargetArray-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[EventTargetArray::AddTail-Methode](../windows/eventtargetarray-addtail-method.md)|Fügt den angegebenen Ereignishandler an das Ende des internen Arrays von Ereignishandlern an.|  
|[EventTargetArray::Begin-Methode](../windows/eventtargetarray-begin-method.md)|Ruft die Adresse des ersten Elements im internen Array von Ereignishandlern.|  
|[EventTargetArray::End-Methode](../windows/eventtargetarray-end-method.md)|Ruft die Adresse des letzten Elements im internen Array von Ereignishandlern.|  
|[EventTargetArray::Length-Methode](../windows/eventtargetarray-length-method.md)|Ruft die aktuelle Anzahl der Elemente im internen Array von Ereignishandlern.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `EventTargetArray`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)