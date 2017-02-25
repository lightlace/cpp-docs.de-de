---
title: "Schreiben eines Ausnahmehandlers | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ausnahmebehandlung, Ausnahmehandler"
  - "Strukturierte Ausnahmebehandlung, Ausnahmehandler"
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Schreiben eines Ausnahmehandlers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ausnahmehandler werden in der Regel verwendet, um auf bestimmte Fehler zu reagieren.  Sie können die Syntax für die Ausnahmebehandlung nutzen, um alle Ausnahmen außer denen zu filtern, deren Behandlung bekannt ist.  Andere Ausnahmen sollten an andere Handler übergeben werden \(möglicherweise in der Laufzeitbibliothek oder im Betriebssystem\), die geschrieben wurden, um nach diesen speziellen Ausnahmen zu suchen.  
  
 Ausnahmehandler verwenden die try\-except\-Anweisung.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [try\-except\-Anweisung](../cpp/try-except-statement.md)  
  
-   [Schreiben eines Ausnahmefilters](../cpp/writing-an-exception-filter.md)  
  
-   [Auslösen von Softwareausnahmen](../cpp/raising-software-exceptions.md)  
  
-   [Hardwareausnahmen](../cpp/hardware-exceptions.md)  
  
-   [Einschränkungen bei Ereignishandlern](../cpp/restrictions-on-exception-handlers.md)  
  
## Siehe auch  
 [Strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md)