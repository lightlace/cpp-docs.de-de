---
title: "critical_section-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::critical_section"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "critical_section-Klasse"
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# critical_section-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ein nicht wieder eintretender Mutex, der explizit die Concurrency Runtime beachtet.  
  
## Syntax  
  
```  
class critical_section;  
```  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`native_handle_type`|Ein Verweis auf ein `critical_section`\-Objekt.|  
  
### Öffentliche Klassen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[critical\_section::scoped\_lock\-Klasse](../Topic/critical_section::scoped_lock%20Class.md)|Ein ausnahmesicherer RAII\-Wrapper für ein `critical_section`\-Objekt.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[critical\_section::critical\_section\-Konstruktor](../Topic/critical_section::critical_section%20Constructor.md)|Erstellt einen neuen kritischen Abschnitt.|  
|[critical\_section::~critical\_section\-Destruktor](../Topic/critical_section::~critical_section%20Destructor.md)|Zerstört einen kritischen Abschnitt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[critical\_section::lock\-Methode](../Topic/critical_section::lock%20Method.md)|Ruft diesen kritischen Abschnitt ab.|  
|[critical\_section::native\_handle\-Methode](../Topic/critical_section::native_handle%20Method.md)|Gibt ein plattformspezifisches systemeigenes Handle zurück, sofern vorhanden.|  
|[critical\_section::try\_lock\-Methode](../Topic/critical_section::try_lock%20Method.md)|Versucht, die Sperre ohne Blockierung abzurufen.|  
|[critical\_section::try\_lock\_for\-Methode](../Topic/critical_section::try_lock_for%20Method.md)|Versucht, die Sperre erhalten, ohne dass für eine bestimmte Anzahl von Millisekunden blockieren.|  
|[critical\_section::unlock\-Methode](../Topic/critical_section::unlock%20Method.md)|Hebt die Sperre des kritischen Abschnitts auf.|  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Synchronisierungsdatenstrukturen](../../../parallel/concrt/synchronization-data-structures.md).  
  
## Vererbungshierarchie  
 `critical_section`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [reader\_writer\_lock\-Klasse](../../../parallel/concrt/reference/reader-writer-lock-class.md)