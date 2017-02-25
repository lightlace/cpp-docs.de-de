---
title: "ITopologyExecutionResource-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::ITopologyExecutionResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITopologyExecutionResource-Struktur"
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
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