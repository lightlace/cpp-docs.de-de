---
title: "Kompilieren und Binden von Multithreadprogrammen"
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
  - "Kompilieren von Multithreadprogrammen"
  - "Kompilieren von Quellcode [C++], Multithreadprogramme"
  - "Verknüpfen [C++], Multithreadprogramme"
  - "Multithreading [C++], Kompilierte Programme"
  - "Multithreading [C++], Verknüpfen von Programmen"
  - "Threading [C++], Kompilierte Programme"
  - "Threading [C++], Verknüpfen von Programmen"
ms.assetid: 27589afc-daf2-4f26-b868-a99de5c9dfec
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Kompilieren und Binden von Multithreadprogrammen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Einführung in das Programm Bounce.c finden Sie unter [Beispiel für ein C\-Multithreadprogramm](../parallel/sample-multithread-c-program.md).  
  
 Programme werden standardmäßig mit Multithreading kompiliert.  
  
#### So kompilieren und binden Sie das Multithreadprogramm Bounce.c innerhalb der Entwicklungsumgebung  
  
1.  Klicken Sie im Menü **Datei** erst auf **Neu** und dann auf **Projekt**.  
  
2.  Klicken Sie im Bereich **Projekttypen** auf **Win32**.  
  
3.  Klicken Sie im Bereich **Vorlagen** auf **Win32\-Konsolenanwendung**, und benennen Sie das Projekt.  
  
4.  Fügen Sie dem Projekt die Datei mit dem C\-Quellcode hinzu.  
  
5.  Erstellen Sie im Menü **Erstellen** das Projekt, indem Sie auf den Befehl **Erstellen** klicken.  
  
#### So kompilieren und binden Sie das Multithreadprogramm Bounce.c von der Befehlszeile  
  
1.  Kompilieren und binden Sie das Programm:  
  
    ```  
    CL BOUNCE.C  
    ```  
  
## Siehe auch  
 [Multithreading bei C und Win32](../parallel/multithreading-with-c-and-win32.md)