---
title: "location-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::location"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "location-Klasse"
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# location-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die Abstraktion eines physischen Speicherorts auf der Hardware.  
  
## Syntax  
  
```  
class location;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[location::location\-Konstruktor](../Topic/location::location%20Constructor.md)|Überladen.  Erstellt ein `location`\-Objekt.|  
|[location::~location\-Destruktor](../Topic/location::~location%20Destructor.md)|Zerstört ein `location`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[location::current\-Methode](../Topic/location::current%20Method.md)|Gibt ein `location`\-Objekt zurück, das den meisten bestimmten Ort darstellt, den der aufrufende Thread ausgeführt wird.|  
|[location::from\_numa\_node\-Methode](../Topic/location::from_numa_node%20Method.md)|Gibt ein `location`\-Objekt zurück, das einen angegebenen NUMA\-Knoten darstellt.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[location::operator\!\=\-Operator](../Topic/location::operator!=%20Operator.md)|Bestimmt, ob zwei `location`\-Objekte unterschiedliche Position darstellen.|  
|[location::operator\=\-Operator](../Topic/location::operator=%20Operator.md)|Weist den Inhalt eines anderen `location`\-Objekts bis dies zu.|  
|[location::operator\=\=\-Operator](../Topic/location::operator==%20Operator.md)|Bestimmt, ob zwei `location`\-Objekte auf die gleiche Position darstellen.|  
  
## Vererbungshierarchie  
 `location`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)