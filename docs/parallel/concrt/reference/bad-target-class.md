---
title: "bad_target-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::bad_target"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_target-Klasse"
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# bad_target-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die dann ausgelöst wird, wenn einem Meldungsblock ein Zeiger auf ein Ziel zugeordnet wird, das für die auszuführende Operation ungültig ist.  
  
## Syntax  
  
```  
class bad_target : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[bad\_target::bad\_target\-Konstruktor](../Topic/bad_target::bad_target%20Constructor.md)|Überladen.  Erstellt ein `bad_target`\-Objekt.|  
  
## Hinweise  
 Diese Ausnahme wird in der Regel aus Gründen ausgelöst, wie einem Ziel, das versucht, eine Meldung zu nutzen, die für ein anderes Ziel reserviert ist, oder das eine Reservierung freigibt, die es nicht verwaltet.  
  
## Vererbungshierarchie  
 `exception`  
  
 `bad_target`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md)