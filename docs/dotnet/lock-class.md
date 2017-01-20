---
title: "lock-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
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
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
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