---
title: "Fehlerbehandlung und Benachrichtigung"
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
  - "Fehlerbehandlung, Und Benachrichtigung"
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Fehlerbehandlung und Benachrichtigung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Informationen über die Fehlerbehandlung und \-benachrichtigung finden Sie unter [Die Hilfsfunktion](assetId:///6279c12c-d908-4967-b0b3-cabfc3e91d3d).  
  
 Weitere Informationen zu Hookfunktionen finden Sie unter [Struktur\- und Konstantendefinitionen](../../build/reference/structure-and-constant-definitions.md).  
  
 Wenn verzögert geladene DLLs vom Programm verwendet werden, müssen Fehler robust behandelt werden, da während der Programmausführung auftretende Fehler unbehandelte Ausnahmen verursachen können.  Die Fehlerbehandlung besteht aus zwei Teilen:  
  
 Wiederherstellung über einen Hook.  
 Wenn vom Code eine Wiederherstellung durchgeführt oder im Fehlerfall eine alternative Bibliothek und\/oder Routine bereitgestellt werden muss, kann der Hilfsfunktion ein Hook zur Verfügung gestellt werden, der unterstützen oder die Situation lösen kann.  Von der Hookroutine muss entweder ein geeigneter Wert \(einen `HINSTANCE`\-Wert oder einen **FARPROC**\-Wert\) zurückgegeben werden, sodass die Verarbeitung fortgesetzt werden kann, oder der Rückgabewert muss 0 sein, um anzuzeigen, dass eine Ausnahme ausgelöst werden soll.  Die Hookroutine kann aber auch selbst eine Ausnahme auslösen oder den Hook mithilfe von `longjmp` verlassen.  Es gibt Benachrichtigungshooks und Fehlerhooks.  
  
 Meldung über eine Ausnahme.  
 Wenn die Prozedur als Fehlerbehandlung lediglich abgebrochen werden muss, ist kein Hook erforderlich, solange die Ausnahme vom Benutzercode behandelt werden kann.  
  
 In den folgenden Themen werden Fehlerbehandlung und \-benachrichtigung genauer beschrieben:  
  
-   [Benachrichtigungshooks](../../build/reference/notification-hooks.md)  
  
-   [Fehlerhooks](../../build/reference/failure-hooks.md)  
  
-   [Ausnahmen](../../build/reference/exceptions-c-cpp.md)  
  
## Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)