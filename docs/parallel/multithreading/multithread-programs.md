---
title: "Multithreadprogramme"
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
  - "Multithreading [C++], Informationen über Threads"
  - "Threading [C++], Informationen über das Threading"
ms.assetid: 02443596-f7e1-48d0-b3a4-39ee0e54e444
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Multithreadprogramme
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bei einem Thread handelt es sich im Grunde um einen Ausführungspfad durch ein Programm.  Er ist außerdem die kleinste Ausführungseinheit, die von Win32 geplant wird.  Ein Thread besteht aus einem Stapel, dem Status der CPU\-Register und einem Eintrag in die Ausführungsliste des Systemschedulers.  Von jedem Thread werden sämtliche Ressourcen des jeweiligen Prozesses gemeinsam genutzt.  
  
 Ein Prozess besteht aus einem oder mehreren Threads sowie dem Code, den Daten und anderen Ressourcen eines im Speicher befindlichen Programms.  Typische Programmressourcen sind geöffnete Dateien, Semaphore und dynamisch belegter Speicher.  Ein Programm wird ausgeführt, wenn der Systemscheduler einem seiner Threads die Ausführungssteuerung überträgt.  Vom Scheduler wird festgelegt, welche Threads zu welchem Zeitpunkt ausgeführt werden sollen.  Dabei müssen eventuell Threads mit einer niedrigeren Priorität warten, bis Threads mit einer höheren Priorität ihre Tasks abgeschlossen haben.  Auf Computern mit mehreren Prozessoren kann der Scheduler einzelne Threads auf unterschiedliche Prozessoren verschieben, um eine gleichmäßige CPU\-Auslastung zu erzielen.  
  
 Die Threads in einem Prozess arbeiten unabhängig voneinander.  Solange Sie diese nicht einander "sichtbar" machen, werden Threads einzeln und ohne Kenntnis der anderen Threads in einem Prozess ausgeführt.  Threads, die allgemeine Ressourcen gemeinsam nutzen, müssen ihre Tätigkeit mithilfe von Semaphoren oder einer anderen Form der Interprozesskommunikation koordinieren.  Weitere Informationen über das Synchronisieren von Threads finden Sie unter [Schreiben von Win32\-Multithreadprogrammen](../../parallel/writing-a-multithreaded-win32-program.md).  
  
## Siehe auch  
 [Multithreading bei C und Win32](../../parallel/multithreading-with-c-and-win32.md)