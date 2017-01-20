---
title: "unorm-Klasse"
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
  - "amp_short_vectors/Concurrency::graphics::unorm"
  - "amp/Concurrency::graphics::unorm"
dev_langs: 
  - "C++"
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
caps.latest.revision: 8
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# unorm-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Erstellen Sie eine unorm Zahl dar.  Jedes Element ist eine Gleitkommazahl im Bereich von \[0.0f, 1.0f\].  
  
## Syntax  
  
```  
class unorm;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[unorm::unorm\-Konstruktor](../Topic/unorm::unorm%20Constructor.md)|Überladen.  Standardkonstruktor.  Initialisieren Sie zu 0.0f.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|unorm::operator\- Operator||  
|unorm::operator float Operator|Konvertierungsoperator.  Konvertieren Sie die unorm Zahl einem Gleitkommawert.|  
|unorm::operator\*\= Operator||  
|unorm::operator\-\/\=operator||  
|unorm::operator\+\+\-Operator||  
|unorm::operator\+\=\-Operator||  
|unorm::operator\= Operator||  
|unorm::operator\-\= Operator||  
  
## Vererbungshierarchie  
 `unorm`  
  
## Anforderungen  
 **Header:** amp\_short\_vectors.h  
  
 **Namespace:** Concurrency::graphics  
  
## Siehe auch  
 [Concurrency::graphics\-Namespace](../../../parallel/amp/reference/concurrency-graphics-namespace.md)