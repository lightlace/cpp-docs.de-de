---
title: "C++-Ausnahmebehandlung"
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
  - "C++-Ausnahmebehandlung"
  - "Visual C++, Ausnahmebehandlung"
ms.assetid: 65f80b44-9d0f-4d17-b910-07205a5c5c40
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# C++-Ausnahmebehandlung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Programmiersprache C\+\+ bietet integrierte Unterstützung für das Auslösen und Abfangen von Ausnahmen.  Beim Programmieren in C\+\+ sollten Sie fast immer die in diesem Abschnitt beschriebene integrierte C\+\+\-Ausnahmeunterstützung verwenden.  
  
 Aktivieren Sie die Ausnahmebehandlung für C\+\+ im Code mit [\/EHsc](../build/reference/eh-exception-handling-model.md).  
  
## In diesem Abschnitt  
 Diese Diskussion zur C\+\+\-Ausnahmebehandlung umfasst Folgendes:  
  
-   [Die try\-, catch\- und throw\-Anweisungen](../cpp/try-throw-and-catch-statements-cpp.md)  
  
-   [Wie Catch\-Blöcke ausgewertet werden](../cpp/how-catch-blocks-are-evaluated-cpp.md)  
  
-   [Ausnahmen und Stapelentladung](../cpp/exceptions-and-stack-unwinding-in-cpp.md)  
  
-   [Ausnahmespezifikationen](../cpp/exception-specifications-throw-cpp.md)  
  
-   [noexcept](../cpp/noexcept-cpp.md)  
  
-   [Nicht behandelte C\+\+\-Ausnahmen](../cpp/unhandled-cpp-exceptions.md)  
  
-   [Kombination von C \(strukturiert\)\- und C\+\+\-Ausnahmen](../cpp/mixing-c-structured-and-cpp-exceptions.md)  
  
## Unterstützung für ältere MFC\-Ausnahmen  
 Ab Version 4.0 begann MFC den C\+\+\-Mechanismus zur Ausnahmebehandlung zu verwenden.  Obwohl Sie zum Verwenden der C\+\+\-Ausnahmebehandlung im neuen Code ermutigt werden, werden die Makros aus früheren MFC\-Versionen in MFC\-Version 4.0 sowie höheren Versionen beibehalten, sodass alter Code nicht unterbrochen wird.  Die Makros und der neue Mechanismus können ebenfalls kombiniert werden.  Weitere Informationen zum Kombinieren von Makros und der C\+\+\-Ausnahmebehandlung sowie zum Konvertieren alten Codes für die Verwendung des neuen Mechanismus finden Sie in den Artikeln [Ausnahmen: Verwenden von MFC\-Makros und C\+\+\-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) und [Ausnahmen: Klicken Sie im MFC\-Ausnahmemakros konvertieren](../mfc/exceptions-converting-from-mfc-exception-macros.md).  Bei älteren MFC\-Ausnahmemakros, sofern Sie diese noch verwenden, werden C\+\+\-Ausnahmeschlüsselwörter ausgewertet.  Weitere Informationen erhalten Sie unter [Ausnahmen: Änderungen an Ausnahmemakros in Version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).  
  
## Siehe auch  
 [Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)