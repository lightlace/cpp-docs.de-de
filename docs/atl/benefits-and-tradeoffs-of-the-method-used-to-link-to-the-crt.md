---
title: "Benefits and Tradeoffs of the Method Used to Link to the CRT | Microsoft Docs"
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
  - "_ATL_MIN_CRT-Makro"
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Benefits and Tradeoffs of the Method Used to Link to the CRT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Projekt kann mit dem CRT dynamisch oder statisch verknüpft werden.  In der Tabelle unten wird beschreibt die Vorteile und die Kompromisse, die beim Auswählen anfallen, welche Methode.  
  
|Methode|Vorteil|Kompromiss|  
|-------------|-------------|----------------|  
|Statisch, Verknüpfen mit CRT<br /><br /> \(**Runtime Library** festgelegt **Singlethreaded**\)|Das CRT\-DLL ist nicht auf dem System erforderlich, auf dem das Bild ausgeführt wird.|Über 25K des Startcodes wird dem Bild hinzugefügt und erheblich verbessert die Größe.|  
|Dynamisch, Verknüpfen mit CRT<br /><br /> \(**Runtime Library** festgelegt **Multithreaded**\)|das Bild nicht den erfordert CRT\-Startcode, sodass es viel kleiner.|Das CRT\-DLL muss auf dem System sein, das das Bild ausführt.|  
  
 Das Thema [Verknüpfen mit CRT in dem ATL\-Projekt](../atl/linking-to-the-crt-in-your-atl-project.md) erläutert, wie die Art auswählt, in der mit CRT verknüpfen.  
  
## Siehe auch  
 [Programmieren mit ATL\- und C\-Laufzeitcode](../atl/programming-with-atl-and-c-run-time-code.md)   
 [Verhalten der Laufzeitbibliothek](../build/run-time-library-behavior.md)   
 [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)