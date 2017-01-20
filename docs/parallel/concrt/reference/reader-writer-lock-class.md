---
title: "reader_writer_lock-Klasse"
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
  - "concrt/concurrency::reader_writer_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reader_writer_lock-Klasse"
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
caps.latest.revision: 21
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# reader_writer_lock-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Eine im Writer festgelegte, warteschlangenbasierte Lese\-\/Schreibsperre mit ausschließlich lokalem Spinning.  Die Sperre gewährt "First In, First Out"\-Zugriff \(FIFO\-Zugriff\) auf Writer und blockiert Reader unter einer fortlaufenden Last von Writern.  
  
## Syntax  
  
```  
class reader_writer_lock;  
```  
  
## Member  
  
### Öffentliche Klassen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[reader\_writer\_lock::scoped\_lock\-Klasse](../Topic/reader_writer_lock::scoped_lock%20Class.md)|Ein ausnahmesicherer RAII\-Wrapper, der verwendet werden kann, um `reader_writer_lock`\-Sperrobjekte als Writer abzurufen.|  
|[reader\_writer\_lock::scoped\_lock\_read\-Klasse](../Topic/reader_writer_lock::scoped_lock_read%20Class.md)|Ein ausnahmesicherer RAII\-Wrapper, der verwendet werden kann, um `reader_writer_lock`\-Sperrobjekte als Reader abzurufen.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[reader\_writer\_lock::reader\_writer\_lock\-Konstruktor](../Topic/reader_writer_lock::reader_writer_lock%20Constructor.md)|Erstellt ein neues `reader_writer_lock`\-Objekt.|  
|[reader\_writer\_lock::~reader\_writer\_lock\-Destruktor](../Topic/reader_writer_lock::~reader_writer_lock%20Destructor.md)|Zerstört das `reader_writer_lock`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[reader\_writer\_lock::lock\-Methode](../Topic/reader_writer_lock::lock%20Method.md)|Ruft die Lese\-\/Schreibsperre als Writer ab.|  
|[reader\_writer\_lock::lock\_read\-Methode](../Topic/reader_writer_lock::lock_read%20Method.md)|Ruft die Lese\-\/Schreibsperre als Reader ab.  Wenn Writer vorhanden sind, müssen aktive Reader warten, bis die Writer fertig sind.  Der Reader registriert einfach ein Interesse an der Sperre und wartet, bis Writer sie freigeben.|  
|[reader\_writer\_lock::try\_lock\-Methode](../Topic/reader_writer_lock::try_lock%20Method.md)|Versucht, die Lese\-\/Schreibsperre als Writer ohne Blockierung zu erhalten.|  
|[reader\_writer\_lock::try\_lock\_read\-Methode](../Topic/reader_writer_lock::try_lock_read%20Method.md)|Versucht, die Lese\-\/Schreibsperre als Reader ohne Blockierung zu erhalten.|  
|[reader\_writer\_lock::unlock\-Methode](../Topic/reader_writer_lock::unlock%20Method.md)|Hebt die Reader\-\/Writer\-Sperre auf Grundlage des Elements auf, das die Sperre festgelegt hat, Reader oder Writer.|  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Synchronisierungsdatenstrukturen](../../../parallel/concrt/synchronization-data-structures.md).  
  
## Vererbungshierarchie  
 `reader_writer_lock`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [critical\_section\-Klasse](../../../parallel/concrt/reference/critical-section-class.md)