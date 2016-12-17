---
title: "scheduler_worker_creation_error-Klasse"
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
  - "concrt/concurrency::scheduler_worker_creation_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scheduler_worker_creation_error-Klasse"
ms.assetid: 4aec1c3e-c32a-41b2-899d-2d898f23b3c7
caps.latest.revision: 9
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# scheduler_worker_creation_error-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die aufgrund eines Fehlers bei der Erstellung eines Workerausführungskontexts in der Concurrency Runtime ausgelöst wird.  
  
## Syntax  
  
```  
class scheduler_worker_creation_error : public scheduler_resource_allocation_error;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[scheduler\_worker\_creation\_error::scheduler\_worker\_creation\_error\-Konstruktor](../Topic/scheduler_worker_creation_error::scheduler_worker_creation_error%20Constructor.md)|Überladen.  Erstellt ein `scheduler_worker_creation_error`\-Objekt.|  
  
## Hinweise  
 Diese Ausnahme wird üblicherweise ausgelöst, wenn ein Aufruf an das Betriebssystem, mit der Ausführungskontexten aus der Concurrency Runtime zu erstellen fehlschlägt.  Ausführungskontexte dass Threads, die Aufgaben in der Concurrency Runtime ausführen.  Der Fehlercode, der normalerweise von einem Aufruf der Win32\-Methode `GetLastError` zurückgegeben würde, wird einem Wert des Typs `HRESULT` konvertiert und mit der Basisklassenmethode `get_error_code` abgerufen werden.  
  
## Vererbungshierarchie  
 `exception`  
  
 [scheduler\_resource\_allocation\_error](../../../parallel/concrt/reference/scheduler-resource-allocation-error-class.md)  
  
 `scheduler_worker_creation_error`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)