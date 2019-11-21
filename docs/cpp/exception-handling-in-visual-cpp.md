---
title: Exception handling in MSVC
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
# <a name="exception-handling-in-msvc"></a>Exception handling in MSVC

Eine Ausnahme ist ein Fehlerzustand, möglicherweise außerhalb der Steuerung des Programms, der verhindert, dass das Programm entlang des regulären Ausführungspfads fortgesetzt wird. Bestimmte Vorgänge, unter anderem die Objekterstellung, Dateieingabe/-ausgabe und Funktionsaufrufe, die von anderen Modulen ausgeführt werden, sind potenzielle Ausnahmequellen, selbst wenn das Programm ordnungsgemäß ausgeführt wird. Stabiler Code antizipiert und behandelt Ausnahmen. To detect logic errors, use assertions rather than exceptions (see [Using Assertions](/visualstudio/debugger/c-cpp-assertions)).

## <a name="kinds-of-exceptions"></a>Kinds of exceptions

The Microsoft C++ compiler (MSVC) supports three kinds of exception handling:

- [C++ exception handling](errors-and-exception-handling-modern-cpp.md)

   Für die meisten C++-Programme sollten Sie die C++-Ausnahmebehandlung verwenden, die typsicher ist und gewährleistet, dass Objektdestruktoren während der Stapelentladung aufgerufen werden.

- [Structured exception handling](structured-exception-handling-c-cpp.md)

   Windows bietet einen eigenen Ausnahmemechanismus mit dem Namen SEH. Er wird für die C++- oder MFC-Programmierung nicht empfohlen. Use SEH only in non-MFC C programs.

- [MFC exceptions](../mfc/exception-handling-in-mfc.md)

Use the [/EH](../build/reference/eh-exception-handling-model.md) compiler option to specify the type of exception handling to use in a project; C++ exception handling is the default. Kombinieren Sie die Fehlerbehandlungsmechanismen nicht miteinander. Verwenden Sie beispielsweise C++-Ausnahmen nicht zusammen mit strukturierter Ausnahmebehandlung. Mit der C++-Ausnahmebehandlung können Sie besser portierbaren Code schreiben und Ausnahmen jeglichen Typs behandeln. For more information about the drawbacks of structured exception handling, see [Structured Exception Handling](structured-exception-handling-c-cpp.md). For advice about mixing MFC macros and C++ exceptions, see [Exceptions: Using MFC Macros and C++ Exceptions](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).

## <a name="in-this-section"></a>In diesem Abschnitt

- [Modern C++ best practices for exceptions and error handling](errors-and-exception-handling-modern-cpp.md)

- [How to design for exception safety](how-to-design-for-exception-safety.md)

- [How to interface between exceptional and non-exceptional code](how-to-interface-between-exceptional-and-non-exceptional-code.md)

- [The try, catch, and throw Statements](try-throw-and-catch-statements-cpp.md)

- [Auswerten von Catch-Blöcken](how-catch-blocks-are-evaluated-cpp.md)

- [Exceptions and Stack Unwinding](exceptions-and-stack-unwinding-in-cpp.md)

- [Exception Specifications](exception-specifications-throw-cpp.md)

- [noexcept](noexcept-cpp.md)

- [Nicht behandelte C++-Ausnahmen](unhandled-cpp-exceptions.md)

- [Kombination von C (strukturiert)- und C++-Ausnahmen](mixing-c-structured-and-cpp-exceptions.md)

- [Structured Exception Handling (SEH) (C/C++)](structured-exception-handling-c-cpp.md)

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](cpp-language-reference.md)</br>
[GCC-Ausnahmebehandlung bei x64-Systemen](../build/exception-handling-x64.md)</br>
[Exception Handling (C++/CLI and C++/CX)](../extensions/exception-handling-cpp-component-extensions.md)
