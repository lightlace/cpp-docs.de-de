---
title: "lock-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::lock"
  - "msclr.lock"
  - "lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock-Klasse"
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# lock-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Klasse automatisiert das Erstellen einer Sperre zum Synchronisieren des Zugriffs auf ein Objekt von mehreren Threads.  Wenn Sie ihn erstellt werden, wenn die Sperre abruft und zerstört, wird die Sperre.  
  
## Syntax  
  
```  
ref class lock;  
```  
  
## Hinweise  
 `lock` ist nur für CLR\-Objekte verfügbar und kann in nur CLR\-Code verwendet werden.  
  
 Intern verwendet die Sperrenklasse <xref:System.Threading.Monitor>, um Vollzugriff zu synchronisieren.  Siehe dieses Thema Ausführlichere Informationen über Synchronisierung.  
  
## Anforderungen  
 **Headerdatei** \<msclr\\lock.h\>  
  
 **Namespace** msclr  
  
## Siehe auch  
 [lock](../dotnet/lock.md)   
 [lock\-Member](../dotnet/lock-members.md)