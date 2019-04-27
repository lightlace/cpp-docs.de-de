---
title: try-except-Anweisung
ms.date: 10/09/2018
f1_keywords:
- _abnormal_termination_cpp
- _exception_code_cpp
- EXCEPTION_CONTINUE_SEARCH
- _exception_info
- __except
- _except
- EXCEPTION_CONTINUE_EXECUTION
- _exception_code
- __except_cpp
- _exception_info_cpp
- EXCEPTION_EXECUTE_HANDLER
- _abnormal_termination
helpviewer_keywords:
- __try keyword [C++]
- EXCEPTION_CONTINUE_EXECUTION macro
- EXCEPTION_CONTINUE_SEARCH macro
- EXCEPTION_EXECUTE_HANDLER macro
- GetExceptionCode function
- try-catch keyword [C++], try-except keyword [C++]
- _exception_code keyword [C++]
- try-except keyword [C++]
- _exception_info keyword [C++]
- _abnormal_termination keyword [C++]
ms.assetid: 30d60071-ea49-4bfb-a8e6-7a420de66381
ms.openlocfilehash: 400c831eec1c570f26dfc010b4e4c61e7d21b1c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266841"
---
# <a name="try-except-statement"></a>try-except-Anweisung

**Microsoft-spezifisch**

Die **versuchen Sie es – mit Ausnahme von** -Anweisung ist eine Microsoft-Erweiterung für den C und C++-Sprachen, die unterstützt strukturierte Ausnahmebehandlung.

## <a name="syntax"></a>Syntax

> **\_\_try**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;überwachten code<br/>
> }<br/>
> **\_\_except** ( *expression* )<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;Code im Ausnahmehandler<br/>
> }<br/>

## <a name="remarks"></a>Hinweise

Die **versuchen Sie es – mit Ausnahme von** -Anweisung ist eine Microsoft-Erweiterung für den C und C++-Sprachen, die es zielanwendungen erhalten ermöglicht zu steuern, wenn Ereignisse, die normalerweise zur Beendigung des Programms auftreten. Solche Ereignisse heißen *Ausnahmen*, und der Mechanismus, der Ausnahmen behandelt, heißt *strukturierte Ausnahmebehandlung* (SEH).

Weitere Informationen finden Sie unter den [Try-finally-Anweisung](../cpp/try-finally-statement.md).

Ausnahmen können entweder hardwarebasiert oder softwarebasiert sein. Auch wenn Anwendungen nicht von Hardware- oder Softwareausnahmen vollständig wiederhergestellt werden können, kann die strukturierte Ausnahmebehandlung das Anzeigen von Fehlerinformationen ermöglichen und den internen Zustand der Anwendung abfangen, um das Problem zu diagnostizieren. Dies ist besonders hilfreich bei zeitweilig auftretenden Problemen, die nicht leicht reproduziert werden können.

> [!NOTE]
> Die strukturierte Ausnahmebehandlung arbeitet mit Win32 für C- und C++-Quelldateien. Sie ist jedoch nicht speziell für C++ entwickelt. Sie können sicherstellen, dass der Code portabler ist, indem Sie die C++-Ausnahmebehandlung verwenden. Die C++-Ausnahmebehandlung ist auch flexibler, da sie Ausnahmen eines beliebigen Typs behandeln kann. Für C++-Programme wird empfohlen, dass Sie den C++-Mechanismus für die Ausnahmebehandlung verwenden ([versuchen, catch- und throw-](../cpp/try-throw-and-catch-statements-cpp.md) Anweisungen).

Die verbundanweisung nach der **__try** -Klausel ist der Text bzw. der geschützte Bereich. Die verbundanweisung nach der **__except** -Klausel ist der Ausnahmehandler. Der Handler gibt eine Reihe von Aktionen an, die abgerufen werden, wenn eine Ausnahme während der Ausführung des Texts des geschützten Bereichs ausgelöst wird. Die Ausführung erfolgt folgendermaßen:

1. Der geschützte Bereich wird ausgeführt.

1. Wenn während der Ausführung des abgesicherten Abschnitts keine Ausnahme auftritt, die Ausführung wird fortgesetzt, bei der Anweisung nach der **__except** Klausel.

1. Wenn eine Ausnahme tritt auf, während der Ausführung des abgesicherten Abschnitts oder in einer Routine der geschützte Abschnitt aufruft, die **__except** *Ausdruck* (bezeichnet das *Filter* Ausdruck) wird ausgewertet, und der Wert bestimmt, wie die Ausnahme behandelt wird. Es gibt drei mögliche Werte:

   - EXCEPTION_CONTINUE_EXECUTION (– 1)-Ausnahme wurde verworfen. Fortsetzen der Ausführung an der Stelle, an der die Ausnahme aufgetreten ist.

   - EXCEPTION_CONTINUE_SEARCH (0)-Ausnahme wurde nicht erkannt. Fahren Sie fort, im Stapel nach einem Handler zu suchen, zuerst nach enthaltenen **try-except**-Anweisungen, dann nach Handlern mit der nächst höheren Priorität.

   - Exception_execute_handler (1)-Ausnahme wurde erkannt. Übertragen Sie die Steuerung an den Ausnahmehandler durch Ausführen der **__except** verbundanweisung aus, und klicken Sie dann fortsetzen der Ausführung nach der **__except** Block.

Da die **__except** -Ausdruck als C-Ausdruck ausgewertet wird, wird er auf einen einzelnen Wert, der bedingten Ausdrucksoperator oder Komma-Operators beschränkt. Wenn eine erweiterte Verarbeitung erforderlich ist, kann der Ausdruck eine Routine aufrufen, die einen der drei Werte zurückgibt, die oben aufgelistet sind.

Jede Anwendung kann einen eigenen Ausnahmehandler haben.

Es ist nicht zulässig, springen Sie in einem **__try** -Anweisung, aber aus einer solchen gültig. Der Ausnahmehandler wird nicht aufgerufen, wenn ein Prozess, während der Ausführung beendet wird eine **Testen – mit Ausnahme von** Anweisung.

Für die Kompatibilität mit früheren Versionen **_finally**, **_except**, und **_leave** sind Synonyme für **__try**, **__except** , und **__leave-** , wenn Compileroption [/Za \(spracherweiterungen deaktivieren)](../build/reference/za-ze-disable-language-extensions.md) angegeben ist.

### <a name="the-leave-keyword"></a>Das __leave-Schlüsselwort

Die **__leave-** Schlüsselwort ist nur innerhalb der geschützte Bereich der gültigen eine **versuchen-außer** -Anweisung und deren Auswirkung besteht darin, am Ende des abgesicherten Abschnitts wechseln. Die Ausführung wird mit der ersten Anweisung nach dem Ausnahmehandler fortgesetzt.

Ein **Goto** -Anweisung kann auch aus dem abgesicherten Abschnitt Herausspringen, und die Leistung wird nicht beeinträchtigt, wie in einem **Try-finally-** Anweisung, da keine stapelentladung. Wir empfehlen jedoch die Verwendung der **__leave-** Schlüsselwort anstelle eines **Goto** Anweisung, da weniger einen Programmierfehler kommt wahrscheinlich, wenn der geschützte Bereich Groß oder komplex ist.

### <a name="structured-exception-handling-intrinsic-functions"></a>Intrinsische Funktionen der strukturierten Ausnahmebehandlung

Strukturierte Ausnahmebehandlung bietet zwei intrinsische Funktionen, die zur Verwendung mit der **versuchen-mit Ausnahme von** Anweisung: `GetExceptionCode` und `GetExceptionInformation`.

`GetExceptionCode` Gibt den Code (32-Bit-Ganzzahl) der Ausnahme zurück.

Die intrinsische Funktion `GetExceptionInformation` gibt einen Zeiger auf eine Struktur, die zusätzliche Informationen zur Ausnahme enthält. Mit diesem Zeiger können Sie auf den Computerzustand zugreifen, der zum Zeitpunkt einer Hardwareausnahme vorhanden war. Die Struktur lautet wie folgt:

```cpp
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS;
```

Die Zeigertypen `PEXCEPTION_RECORD` und `PCONTEXT` werden in der Includedatei definiert \<"Winnt.h" >, und `_EXCEPTION_RECORD` und `_CONTEXT` werden in der Includedatei definiert \<excpt.h >

Sie können `GetExceptionCode` innerhalb des ausnahmehandlers. Sie können jedoch `GetExceptionInformation` nur innerhalb des ausnahmefilterausdrucks. Die Information, auf die verwiesen wird, befindet sich im Allgemeinen auf dem Stapel und ist nicht mehr verfügbar, wenn die Steuerung an den Ausnahmehandler übertragen wird.

Die intrinsische Funktion `AbnormalTermination` ist innerhalb eines beendigungshandlers zur Verfügung. Es gibt 0 zurück, wenn der Hauptteil der **Try-finally-** -Anweisung nacheinander beendet wird. In allen anderen Fällen wird 1 zurückgegeben.

excpt.h definiert mehrere alternativen Namen für diese systeminternen Funktionen:

`GetExceptionCode` ist gleich `_exception_code`

`GetExceptionInformation` ist gleich `_exception_info`

`AbnormalTermination` ist gleich `_abnormal_termination`

## <a name="example"></a>Beispiel

```cpp
// exceptions_try_except_Statement.cpp
// Example of try-except and try-finally statements
#include <stdio.h>
#include <windows.h> // for EXCEPTION_ACCESS_VIOLATION
#include <excpt.h>

int filter(unsigned int code, struct _EXCEPTION_POINTERS *ep)
{
    puts("in filter.");
    if (code == EXCEPTION_ACCESS_VIOLATION)
    {
        puts("caught AV as expected.");
        return EXCEPTION_EXECUTE_HANDLER;
    }
    else
    {
        puts("didn't catch AV, unexpected.");
        return EXCEPTION_CONTINUE_SEARCH;
    };
}

int main()
{
    int* p = 0x00000000;   // pointer to NULL
    puts("hello");
    __try
    {
        puts("in try");
        __try
        {
            puts("in try");
            *p = 13;    // causes an access violation exception;
        }
        __finally
        {
            puts("in finally. termination: ");
            puts(AbnormalTermination() ? "\tabnormal" : "\tnormal");
        }
    }
    __except(filter(GetExceptionCode(), GetExceptionInformation()))
    {
        puts("in except");
    }
    puts("world");
}
```

### <a name="output"></a>Output

```Output
hello
in try
in try
in filter.
caught AV as expected.
in finally. termination:
        abnormal
in except
world
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)<br/>
[Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)
