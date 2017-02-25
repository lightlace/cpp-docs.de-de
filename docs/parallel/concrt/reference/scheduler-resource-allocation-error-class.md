---
title: "scheduler_resource_allocation_error-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::scheduler_resource_allocation_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scheduler_resource_allocation_error-Klasse"
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# scheduler_resource_allocation_error-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die aufgrund eines Fehlers ausgelöst wird, um in der Concurrency Runtime eine wichtige Ressource abzurufen.  
  
## Syntax  
  
```  
class scheduler_resource_allocation_error : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[scheduler\_resource\_allocation\_error::scheduler\_resource\_allocation\_error\-Konstruktor](../Topic/scheduler_resource_allocation_error::scheduler_resource_allocation_error%20Constructor.md)|Überladen.  Erstellt ein `scheduler_resource_allocation_error`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[scheduler\_resource\_allocation\_error::get\_error\_code\-Methode](../Topic/scheduler_resource_allocation_error::get_error_code%20Method.md)|Gibt den Fehlercode zurück, der die Ausnahme ausgelöst hat.|  
  
## Hinweise  
 Diese Ausnahme wird in der Regel ausgelöst, wenn ein Aufruf des Betriebssystems von innerhalb der Concurrency Runtime fehlschlägt.  Der Fehlercode, der normalerweise von einem Aufruf der Win32\-Methode `GetLastError` zurückgegeben würde, wird einem Wert des Typs `HRESULT` konvertiert und mit der `get_error_code`\-Methode abgerufen werden.  
  
## Vererbungshierarchie  
 `exception`  
  
 `scheduler_resource_allocation_error`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)