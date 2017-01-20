---
title: "Threadsicherheit in der C++-Standardbibliothek"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++-Standardbibliothek, Threadsicherheit"
  - "Threadsicherheit"
  - "Threadsicherheit, Standardvorlagenbibliothek"
ms.assetid: 9351c8fb-4539-4728-b0e9-226e2ac4284b
caps.latest.revision: 21
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# Threadsicherheit in der C++-Standardbibliothek
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Threadsicherheitsregeln gelten für alle Klassen in der C\+\+\-Standardbibliothek – dazu gehört wie unten beschrieben auch `shared_ptr`.  In manchen Fällen stehen noch stärkere Garantien zur Verfügung – z. B. die unten beschriebenen iostream\-Standardobjekte und Typen, die speziell für das Multithreading entwickelt wurden \(wie diejenigen in [\<atomic\>](../standard-library/atomic.md)\).  
  
 Ein Objekt ist threadsicher zum Lesen aus mehreren Threads.  Ein bestimmtes Objekt A kann z. B. sicher gleichzeitig aus Thread 1 und Thread 2 ausgelesen werden.  
  
 Wenn durch einen Thread in ein Objekt geschrieben wird, müssen alle Lese\- und Schreibvorgänge im Zusammenhang mit diesem Objekt in diesem oder anderen Threads geschützt werden.  Wenn z. B. Thread 1 in Objekt A schreibt, muss verhindert werden, dass Thread 2 Objekt A ausliest oder in Objekt A schreibt.  
  
 Es ist sicher, aus einer Instanz eines Typs zu lesen oder in diese zu schreiben, wenn ein anderer Thread aus einer anderen Instanz desselben Typs liest oder in diese schreibt.  Im Fall zweier Objekte desselben Typs namens Objekt A und Objekt B ist es sicher, wenn Thread 1 in Objekt A schreibt und in Thread 2 aus Objekt B gelesen wird.  
  
## shared\_ptr  
 Mehrere Threads können gleichzeitig verschiedene [shared\_ptr](../standard-library/shared-ptr-class.md)\-Objekte auslesen und in diese schreiben, auch wenn die Objekte Kopien sind, die denselben Besitzer haben.  
  
## iostream  
 Die iostream\-Standardobjekte `cin`, `cout`, `cerr`, `clog`, `wcin`, `wcout`, `wcerr` und `wclog` folgen denselben Regeln wie die anderen Klassen, mit der Ausnahme, dass es sicher ist, wenn in mehreren Threads in ein Objekt geschrieben wird.  Thread 1 kann z. B zur selben Zeit in [cout](../Topic/cout.md) schreiben wie Thread 2.  Dies kann allerdings zu einer Vermischung der Ausgaben zweier Threads führen.  
  
> [!NOTE]
>  Das Lesen aus einem Streampuffer wird nicht als Lesevorgang betrachtet.  Stattdessen wird es als Schreibvorgang angesehen, da der Zustand der Klasse geändert wird.  
  
## Siehe auch  
 [STL\-Übersicht](../standard-library/cpp-standard-library-overview.md)