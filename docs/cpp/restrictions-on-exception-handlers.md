---
title: "Einschr&#228;nkungen bei Ereignishandlern | Microsoft Docs"
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
  - "Beschränkungen, Ausnahmehandler"
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Einschr&#228;nkungen bei Ereignishandlern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Haupteinschränkung bei der Verwendung von Ausnahmehandlern im Code besteht darin, dass Sie keine `goto`\-Anweisung verwenden können, um in einen `__try`\-Anweisungsblock zu wechseln.  Stattdessen müssen Sie den Anweisungsblock über die normale Ablaufsteuerung eingeben.  Sie können aus einem `__try`\-Anweisungsblock herausspringen und Ausnahmehandler nach Belieben schachteln.  
  
## Siehe auch  
 [Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)   
 [Strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md)