---
title: Structured Exception Handling (C/C++)
ms.date: 08/14/2018
helpviewer_keywords:
- termination handlers [C++], handling exceptions in C++
- structured exception handling [C++]
- try-catch keyword [C++], exception handlers
- C++ exception handling, termination handlers
- try-catch keyword [C++], termination handlers
- C++ exception handling, exception handlers
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
ms.openlocfilehash: 942a7e48e4315454476bfe93c68169f461b006b2
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245133"
---
# <a name="structured-exception-handling-cc"></a>Structured Exception Handling (C/C++)

Structured exception handling (SEH) is a Microsoft extension to C to handle certain exceptional code situations, such as hardware faults, gracefully. Although Windows and Microsoft C++ support SEH, we recommend that you use ISO-standard C++ exception handling because it makes your code more portable and flexible. Nevertheless, to maintain existing code or for particular kinds of programs, you still might have to use SEH.

**Microsoft specific:**

## <a name="grammar"></a>Grammatik

*try-except-statement* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__try** *compound-statement* **__except** **(** *expression* **)** *compound-statement*

*try-finally-statement* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__try** *compound-statement* **__finally** *compound-statement*

## <a name="remarks"></a>Hinweise

With SEH, you can ensure that resources such as memory blocks and files are released correctly if execution unexpectedly terminates. You can also handle specific problems—for example, insufficient memory—by using concise structured code that does not rely on **goto** statements or elaborate testing of return codes.

Die Anweisungen try-except und try-finally, auf die sich dieser Artikel bezieht, sind Microsoft-Erweiterungen der Programmiersprache C. Sie unterstützen SEH, indem es Anwendungen ermöglicht wird, die Steuerung eines Programms nach Ereignissen abzurufen, die andernfalls das Beenden der Ausführung zur Folge haben würden. Obwohl SEH mit C++-Quelldateien funktioniert, ist sie nicht ausdrücklich für C++ vorgesehen. If you use SEH in a C++ program that you compile by using the [/EHa or /EHsc](../build/reference/eh-exception-handling-model.md) option, destructors for local objects are called but other execution behavior might not be what you expect. For an illustration, see the example later in this article. In most cases, instead of SEH we recommend that you use ISO-standard [C++ exception handling](../cpp/try-throw-and-catch-statements-cpp.md), which the Microsoft C++ compiler also supports. Mithilfe der C++-Ausnahmebehandlung können Sie eine bessere Portierbarkeit des Codes sicherstellen, und Sie können Ausnahmen jeglichen Typs behandeln.

If you have C code that uses SEH, you can mix it with C++ code that uses C++ exception handling. For information, see [Handle structured exceptions in C++](../cpp/exception-handling-differences.md).

Es gibt zwei SEH-Mechanismen:

- [Exception handlers](../cpp/writing-an-exception-handler.md), or **__except** blocks, which can respond to or dismiss the exception.

- [Termination handlers](../cpp/writing-a-termination-handler.md), or **__finally** blocks, which are always called, whether an exception causes termination or not.

Diese beiden Arten von Handlern unterscheiden sich zwar, sind allerdings hinsichtlich eines als "Entladen des Stapels" bekannten Prozesses eng miteinander verknüpft. When a structured exception occurs, Windows looks for the most recently installed exception handler that is currently active. Beim Handler kann eine von drei Möglichkeiten auftreten:

- Fehler beim Erkennen der Ausnahme und Übergabe des Steuerelements an andere Handler

- Erkennen der Ausnahme, diese aber zurückweisen

- Erkennen und behandeln der Ausnahme

Der Ausnahmehandler, der die Ausnahme erkennt, befindet sich möglicherweise nicht in der Funktion, die bei Auftreten der Ausnahme ausgeführt wurde. In einigen Fällen ist es möglicherweise in einer Funktion wesentlich höher auf dem Stapel. Die gegenwärtig ausgeführte Funktion sowie alle weiteren Funktionen im Stapelrahmen werden beendet. During this process, the stack is "unwound;" that is, local non-static variables of terminated functions are cleared from the stack.

Beim Entladen des Stapels ruft das Betriebssystem alle Beendigungshandler auf, die Sie für jede Funktion geschrieben haben. Mit einem Beendigungshandler können Sie Ressourcen bereinigen, die andernfalls bei einer nicht ordnungsgemäßen Beendigung geöffnet bleiben würden. If you've entered a critical section, you can exit it in the termination handler. Wenn das Programm beendet werden soll, können Sie weitere Ordnungsaufgaben, z. B. das Schließen und Entfernen von temporären Dateien, ausführen.

## <a name="next-steps"></a>Nächste Schritte

- [Writing an exception handler](../cpp/writing-an-exception-handler.md)

- [Writing a termination handler](../cpp/writing-a-termination-handler.md)

- [Behandeln strukturierter Ausnahmen in C++](../cpp/exception-handling-differences.md)

## <a name="example"></a>Beispiel

As stated earlier, destructors for local objects are called if you use SEH in a C++ program and compile it by using the **/EHa** or **/EHsc** option. Allerdings entspricht das Verhalten während der Ausführung bei zusätzlicher Verwendung von C++-Ausnahmen möglicherweise nicht Ihren Erwartungen. This example demonstrates these behavioral differences.

```cpp
#include <stdio.h>
#include <Windows.h>
#include <exception>

class TestClass
{
public:
    ~TestClass()
    {
        printf("Destroying TestClass!\r\n");
    }
};

__declspec(noinline) void TestCPPEX()
{
#ifdef CPPEX
    printf("Throwing C++ exception\r\n");
    throw std::exception("");
#else
    printf("Triggering SEH exception\r\n");
    volatile int *pInt = 0x00000000;
    *pInt = 20;
#endif
}

__declspec(noinline) void TestExceptions()
{
    TestClass d;
    TestCPPEX();
}

int main()
{
    __try
    {
        TestExceptions();
    }
    __except(EXCEPTION_EXECUTE_HANDLER)
    {
        printf("Executing SEH __except block\r\n");
    }

    return 0;
}
```

If you use **/EHsc** to compile this code but the local test control macro `CPPEX` is undefined, there is no execution of the `TestClass` destructor and the output looks like this:

```Output
Triggering SEH exception
Executing SEH __except block
```

If you use **/EHsc** to compile the code and `CPPEX` is defined by using `/DCPPEX` (so that a C++ exception is thrown), the `TestClass` destructor executes and the output looks like this:

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

If you use **/EHa** to compile the code, the `TestClass` destructor executes regardless of whether the exception was thrown by using `std::throw` or by using SEH to trigger the exception, that is, whether `CPPEX` defined or not. Die Ausgabe sieht wie folgt aus:

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

Weitere Informationen finden Sie unter [/EH (Ausnahmebehandlungsmodell)](../build/reference/eh-exception-handling-model.md).

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)<br/>
[Stichwörter](../cpp/keywords-cpp.md)<br/>
[\<exception>](../standard-library/exception.md)<br/>
[Errors and Exception Handling](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Structured Exception Handling (Windows)](/windows/win32/debug/structured-exception-handling)
