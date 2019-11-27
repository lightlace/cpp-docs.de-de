---
title: Ausnahmebehandlung in MSVC
ms.date: 11/19/2019
helpviewer_keywords:
- try-catch keyword [C++], exception handling
ms.assetid: a6aa08de-669d-4ce8-9ec3-ec20d1354fcf
ms.openlocfilehash: 6cf71d6e6d0519951a084ebead65003bd363395f
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246590"
---
# <a name="exception-handling-in-msvc"></a>Ausnahmebehandlung in MSVC

Eine Ausnahme ist ein Fehlerzustand, möglicherweise außerhalb der Steuerung des Programms, der verhindert, dass das Programm entlang des regulären Ausführungspfads fortgesetzt wird. Bestimmte Vorgänge, unter anderem die Objekterstellung, Dateieingabe/-ausgabe und Funktionsaufrufe, die von anderen Modulen ausgeführt werden, sind potenzielle Ausnahmequellen, selbst wenn das Programm ordnungsgemäß ausgeführt wird. Stabiler Code antizipiert und behandelt Ausnahmen. Verwenden Sie zum Erkennen von Logik Fehlern Assertionen anstelle von Ausnahmen (siehe [using](/visualstudio/debugger/c-cpp-assertions)Assertionen).

## <a name="kinds-of-exceptions"></a>Arten von Ausnahmen

Der Microsoft C++ -Compiler (MSVC) unterstützt drei Arten der Ausnahmebehandlung:

- [C++Ausnahmebehandlung](errors-and-exception-handling-modern-cpp.md)

   Für die meisten C++-Programme sollten Sie die C++-Ausnahmebehandlung verwenden, die typsicher ist und gewährleistet, dass Objektdestruktoren während der Stapelentladung aufgerufen werden.

- [Strukturierte Ausnahmebehandlung](structured-exception-handling-c-cpp.md)

   Windows bietet einen eigenen Ausnahmemechanismus mit dem Namen SEH. Er wird für die C++- oder MFC-Programmierung nicht empfohlen. Verwenden Sie SEH nur in nicht-MFC-C-Programmen.

- [MFC-Ausnahmen](../mfc/exception-handling-in-mfc.md)

Verwenden Sie die [/eh](../build/reference/eh-exception-handling-model.md) -Compileroption, um den Typ der Ausnahmebehandlung anzugeben, der in einem Projekt verwendet werden soll. C++ die Ausnahmebehandlung ist die Standardeinstellung. Kombinieren Sie die Fehlerbehandlungsmechanismen nicht miteinander. Verwenden Sie beispielsweise C++-Ausnahmen nicht zusammen mit strukturierter Ausnahmebehandlung. Mit der C++-Ausnahmebehandlung können Sie besser portierbaren Code schreiben und Ausnahmen jeglichen Typs behandeln. Weitere Informationen zu den Nachteilen der strukturierten Ausnahmebehandlung finden Sie unter [strukturierte Ausnahmebehandlung](structured-exception-handling-c-cpp.md). Hinweise zum Mischen von MFC-Makros C++ und-Ausnahmen finden [Sie unter Ausnahmen: Verwenden von C++ MFC-Makros und-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).

## <a name="in-this-section"></a>In diesem Abschnitt

- [Moderne C++ bewährte Methoden für Ausnahmen und Fehlerbehandlung](errors-and-exception-handling-modern-cpp.md)

- [Entwerfen von Ausnahme Sicherheit](how-to-design-for-exception-safety.md)

- [Gewusst wie: verbinden zwischen Ausnahme-und nicht-Ausnahme Code](how-to-interface-between-exceptional-and-non-exceptional-code.md)

- [Die try-, catch-und Throw-Anweisungen](try-throw-and-catch-statements-cpp.md)

- [Auswerten von Catch-Blöcken](how-catch-blocks-are-evaluated-cpp.md)

- [Ausnahmen und Stapel Entwicklung](exceptions-and-stack-unwinding-in-cpp.md)

- [Ausnahme Spezifikationen](exception-specifications-throw-cpp.md)

- [noexcept](noexcept-cpp.md)

- [Nicht behandelte C++-Ausnahmen](unhandled-cpp-exceptions.md)

- [Kombination von C (strukturiert)- und C++-Ausnahmen](mixing-c-structured-and-cpp-exceptions.md)

- [Strukturierte Ausnahmebehandlung (SEH) (C/C++)](structured-exception-handling-c-cpp.md)

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](cpp-language-reference.md)</br>
[GCC-Ausnahmebehandlung bei x64-Systemen](../build/exception-handling-x64.md)</br>
[Ausnahmebehandlung (C++/CLI und C++/CX)](../extensions/exception-handling-cpp-component-extensions.md)
