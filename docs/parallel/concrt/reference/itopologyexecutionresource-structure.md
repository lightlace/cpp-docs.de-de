---
title: "ITopologyExecutionResource-Struktur"
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
  - "concrtrm/concurrency::ITopologyExecutionResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITopologyExecutionResource-Struktur"
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
caps.latest.revision: 10
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# ITopologyExecutionResource-Struktur
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Eine Schnittstelle zu einer vom Ressourcen\-Manager definierten Ausführungsressource.  
  
## Syntax  
  
```  
struct ITopologyExecutionResource;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ITopologyExecutionResource::GetId\-Methode](../Topic/ITopologyExecutionResource::GetId%20Method.md)|Gibt dem eindeutigen Bezeichner des Ressourcen\-Managers für diese Ausführungsressource zurück.|  
|[ITopologyExecutionResource::GetNext\-Methode](../Topic/ITopologyExecutionResource::GetNext%20Method.md)|Gibt eine Schnittstelle zur folgenden Ausführungsressource in der Enumerationsreihenfolge zurück.|  
  
## Hinweise  
 Diese Schnittstelle wird in der Regel verwendet, um die Topologie des Systems zu durchlaufen, wie vom Ressourcen\-Manager beachtet.  
  
## Vererbungshierarchie  
 `ITopologyExecutionResource`  
  
## Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)