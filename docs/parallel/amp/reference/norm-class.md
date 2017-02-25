---
title: "norm-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_short_vectors/Concurrency::graphics::norm"
dev_langs: 
  - "C++"
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# norm-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Erstellen Sie eine Normenzahl dar.  Jedes Element ist eine Gleitkommazahl im Bereich von \[\- 1.0f, 1.0f\].  
  
## Syntax  
  
```  
class norm;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[norm::norm\- Konstruktor](../Topic/norm::norm%20Constructor.md)|Überladen.  Standardkonstruktor.  Initialisieren Sie zu 0.0f.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|norm::operator\- Operator||  
|norm::operator\- Operator||  
|norm::operator float Operator|Konvertierungsoperator.  Konvertieren Sie die Normenzahl einem Gleitkommawert.|  
|norm::operator\*\= Operator||  
|norm::operator\-\/\=operator||  
|norm::operator\+\+\-Operator||  
|norm::operator\+\=\-Operator||  
|norm::operator\= Operator||  
|norm::operator\-\= Operator||  
  
## Vererbungshierarchie  
 `norm`  
  
## Anforderungen  
 **Header:** amp\_short\_vectors.h  
  
 **Namespace:** Concurrency::graphics  
  
## Siehe auch  
 [Concurrency::graphics\-Namespace](../../../parallel/amp/reference/concurrency-graphics-namespace.md)