---
title: "Ereignisklasse (C++-Vorlagenbibliothek der Windows-Runtime)"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Event"
dev_langs: 
  - "C++"
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# Ereignisklasse (C++-Vorlagenbibliothek der Windows-Runtime)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt ein Ereignis dar.  
  
## Syntax  
  
```  
class Event : public HandleT<HandleTraits::EventTraits>;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Event::Event Constructor \(C\+\+\-Vorlagenbibliothek der Windows Runtime\)](../windows/event-event-constructor-windows-runtime-cpp-template-library.md)|Initialisiert eine neue Instanz der Ereignisklasse.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Event::operator\=\-Operator](../windows/event-operator-assign-operator.md)|Weist den angegebenen Ereignisverweis der aktuellen Ereignisinstanz zu.|  
  
## Vererbungshierarchie  
 `HandleT`  
  
 `Event`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers\-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)