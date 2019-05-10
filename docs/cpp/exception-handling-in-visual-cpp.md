---
title: Behandlung von Ausnahmen in MSVC
ms.date: 05/07/2019
helpviewer_keywords:
- try-catch keyword [C++], exception handling
ms.assetid: a6aa08de-669d-4ce8-9ec3-ec20d1354fcf
ms.openlocfilehash: 47443f1b7021aac7755d77f797a4f7b7410281f8
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222064"
---
# <a name="exception-handling-in-msvc"></a>Behandlung von Ausnahmen in MSVC

Eine Ausnahme ist ein Fehlerzustand, möglicherweise außerhalb der Steuerung des Programms, der verhindert, dass das Programm entlang des regulären Ausführungspfads fortgesetzt wird. Bestimmte Vorgänge, unter anderem die Objekterstellung, Dateieingabe/-ausgabe und Funktionsaufrufe, die von anderen Modulen ausgeführt werden, sind potenzielle Ausnahmequellen, selbst wenn das Programm ordnungsgemäß ausgeführt wird. Stabiler Code antizipiert und behandelt Ausnahmen.

Verwenden Sie zum Erkennen logischer Fehler innerhalb eines einzelnen Programms oder Moduls Assertionen anstelle von Ausnahmen (siehe [Using Assertions](/visualstudio/debugger/c-cpp-assertions)).

Microsoft C++ (MSVC)-Compiler unterstützt drei Arten der Ausnahmebehandlung:

- [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)

   Für die meisten C++-Programme sollten Sie die C++-Ausnahmebehandlung verwenden, die typsicher ist und gewährleistet, dass Objektdestruktoren während der Stapelentladung aufgerufen werden.

- [Strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md)

   Windows bietet einen eigenen Ausnahmemechanismus mit dem Namen SEH. Er wird für die C++- oder MFC-Programmierung nicht empfohlen. Verwenden Sie SEH nur in MFC - fremden C-Programmen.

- [MFC-Ausnahmen](../mfc/exception-handling-in-mfc.md)

   Seit Version 3.0 verwendet MFC C++-Ausnahmen, unterstützt jedoch weiterhin die älteren Ausnahmebehandlungsmakros, deren Form der von C++-Ausnahmen ähnelt. Obwohl diese Makros nicht für neue Programmierungen empfohlen werden, werden sie weiterhin zu Zwecken der Abwärtskompatibilität unterstützt. In Programmen, die bereits die Makros verwenden, können Sie C++-Ausnahmen ebenfalls problemlos verwenden. Während der vorverarbeitung ergeben die Makros, die der Webdienst zur Ausnahmebehandlung Schlüsselwörter in der MSVC-Implementierung von definiert die C++ Sprache ab Visual C++ Version 2.0. Sie können vorhandene Ausnahmemakros beibehalten, während Sie beginnen, C++-Ausnahmen zu verwenden.

Verwenden Sie die [/EH](../build/reference/eh-exception-handling-model.md) -Compileroption verwenden, um den Typ der Ausnahmebehandlung für die Verwendung in einem Projekt angeben C++-Ausnahmebehandlung ist die Standardeinstellung. Kombinieren Sie die Fehlerbehandlungsmechanismen nicht miteinander. Verwenden Sie beispielsweise C++-Ausnahmen nicht zusammen mit strukturierter Ausnahmebehandlung. Mit der C++-Ausnahmebehandlung können Sie besser portierbaren Code schreiben und Ausnahmen jeglichen Typs behandeln. Weitere Informationen zu den Nachteilen der strukturierten Ausnahmebehandlung finden Sie unter [Structured Exception Handling](../cpp/structured-exception-handling-c-cpp.md). Ratschläge zum Mischen von MFC-Makros und C++-Ausnahmen, finden Sie unter [Ausnahmen: Mithilfe von MFC-Makros und C++-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).

Weitere Informationen zur Behandlung von Ausnahmen in CLR-Anwendungen finden Sie unter [Exception Handling (C++ / CLI und C++ / CX)](../extensions/exception-handling-cpp-component-extensions.md).

Informationen über die Ausnahmebehandlung auf X64-Prozessoren finden Sie unter [X64 Ausnahmebehandlung](../build/exception-handling-x64.md).

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)