---
title: Ausnahmebehandlung in Visual C++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- try-catch keyword [C++], exception handling
ms.assetid: a6aa08de-669d-4ce8-9ec3-ec20d1354fcf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0acd5df644f097d19e5f9708f0a059a31f3e9ee9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413322"
---
# <a name="exception-handling-in-visual-c"></a>Ausnahmebehandlung in Visual C++
Eine Ausnahme ist ein Fehlerzustand, möglicherweise außerhalb der Steuerung des Programms, der verhindert, dass das Programm entlang des regulären Ausführungspfads fortgesetzt wird. Bestimmte Vorgänge, unter anderem die Objekterstellung, Dateieingabe/-ausgabe und Funktionsaufrufe, die von anderen Modulen ausgeführt werden, sind potenzielle Ausnahmequellen, selbst wenn das Programm ordnungsgemäß ausgeführt wird. Stabiler Code antizipiert und behandelt Ausnahmen.  
  
 Verwenden Sie zum Erkennen logischer Fehler innerhalb eines einzelnen Programms oder Moduls Assertionen anstelle von Ausnahmen (siehe [Using Assertions](/visualstudio/debugger/c-cpp-assertions)).  
  
 Visual C++ unterstützt drei Arten der Ausnahmebehandlung:  
  
-   [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)  
  
     Für die meisten C++-Programme sollten Sie die C++-Ausnahmebehandlung verwenden, die typsicher ist und gewährleistet, dass Objektdestruktoren während der Stapelentladung aufgerufen werden.  
  
-   [Strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md)  
  
     Windows bietet einen eigenen Ausnahmemechanismus mit dem Namen SEH. Er wird für die C++- oder MFC-Programmierung nicht empfohlen. Verwenden Sie SEH nur in MFC - fremden C-Programme.  
  
-   [MFC-Ausnahmen](../mfc/exception-handling-in-mfc.md)  
  
     Seit Version 3.0 verwendet MFC C++-Ausnahmen, unterstützt jedoch weiterhin die älteren Ausnahmebehandlungsmakros, deren Form der von C++-Ausnahmen ähnelt. Obwohl diese Makros nicht für neue Programmierungen empfohlen werden, werden sie weiterhin zu Zwecken der Abwärtskompatibilität unterstützt. In Programmen, die bereits die Makros verwenden, können Sie C++-Ausnahmen ebenfalls problemlos verwenden. Während der Vorverarbeitung führen die Makros mithilfe der Schlüsselwörter für die Ausnahmebehandlung eine Auswertung durch, die in der Visual C++-Implementierung der Programmiersprache C++ ab Visual C++-Version 2.0 definiert sind. Sie können vorhandene Ausnahmemakros beibehalten, während Sie beginnen, C++-Ausnahmen zu verwenden.  
  
 Verwenden Sie die [/EH](../build/reference/eh-exception-handling-model.md) zur Angabe der Ausnahmebehandlung für die Verwendung in einem Projekt (Compileroption) C++-Ausnahmebehandlung ist die Standardeinstellung. Kombinieren Sie die Fehlerbehandlungsmechanismen nicht miteinander. Verwenden Sie beispielsweise C++-Ausnahmen nicht zusammen mit strukturierter Ausnahmebehandlung. Mit der C++-Ausnahmebehandlung können Sie besser portierbaren Code schreiben und Ausnahmen jeglichen Typs behandeln. Weitere Informationen zu den Nachteilen der strukturierten Ausnahmebehandlung finden Sie unter [strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md). Hinweise zum Mischen von MFC-Makros und C++-Ausnahmen, finden Sie unter [Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).  
  
 Informationen zur Behandlung von Ausnahmen in CLR-Anwendungen finden Sie unter [Exception Handling](../windows/exception-handling-cpp-component-extensions.md).  
  
 Informationen zur Ausnahmebehandlung auf X64-Prozessoren finden Sie unter [Exception Handling (x64)](../build/exception-handling-x64.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)