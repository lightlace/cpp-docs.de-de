---
title: "unsupported_feature-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::unsupported_feature"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unsupported_feature-Klasse"
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# unsupported_feature-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die Ausnahme, die ausgelöst wird, wenn eine nicht unterstützte Funktion verwendet wird.  
  
## Syntax  
  
```  
class unsupported_feature : public runtime_exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[unsupported\_feature::unsupported\_feature\-Konstruktor](../Topic/unsupported_feature::unsupported_feature%20Constructor.md)|Erstellt eine neue Instanz der `unsupported_feature`\-Ausnahme.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `runtime_exception`  
  
 `unsupported_feature`  
  
## Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Nebenläufigkeit  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)