---
title: "Einschr&#228;nkungen bei Beendigungshandlern"
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
  - "Beschränkungen, Beendigungshandler"
  - "Beendigungshandler, Einschränkungen"
  - "try-catch-Schlüsselwort [C++], Beendigungshandler"
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Einschr&#228;nkungen bei Beendigungshandlern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können keine `goto`\-Anweisung verwenden, um in einen `__try`\-Anweisungsblock oder einen `__finally`\-Anweisungsblock zu wechseln.  Stattdessen müssen Sie den Anweisungsblock über die normale Ablaufsteuerung eingeben. \(Sie können jedoch aus einem `__try`\-Anweisungsblock herausspringen\). Sie können auch keinen Ausnahmehandler oder Beendigungshandler innerhalb eines `__finally`\-Blocks verschachteln.  
  
 Darüber hinaus erzeugen einige in einem Beendigungshandler zulässige Arten von Code fragliche Ergebnisse. Daher sollten Sie diese, wenn überhaupt, mit Vorsicht verwenden.  Eine ist eine `goto`\-Anweisung, die aus einem `__finally`\-Anweisungsblock herausspringt.  Wenn der Block als Teil der normalen Beendigung ausgeführt wird, passiert nichts Ungewöhnliches.  Aber wenn das System den Stapel entlädt, wird das Entladen gestoppt, und die aktuelle Funktion erhält die Steuerung,als ob keine nicht ordnungsgemäße Beendigung vorläge.  
  
 Eine `return`\-Anweisung innerhalb eines `__finally`\-Anweisungsblocks stellt ungefähr die gleiche Situation dar.  Die Steuerung wird an den unmittelbaren Aufrufer der Funktion zurückgegeben, die den Beendigungshandler enthält.  Wenn das System beim Entladen des Stapels war, wird dieser Prozess unterbrochen, und das Programm wird fortgesetzt, als wäre keine Ausnahme ausgelöst worden.  
  
## Siehe auch  
 [Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)   
 [Strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md)