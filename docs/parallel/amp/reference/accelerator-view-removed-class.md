---
title: "accelerator_view_removed-Klasse"
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
  - "amprt/Concurrency::accelerator_view_removed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "amprt/Concurrency::accelerator_view_removed-Klasse"
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
caps.latest.revision: 6
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# accelerator_view_removed-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die Ausnahme, die ausgelöst wird, wenn ein zugrunde liegender DirectX\-Aufruf aufgrund des Windows\-TDR\-Mechanismus \(Timeout Detection and Recovery\) fehlschlägt.  
  
## Syntax  
  
```  
class accelerator_view_removed : public runtime_exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[accelerator\_view\_removed::accelerator\_view\_removed\-Konstruktor](../Topic/accelerator_view_removed::accelerator_view_removed%20Constructor.md)|Initialisiert eine neue Instanz der `accelerator_view_removed`\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[accelerator\_view\_removed::get\_view\_removed\_reason\-Methode](../Topic/accelerator_view_removed::get_view_removed_reason%20Method.md)|Gibt einen HRESULT\-Fehlercode zurück, die die Ursache des Entfernens `accelerator_view` des Objekts angibt.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Nebenläufigkeit  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)