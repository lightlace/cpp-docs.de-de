---
title: "IResourceManager-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IResourceManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IResourceManager-Struktur"
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# IResourceManager-Struktur
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Eine Schnittstelle zum Ressourcen\-Manager der Concurrency Runtime.  Dies ist die Schnittstelle, über die Planer mit dem Ressourcen\-Manager kommunizieren.  
  
## Syntax  
  
```  
struct IResourceManager;  
```  
  
## Member  
  
### Öffentliche Enumerationen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[IResourceManager::OSVersion\-Enumeration](../Topic/IResourceManager::OSVersion%20Enumeration.md)|Ein enumerierter Typ, der die Betriebssystemversion darstellt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[IResourceManager::CreateNodeTopology\-Methode](../Topic/IResourceManager::CreateNodeTopology%20Method.md)|Diese Methode ist nur in Debugbuilds der Laufzeit vorhanden und ist ein Testhook, mit dem Tests des Ressourcen\-Managers auf unterschiedlichen Hardwaretopologien möglich sind, ohne tatsächlich die Hardware ändern zu müssen.  Bei Verkaufsversionsbuilds der Laufzeit gibt diese Methode einen Wert zurück, ohne irgendeine Aktion auszuführen.|  
|[IResourceManager::GetAvailableNodeCount\-Methode](../Topic/IResourceManager::GetAvailableNodeCount%20Method.md)|Gibt die Anzahl der Knoten zurück, die z Ressourcen\-Manager verfügbar sind.|  
|[IResourceManager::GetFirstNode\-Methode](../Topic/IResourceManager::GetFirstNode%20Method.md)|Gibt dem ersten Knoten in der Enumerationsreihenfolge zurück, wie vom Ressourcen\-Manager definiert.|  
|[IResourceManager::Reference\-Methode](../Topic/IResourceManager::Reference%20Method.md)|Inkrementiert die Verweiszähler der Ressourcen\-Manager\-Instanz.|  
|[IResourceManager::RegisterScheduler\-Methode](../Topic/IResourceManager::RegisterScheduler%20Method.md)|Registriert einen Planer beim Ressourcen\-Manager.  Sobald der Planer registriert wurde, sollte er mit dem Ressourcen\-Manager über die zurückgegebene `ISchedulerProxy`\-Schnittstelle kommunizieren.|  
|[IResourceManager::Release\-Methode](../Topic/IResourceManager::Release%20Method.md)|Dekrementiert die Verweiszähler der Ressourcen\-Manager\-Instanz.  Der Ressourcen\-Manager wird zerstört, wenn sein Verweiszähler auf `0` geht.|  
  
## Hinweise  
 Verwenden Sie die [CreateResourceManager](../Topic/CreateResourceManager%20Function.md)\-Funktion, um eine Schnittstelle für die Singleton\-Ressourcen\-Manager\-Instanz zu erhalten.  Die Methode inkrementiert auf dem Ressourcen\-Manager einen Verweiszähler. Sie sollten die [IResourceManager::Release](../Topic/IResourceManager::Release%20Method.md)\-Methode nach Verwendung des Ressourcen\-Managers aufrufen, um den Verweis freizugeben.  In der Regel ruft jeder Planer, den Sie erstellen, während der Erstellung diese Methode auf und gibt den Verweis auf den Ressourcen\-Manager frei, nachdem er geschlossen wurde.  
  
## Vererbungshierarchie  
 `IResourceManager`  
  
## Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ISchedulerProxy\-Struktur](../../../parallel/concrt/reference/ischedulerproxy-structure.md)   
 [IScheduler\-Struktur](../../../parallel/concrt/reference/ischeduler-structure.md)