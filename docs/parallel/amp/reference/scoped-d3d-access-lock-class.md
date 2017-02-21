---
title: "scoped_d3d_access_lock-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# scoped_d3d_access_lock-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

RAII\-Wrapper für eine D3D\-Zugriffssperre auf einem accelerator\_view\-Objekt.  
  
## Syntax  
  
```  
class scoped_d3d_access_lock;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[scoped\_d3d\_access\_lock::scoped\_d3d\_access\_lock\-Konstruktor](../Topic/scoped_d3d_access_lock::scoped_d3d_access_lock%20Constructor.md)|Überladen.  Erstellt ein `scoped_d3d_access_lock`\-Objekt.  Die Sperre wird aufgehoben, wenn dieses Objekt den Gültigkeitsbereich verlässt.|  
|[scoped\_d3d\_access\_lock::~scoped\_d3d\_access\_lock\-Destruktor](../Topic/scoped_d3d_access_lock::~scoped_d3d_access_lock%20Destructor.md)|Gibt die D3D\-Zugriffssperre auf dem zugeordneten `accelerator_view`\-Objekt frei.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[scoped\_d3d\_access\_lock::operator\= Operator](../Topic/scoped_d3d_access_lock::operator=%20Operator.md)|Übernimmt den Besitz einer Sperre eines anderen `scoped_d3d_access_lock`\-Objekts.|  
  
## Vererbungshierarchie  
 `scoped_d3d_access_lock`  
  
## Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** concurrency::direct3d  
  
## Siehe auch  
 [Concurrency::direct3d\-Namespace](../../../parallel/amp/reference/concurrency-direct3d-namespace.md)