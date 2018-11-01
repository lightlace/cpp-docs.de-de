---
title: try-finally-Anweisung
ms.date: 10/09/2018
f1_keywords:
- __try
- _try
- __leave_cpp
- __leave
- __finally_cpp
- __try_cpp
- __finally
- _finally
helpviewer_keywords:
- __try keyword [C++]
- __finally keyword [C++]
- __leave keyword [C++]
- try-catch keyword [C++], try-finally keyword
- try-finally keyword [C++]
- __finally keyword [C++], try-finally statement syntax
- __leave keyword [C++], try-finally statement
- structured exception handling [C++], try-finally
ms.assetid: 826e0347-ddfe-4f6e-a7bc-0398e0edc7c2
ms.openlocfilehash: 6b0c0f018d5d66ea62b29b971e5390751a69e3c4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631802"
---
# <a name="try-finally-statement"></a>try-finally-Anweisung

**Microsoft-spezifisch**

Die folgende Syntax beschreibt die **Try-finally-** Anweisung:

```cpp
__try {
   // guarded code
}
__finally {
   // termination code
}
```

## <a name="grammar"></a>Grammatik

*Try-finally-Anweisung*: **__try** *Compound-Statement*

**__finally** *Compound-Statement*

Die **Try-finally-** -Anweisung ist eine Microsoft-Erweiterung der Programmiersprachen C und C++, die es ermöglicht zielanwendungen Bereinigungscode bei der Ausführung eines Codeblocks unterbrochen wird. Die Bereinigung besteht aus Aufgaben wie z. B. Neuzuweisung von Arbeitsspeicher, Schließen von Dateien und Freigeben von Dateihandles. Die **Try-finally-** -Anweisung ist besonders nützlich für Routinen, die mehrfach haben, in dem eine Überprüfung statt, für einen Fehler, die verursachen könnten vorzeitige, von der Routine Rückgabe.

Weitere Informationen und ein Codebeispiel finden Sie unter [versuchen-except-Anweisung](../cpp/try-except-statement.md). Weitere Informationen über die strukturierte Ausnahmebehandlung im Allgemeinen, finden Sie unter [Structured Exception Handling](../cpp/structured-exception-handling-c-cpp.md). Weitere Informationen zur Behandlung von Ausnahmen in verwalteten Anwendungen finden Sie unter [Ausnahmebehandlung unter/CLR](../windows/exception-handling-cpp-component-extensions.md).

> [!NOTE]
>  Die strukturierte Ausnahmebehandlung arbeitet mit Win32 für C- und C++-Quelldateien. Sie ist jedoch nicht speziell für C++ entwickelt. Sie können sicherstellen, dass der Code portabler ist, indem Sie die C++-Ausnahmebehandlung verwenden. Die C++-Ausnahmebehandlung ist auch flexibler, da sie Ausnahmen eines beliebigen Typs behandeln kann. Für C++-Programme wird empfohlen, dass Sie den C++-Mechanismus für die Ausnahmebehandlung verwenden ([versuchen, catch- und throw-](../cpp/try-throw-and-catch-statements-cpp.md) Anweisungen).

Die verbundanweisung nach der **__try** -Klausel ist der abgesicherte Abschnitt. Die verbundanweisung nach der **__finally** -Klausel ist der Beendigungshandler. Der Handler gibt eine Reihe von Aktionen an, welche ausgeführt werden, wenn der geschützte Bereich verlassen wird, ungeachtet dessen, ob der geschützte Bereich durch eine Ausnahme verlassen wird (nicht ordnungsgemäße Beendigung) oder durch ein standardmäßiges Fortsetzen (gewöhnliche Beendigung).

Erreicht eine **__try** -Anweisung durch einfache sequenzielle Ausführung (fortfahren). Wenn Eintritte der **__try**, der zugehörige Handler aktiv. Wenn die Ablaufsteuerung das Ende des try-Blocks erreicht, wird die Ausführung wie folgt fortgesetzt:

1. Der Beendigungshandler wird aufgerufen.

1. Wenn der Beendigungshandler abgeschlossen ist, die Ausführung wird fortgesetzt, nachdem die **__finally** Anweisung. Unabhängig davon, wie der abgesicherte Abschnitt endet (z. B. über eine **"GoTo"** aus dem abgesicherten Text oder ein **zurückgeben** Anweisung), wird der Beendigungshandler ausgeführt *vor* der ablaufsteuerung wird aus dem abgesicherten Abschnitt verschoben.

   Ein **__finally** Anweisung blockiert nicht die Suche nach einer entsprechenden Ausnahmehandler übergeben.

Im Falle eine Ausnahme der **__try** blockieren, muss das Betriebssystem einen Handler finden, für die Ausnahme oder die Anwendung schlägt fehl. Wenn ein Handler für alle gefunden wird, **__finally** -blocke ausgeführt werden, und die Ausführung im Handler fortgesetzt wird.

Nehmen Sie z. B. an, eine Reihe von Funktionsaufrufen verbindet Funktion A mit Funktion D, wie in der folgenden Abbildung dargestellt. Jede Funktion verfügt über einen Beendigungshandler. Wenn eine Ausnahme in Funktion D ausgelöst und in A behandelt wird, werden die Beendigungshandler in folgender Reihenfolge aufgerufen, während das System den Stapel abwickelt: D, C, B.

![Reihenfolge der Beendigung&#45;Handler Ausführung](../cpp/media/vc38cx1.gif "vc38CX1") Reihenfolge von Handlerausführung

> [!NOTE]
>  Das Verhalten des Try-finally-unterscheidet sich von einigen anderen Sprachen, die die Verwendung von unterstützen **schließlich**, wie z. B. c#.  Ein einzelnes **__try** möglicherweise, jedoch nicht beide von **__finally** und **__except**.  Wenn beide zusammen verwendet werden sollen, muss eine äußere try-except-Anweisung die innere try-finally-Anweisung einschließen.  Es gelten andere Regeln für die Angabe, wann ein einzelner Block ausgeführt wird.

Für die Kompatibilität mit früheren Versionen **_finally**, **__identifier**, und **_leave** sind Synonyme für **__try**, **__ zum Schluss**, und **__leave-** , wenn Compileroption [/Za \(spracherweiterungen deaktivieren)](../build/reference/za-ze-disable-language-extensions.md) angegeben ist.

## <a name="the-leave-keyword"></a>Das __leave-Schlüsselwort

Die **__leave-** Schlüsselwort ist nur innerhalb der geschützte Bereich der gültigen eine **Try-finally-** -Anweisung und deren Auswirkung besteht darin, am Ende des abgesicherten Abschnitts wechseln. Die Ausführung wird mit der ersten Anweisung im Beendigungshandler fortgesetzt.

Ein **Goto** -Anweisung kann auch aus dem abgesicherten Abschnitt Herausspringen, jedoch wird die Leistung beeinträchtigt, da es eine stapelentladung aufruft. Die **__leave-** -Anweisung ist effizienter, da sie keine stapelentladung verursacht.

## <a name="abnormal-termination"></a>Nicht ordnungsgemäße Beendigung

Beenden einer **Try-finally-** Anweisung mit der [Longjmp](../c-runtime-library/reference/longjmp.md) Run-Time-Funktion wird als nicht ordnungsgemäße Beendigung angesehen. Es ist nicht zulässig, wechseln in einem **__try** -Anweisung, jedoch aus einer solchen zulässig. Alle **__finally** Anweisungen, die zwischen dem Anfangspunkt aktiv sind (normale Beendigung der **__try** Block) und das Ziel (die **__except** blockiert wird, die Ausnahme behandelt) muss ausgeführt werden. Dies wird als "lokale Entladung" bezeichnet.

Wenn eine **versuchen** Block vorzeitig aus irgendeinem Grund auch durch Herausspringen aus dem Block beendet wird, führt das System die zugeordnete **schließlich** Block als Teil der Prozess der stapelentladung. In solchen Fällen die [AbnormalTermination](/windows/desktop/Debug/abnormaltermination) -Funktion zurückgegeben wird **"true"** bei Aufruf innerhalb der **schließlich** blockieren; andernfalls wird **"false"**.

Der Beendigungshandler wird nicht aufgerufen, wenn ein Prozess, während der Ausführung abgebrochen wird einer **Try-finally-** Anweisung.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)<br/>
[Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[Beendigungshandler Syntax](/windows/desktop/Debug/termination-handler-syntax)