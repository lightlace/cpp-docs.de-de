---
title: "Marshaling | Microsoft Docs"
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
helpviewer_keywords: 
  - "COM-Schnittstellen, Marshalling"
  - "Marshalling"
  - "Marshalling, COM-Interop"
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Marshaling
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die COM\-Technik des Marshallens ermöglicht die Schnittstellen, die von einem Objekt in einem verfügbar gemacht werden in einem anderen Prozess verwendet werden Prozess.  Im Marshalling stellt COM Code \(oder den Code bereitgestellt von der Schnittstellenimplementierung beide\), um die Parameter einer Methode in ein Format zu packen, das über Prozesse \(verschoben werden, sowie über die Verbindung zu Prozessen, die auf anderen Computern ausgeführt werden\) und diese Parameter am anderen Ende entpacken kann.  Entsprechend muss COM dieselben Schritte bei der Rückgabe aus dem Aufruf ausführen.  
  
> [!NOTE]
>  Marshalling ist in der Regel nicht erforderlich, wenn eine Schnittstelle, die von einem Objekt bereitgestellt wird, im selben Prozess wie das Objekt verwendet wird.  wird jedoch das Marshalling zwischen Threads erforderlich sein.  
  
## Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [Marshaling Details](http://msdn.microsoft.com/library/windows/desktop/ms692621)