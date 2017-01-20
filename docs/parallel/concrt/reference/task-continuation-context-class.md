---
title: "task_continuation_context-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ppltasks/concurrency::task_continuation_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_continuation_context-Klasse"
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
caps.latest.revision: 15
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# task_continuation_context-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Mit der `task_continuation_context`\-Klasse können Sie angeben, an welcher Stelle eine Fortsetzung ausgeführt werden soll.  Es ist nur sinnvoll, diese Klasse von einer Windows Store\-App aus zu verwenden.  Bei Apps, die keine Windows Store\-Apps sind, wird der Ausführungskontext der Aufgabenfortsetzung von der Laufzeit bestimmt, und kann nicht konfiguriert werden.  
  
## Syntax  
  
```  
class task_continuation_context : public details::_ContextCallback;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[task\_continuation\_context::use\_arbitrary\-Methode](../Topic/task_continuation_context::use_arbitrary%20Method.md)|Erstellt einen Aufgabenfortsetzungskontext, der er es der Laufzeit ermöglicht, den Ausführungskontext für eine Fortsetzung auszuwählen.|  
|[task\_continuation\_context::use\_current\-Methode](../Topic/task_continuation_context::use_current%20Method.md)|Gibt ein Kontextobjekt für die Aufgabenfortsetzung zurück, das den aktuellen Ausführungskontext darstellt.|  
|[task\_continuation\_context::use\_default\-Methode](../Topic/task_continuation_context::use_default%20Method.md)|Erstellt den standardmäßigen Aufgabenfortsetzungskontext.|  
  
## Vererbungshierarchie  
 `_ContextCallback`  
  
 `task_continuation_context`  
  
## Anforderungen  
 **Header:** ppltasks.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task Class](assetId:///5389e8a5-5038-40b6-844a-55e9b58ad35f)