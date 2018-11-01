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
ms.openlocfilehash: b77a218340399578e3c9428100476787e2e60b25
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534562"
---
# <a name="structured-exception-handling-cc"></a>Structured Exception Handling (C/C++)

Strukturierte Ausnahmebehandlung (SEH) ist ein Microsoft-Erweiterung für C, um bestimmte Ausnahmecode-Situationen, z. B. Hardwareausfällen ordnungsgemäß behandelt. Obwohl Windows und Visual C++ SEH unterstützen, empfehlen wir die Verwendung von ISO-Standard-c++-Ausnahmebehandlung, da Ihr Code damit besser portierbar und flexibler ist. Dennoch, um vorhandenen Code beibehalten oder für bestimmte Arten von Programmen, Sie können es erforderlich sein, die SEH verwenden.

**Microsoft-spezifisch:**

## <a name="grammar"></a>Grammatik

*Try-except-Anweisung* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__try** *Compound-Statement* **__except** **(** *Ausdruck* **)** *Compound-Statement*

*Try-finally-Anweisung* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__try** *Compound-Statement* **__finally** *Compound-Statement*

## <a name="remarks"></a>Hinweise

Mit SEH können Sie sicherstellen, dass Ressourcen wie Speicherblöcke und Dateien ordnungsgemäß freigegeben werden, wenn die Ausführung unerwartet beendet wird. Sie können auch bestimmte Probleme behandeln, z. B. unzureichender Arbeitsspeicher – mithilfe von kurzem strukturiertem Code, der nicht abhängig ist **Goto** -Anweisungen oder ausführliche Tests von Rückgabecodes.

Die Anweisungen try-except und try-finally, auf die sich dieser Artikel bezieht, sind Microsoft-Erweiterungen der Programmiersprache C. Sie unterstützen SEH, indem es Anwendungen ermöglicht wird, die Steuerung eines Programms nach Ereignissen abzurufen, die andernfalls das Beenden der Ausführung zur Folge haben würden. Obwohl SEH mit C++-Quelldateien funktioniert, ist sie nicht ausdrücklich für C++ vorgesehen. Wenn Sie SEH in einem C++-Programm verwenden, die Sie bei der Kompilierung der [/EHa "oder" / EHsc](../build/reference/eh-exception-handling-model.md) option Destruktoren für lokale Objekte aufgerufen werden, aber weitere Ausführungsverhalten entspricht möglicherweise nicht Ihren Erwartungen. Eine Veranschaulichung finden Sie im Beispiel weiter unten in diesem Artikel. In den meisten Fällen anstelle von SEH empfiehlt es sich, dass Sie die ISO-Standard verwenden [C++-Ausnahmebehandlung](../cpp/try-throw-and-catch-statements-cpp.md), die auch Visual C++ unterstützt. Mithilfe der C++-Ausnahmebehandlung können Sie eine bessere Portierbarkeit des Codes sicherstellen, und Sie können Ausnahmen jeglichen Typs behandeln.

Wenn Sie C-Code verfügen, die SEH verwendet wird, können Sie es mit C++-Code mischen, die C++-Ausnahmebehandlung verwendet wird. Weitere Informationen finden Sie unter [strukturierter Ausnahmebehandlung in C++](../cpp/exception-handling-differences.md).

Es gibt zwei SEH-Mechanismen:

- [Ausnahmehandler](../cpp/writing-an-exception-handler.md), oder **__except** -Blöcken, die reagieren können, oder die Ausnahme zu schließen.

- [Beendigungshandler](../cpp/writing-a-termination-handler.md), oder **__finally** -Blöcken, die immer aufgerufen werden, ob eine Ausnahme davon Beendigung verursacht,.

Diese beiden Arten von Handlern unterscheiden sich zwar, sind allerdings hinsichtlich eines als "Entladen des Stapels" bekannten Prozesses eng miteinander verknüpft. Wenn eine strukturierte Ausnahme auftritt, sucht Windows die zuletzt installierte Ausnahmehandler, der gerade aktiv ist. Beim Handler kann eine von drei Möglichkeiten auftreten:

- Fehler beim Erkennen der Ausnahme und Übergabe des Steuerelements an andere Handler

- Erkennen der Ausnahme, diese aber zurückweisen

- Erkennen und behandeln der Ausnahme

Der Ausnahmehandler, der die Ausnahme erkennt, befindet sich möglicherweise nicht in der Funktion, die bei Auftreten der Ausnahme ausgeführt wurde. In einigen Fällen ist es möglicherweise in einer Funktion wesentlich höher auf dem Stapel. Die gegenwärtig ausgeführte Funktion sowie alle weiteren Funktionen im Stapelrahmen werden beendet. Der Stapel ist während dieses Vorgangs "entlädt sich", also lokale nicht statische Variablen von beendeten Funktionen aus dem Stapel gelöscht werden.

Beim Entladen des Stapels ruft das Betriebssystem alle Beendigungshandler auf, die Sie für jede Funktion geschrieben haben. Mit einem Beendigungshandler können Sie Ressourcen bereinigen, die andernfalls bei einer nicht ordnungsgemäßen Beendigung geöffnet bleiben würden. Wenn Sie einen kritischen Abschnitt eingegeben haben, können Sie es in den Beendigungshandler beenden. Wenn das Programm beendet werden soll, können Sie weitere Ordnungsaufgaben, z. B. das Schließen und Entfernen von temporären Dateien, ausführen.

## <a name="next-steps"></a>Nächste Schritte

- [Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)

- [Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)

- [Behandeln strukturierter Ausnahmen in C++](../cpp/exception-handling-differences.md)

## <a name="example"></a>Beispiel

Wie bereits erwähnt werden Destruktoren für lokale Objekte aufgerufen werden, wenn Sie verwenden Sie SEH in einem C++-Programms und kompilieren sie mit der **/EHa** oder **/EHsc** Option. Allerdings entspricht das Verhalten während der Ausführung bei zusätzlicher Verwendung von C++-Ausnahmen möglicherweise nicht Ihren Erwartungen. Dieses Beispiel zeigt diese unterschiedlichen Verhaltensweisen.

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

Bei Verwendung von **/EHsc** kompiliert diesen Code aber das Steuerelement-Makro lokalen Test `CPPEX` ist nicht definiert ist, besteht keine Ausführung von der `TestClass` Destruktor und die Ausgabe sieht wie folgt:

```Output
Triggering SEH exception
Executing SEH __except block
```

Bei Verwendung von **/EHsc** zum Kompilieren des Codes und `CPPEX` wird mittels definiert `/DCPPEX` (sodass eine C++-Ausnahme ausgelöst wird), wird die `TestClass` Destruktor ausgeführt und die Ausgabe sieht wie folgt aus:

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

Bei Verwendung von **/EHa** zum Kompilieren des Codes, der `TestClass` Destruktor ausgeführt wird, unabhängig davon, ob die Ausnahme ausgelöst wurde, mithilfe von `std::throw` oder mit SEH zum Auslösen der Ausnahme, d. h., ob `CPPEX` definiert oder nicht. Die Ausgabe sieht wie folgt aus:

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

Weitere Informationen finden Sie unter [/EH (Ausnahmebehandlungsmodell)](../build/reference/eh-exception-handling-model.md).

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[\<exception>](../standard-library/exception.md)<br/>
[Fehler- und Ausnahmebehandlung](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Strukturierte Ausnahmebehandlung (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms680657.aspx)
