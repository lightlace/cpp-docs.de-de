---
title: "progress_reporter-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppltasks/concurrency::progress_reporter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "progress_reporter-Klasse"
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# progress_reporter-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die Status\-Reporter\-Klasse ermöglicht Benachrichtigungen zum Status der Berichterstellung eines bestimmten Typs.  Jedes progress\_reporter\-Objekt ist an eine bestimmte asynchrone Aktion bzw. einen Vorgang gebunden.  
  
## Syntax  
  
```  
template<  
   typename _ProgressType  
>  
class progress_reporter;  
```  
  
#### Parameter  
 `_ProgressType`  
 Der Nutzlasttyp jeder Statusbenachrichtigung, die vom Status\-Reporter gemeldet wird.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[progress\_reporter::progress\_reporter\-Konstruktor](../Topic/progress_reporter::progress_reporter%20Constructor.md)||  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[progress\_reporter::report\-Methode](../Topic/progress_reporter::report%20Method.md)|Sendet einen Statusbericht an die asynchrone Aktion oder den asynchronen Vorgang, an die bzw. an den dieser Status\-Reporter gebunden ist.|  
  
## Hinweise  
 Dieser Typ ist nur für Windows Store\-Apps verfügbar.  
  
## Vererbungshierarchie  
 `progress_reporter`  
  
## Anforderungen  
 **Header:** ppltasks.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [create\_async\-Funktion](../Topic/create_async%20Function.md)