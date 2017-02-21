---
title: "invalid_link_target-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::invalid_link_target"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_link_target-Klasse"
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# invalid_link_target-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `link_target`\-Methode eines Meldungsblocks aufgerufen wird und der Meldungsblock keine Verknüpfung mit dem Ziel erstellen kann.  Dies kann das Ergebnis vom Überschreiten der Anzahl zulässiger Links für den Meldungsblock sein oder das Ergebnis von Versuchen, ein bestimmtes Ziel zweimal mit der gleichen Quelle zu verknüpfen.  
  
## Syntax  
  
```  
class invalid_link_target : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[invalid\_link\_target::invalid\_link\_target\-Konstruktor](../Topic/invalid_link_target::invalid_link_target%20Constructor.md)|Überladen.  Erstellt ein `invalid_link_target`\-Objekt.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `invalid_link_target`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md)