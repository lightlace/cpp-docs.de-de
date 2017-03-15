---
title: "DeferrableEventArgs::InvokeAllFinished-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 86b45205-3edb-4134-9cd0-ed7a7b4c3b1a
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
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