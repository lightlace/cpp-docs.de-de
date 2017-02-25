---
title: "C-Laufzeitfehler R6016 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6016"
ms.assetid: 7bd3f274-d9c4-4bc4-8252-80bf168c4c3a
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# C-Laufzeitfehler R6016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht genügend Speicher für Threaddaten  
  
> [!NOTE]
>  Wenn diese Fehlermeldung auftritt, wurde das genannte Programm aufgrund eines Problems mit seinem internen Speicher beendet.  Es gibt verschiedene Gründe für diesen Fehler; häufig wird er durch einen Fehler im Programm oder eine Beschädigung der vom Programm verwendeten Visual C\+\+\-Bibliotheken verursacht.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Verwenden Sie die Seite **Programme und Funktionen** in der **Systemsteuerung**, um das Programm zu reparieren oder neu zu installieren.  
> -   Verwenden Sie die Seite **Programme und Funktionen** in der **Systemsteuerung**, um alle Kopien des verteilbaren Microsoft Visual C\+\+\-Pakets zu reparieren oder neu zu installieren.  
> -   Aktivieren Sie die Option **Windows Update** in der **Systemsteuerung**, um Softwareupdates abzurufen.  
> -   Suchen Sie eine aktualisierte Version des Programms.  
  
 Dieser Fehler tritt auf, wenn dem Programm vom Betriebssystem nicht genügend Arbeitsspeicher bereitgestellt wurde, um einen [\_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md)\- oder `_beginthreadex`\-Aufruf abzuschließen, oder der lokale Threadspeicher nicht durch `_beginthread` oder `_beginthreadex` initialisiert wurde.  
  
 Beim Start eines neuen Threads muss die Bibliothek für diesen eine interne Datenbank anlegen.  Wenn der vom Betriebssystem bereitgestellte Speicher nicht zum Erweitern dieser Datenbank ausreicht, wird der Thread nicht gestartet, und der Aufrufprozess wird angehalten.  Das kann vorkommen, wenn durch den Prozess zu viele Threads erstellt wurden oder der lokale Threadspeicher ausgeschöpft ist.  
  
 Eine ausführbare Datei, die die C\-Laufzeitbibliothek \(CRT\) aufruft, sollte zur Threaderstellung `_beginthreadex` und nicht die `CreateThread`\-Funktion der Windows\-API verwenden.  `_beginthreadex` initialisiert den internen statischen Speicher, der von vielen CRT\-Funktionen im lokalen Threadspeicher verwendet wird.  Wenn Sie zur Erstellung eines Threads die `CreateThread`\-Funktion verwenden, beendet das CRT den Prozess beim Aufruf einer CRT\-Funktion, die initialisierten internen statischen Speicher benötigt, möglicherweise mit R6016.