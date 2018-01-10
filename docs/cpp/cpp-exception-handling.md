---
title: C++-Ausnahmebehandlung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- C++ exception handling
- Visual C++, exception handling
ms.assetid: 65f80b44-9d0f-4d17-b910-07205a5c5c40
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a6cbe3489b0d45111a527102c85e6d8c207715ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="c-exception-handling"></a>C++-Ausnahmebehandlung
Die Programmiersprache C++ bietet integrierte Unterstützung für das Auslösen und Abfangen von Ausnahmen. Beim Programmieren in C++ sollten Sie fast immer die in diesem Abschnitt beschriebene integrierte C++-Ausnahmeunterstützung verwenden.  
  
 Verwenden Sie zum Aktivieren von C++-Ausnahmebehandlung im Code [/EHsc /](../build/reference/eh-exception-handling-model.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 Diese Diskussion zur C++-Ausnahmebehandlung umfasst Folgendes:  
  
-   [Die try-, catch- und throw-Anweisungen](../cpp/try-throw-and-catch-statements-cpp.md)  
  
-   [Wie Catch-Blöcke ausgewertet werden](../cpp/how-catch-blocks-are-evaluated-cpp.md)  
  
-   [Ausnahmen und Stapelentladung](../cpp/exceptions-and-stack-unwinding-in-cpp.md)  
  
-   [Ausnahmespezifikationen](../cpp/exception-specifications-throw-cpp.md)  
  
-   [noexcept](../cpp/noexcept-cpp.md)  
  
-   [Nicht behandelte C++-Ausnahmen](../cpp/unhandled-cpp-exceptions.md)  
  
-   [Kombination von C (strukturiert)- und C++-Ausnahmen](../cpp/mixing-c-structured-and-cpp-exceptions.md)  
  
## <a name="support-for-earlier-mfc-exceptions"></a>Unterstützung für ältere MFC-Ausnahmen  
 Ab Version 4.0 begann MFC den C++-Mechanismus zur Ausnahmebehandlung zu verwenden. Obwohl Sie zum Verwenden der C++-Ausnahmebehandlung im neuen Code ermutigt werden, werden die Makros aus früheren MFC-Versionen in MFC-Version 4.0 sowie höheren Versionen beibehalten, sodass alter Code nicht unterbrochen wird. Die Makros und der neue Mechanismus können ebenfalls kombiniert werden. Informationen zum Kombinieren von Makros und C++-Ausnahmebehandlung und zum Konvertieren alten Codes Verwendung des neuen Mechanismus finden Sie in den Artikeln [Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) und [Ausnahmen: Konvertieren von MFC Ausnahmemakros](../mfc/exceptions-converting-from-mfc-exception-macros.md). Bei älteren MFC-Ausnahmemakros, sofern Sie diese noch verwenden, werden C++-Ausnahmeschlüsselwörter ausgewertet. Finden Sie unter [Ausnahmen: Änderungen an Ausnahmemakros in Version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)