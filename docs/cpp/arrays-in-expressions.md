---
title: "Arrays in Ausdr&#252;cken"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Arrays [C++], In Ausdrücken"
  - "Ausdrücke [C++], Arrays in"
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Arrays in Ausdr&#252;cken
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn ein Bezeichner von einem Arraytyp in einem anderen Ausdruck als `sizeof`, "address\-of" \(**&**\) oder in der Initialisierung eines Verweises auftritt, wird er in einen Zeiger auf das erste Arrayelement konvertiert.  Beispiel:  
  
```  
char szError1[] = "Error: Disk drive not ready.";  
char *psz = szError1;  
```  
  
 Der Zeiger `psz` zeigt auf das erste Element des Arrays `szError1`.  Beachten Sie, dass Arrays, im Gegensatz zu Zeigern, nicht veränderbare l\-Werte sind.  Daher ist die folgende Zuordnung ungültig:  
  
```  
szError1 = psz;  
```  
  
## Siehe auch  
 [Arrays](../cpp/arrays-cpp.md)