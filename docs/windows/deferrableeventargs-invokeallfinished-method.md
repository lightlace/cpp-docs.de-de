---
title: "DeferrableEventArgs::InvokeAllFinished-Methode"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 86b45205-3edb-4134-9cd0-ed7a7b4c3b1a
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# DeferrableEventArgs::InvokeAllFinished-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wird aufgerufen, um anzugeben, dass das Behandeln eines verzögerten Ereignisses abgeschlossen ist.  
  
## Syntax  
  
```cpp  
void InvokeAllFinished()  
```  
  
## Hinweise  
 Rufen Sie diese Methode auf, nachdem die Ereignisquelle [InvokeAll](../windows/eventsource-invokeall-method.md) aufgerufen hat.  Das Aufrufen dieser Methode verhindert weitere Verzögerungen und erzwingt die Ausführung des Abschlusshandlers, wenn keine Verzögerungen ausgeführt wurden.  
  
 Ein Codebeispiel finden Sie unter [DeferrableEventArgs\-Klasse](../windows/deferrableeventargs-class.md).  
  
## Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [DeferrableEventArgs\-Klasse](../windows/deferrableeventargs-class.md)   
 [EventSource::InvokeAll\-Methode](../windows/eventsource-invokeall-method.md)