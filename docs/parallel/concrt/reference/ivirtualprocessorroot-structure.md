---
title: "IVirtualProcessorRoot-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IVirtualProcessorRoot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IVirtualProcessorRoot-Struktur"
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# IVirtualProcessorRoot-Struktur
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Eine Abstraktion für einen Hardwarethread, auf dem ein Threadproxy ausgeführt werden kann.  
  
## Syntax  
  
```  
struct IVirtualProcessorRoot : public IExecutionResource;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[IVirtualProcessorRoot::Activate\-Methode](../Topic/IVirtualProcessorRoot::Activate%20Method.md)|Veranlasst, dass der der Ausführungskontextschnittstelle `pContext` zugeordnete Threadproxy auf diesem virtuellen Prozessorstamm ausgeführt wird.|  
|[IVirtualProcessorRoot::Deactivate\-Methode](../Topic/IVirtualProcessorRoot::Deactivate%20Method.md)|Veranlasst, dass der derzeit auf diesem virtuellen Prozessorstamm ausgeführte Threadproxy die Weiterleitung im Ausführungskontext beendet.  Der Threadproxy setzt die Ausführung eines Aufrufs der `Activate`\-Methode fort.|  
|[IVirtualProcessorRoot::EnsureAllTasksVisible\-Methode](../Topic/IVirtualProcessorRoot::EnsureAllTasksVisible%20Method.md)|Veranlasst, dass in der Arbeitsspeicherhierarchie einzelner Prozessoren gespeicherte Daten für alle Prozessoren auf dem System sichtbar werden.  Stellt sicher, dass ein vollständiger Arbeitsspeicherzaun auf allen Prozessoren ausgeführt wurde, bevor die Methode zurückkehrt.|  
|[IVirtualProcessorRoot::GetId\-Methode](../Topic/IVirtualProcessorRoot::GetId%20Method.md)|Gibt einen eindeutigen Bezeichner für den virtuellen Prozessorstamm zurück.|  
  
## Hinweise  
 Jeder virtuelle Prozessorstamm hat eine zugeordnete Ausführungsressource.  Die `IVirtualProcessorRoot`\-Schnittstelle erbt von der [IExecutionResource](../../../parallel/concrt/reference/iexecutionresource-structure.md)\-Schnittstelle.  Mehrere virtuelle Prozessorstämme können auf denselben zugrunde liegenden Hardwarethread verweisen.  
  
 Der Ressourcen\-Manager gewährt Planern als Reaktion auf Anforderungen für Ressourcen Stämme virtueller Prozessoren.  Ein Planer mithilfe eines virtuellen Prozessorstamms Arbeiten ausführen, indem er mit einem Ausführungskontext aktiviert wird.  
  
## Vererbungshierarchie  
 [IExecutionResource](../../../parallel/concrt/reference/iexecutionresource-structure.md)  
  
 `IVirtualProcessorRoot`  
  
## Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)