---
title: "Einschr&#228;nkungen bei Ereignishandlern"
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
  - "Ausnahmebehandlung, Ausnahmehandler"
  - "Beschränkungen, Ausnahmehandler"
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Einschr&#228;nkungen bei Ereignishandlern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Haupteinschränkung bei der Verwendung von Ausnahmehandlern im Code besteht darin, dass Sie keine `goto`\-Anweisung verwenden können, um in einen `__try`\-Anweisungsblock zu wechseln.  Stattdessen müssen Sie den Anweisungsblock über die normale Ablaufsteuerung eingeben.  Sie können aus einem `__try`\-Anweisungsblock herausspringen und Ausnahmehandler nach Belieben schachteln.  
  
## Siehe auch  
 [Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)   
 [Strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md)