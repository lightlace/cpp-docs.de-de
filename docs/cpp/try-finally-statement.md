---
title: try-finally-Anweisung
ms.date: 11/19/2018
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
ms.openlocfilehash: 045d2bf5617c81bcc4d7a202f36b112d5f0142a6
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246304"
---
# <a name="try-finally-statement"></a>try-finally-Anweisung

**Microsoft-spezifisch**

Die folgende Syntax beschreibt die **try-endlich-** Anweisung:

> **\_\_versuchen**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;//überwachten Code<br/>
> }<br/>
> **\_\_**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;//Beendigungs Code<br/>
> }

## <a name="grammar"></a>Grammatik

*try-finally-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **\_** \_\_zum **Schluss** eine *Verbund Anweisung \_*

Bei der **Try-End-** Anweisung handelt es sich um eine Microsoft C++ -Erweiterung für C und Sprachen, die es Zielanwendungen ermöglichen, die Ausführung von Bereinigungs Code zu gewährleisten, wenn die Ausführung eines Code Blocks unterbrochen wird. Die Bereinigung besteht aus Aufgaben wie z. B. Neuzuweisung von Arbeitsspeicher, Schließen von Dateien und Freigeben von Dateihandles. Die **try-schließlich-** Anweisung ist besonders nützlich für Routinen mit mehreren Stellen, an denen eine Überprüfung auf einen Fehler erfolgt, der eine vorzeitige Rückgabe von der Routine verursachen könnte.

Verwandte Informationen und ein Codebeispiel finden Sie unter [Try-außer-Anweisung](../cpp/try-except-statement.md). Weitere Informationen über die strukturierte Ausnahmebehandlung im Allgemeinen finden Sie unter [strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md). Weitere Informationen zur Behandlung von Ausnahmen in verwalteten Anwendungen mit C++/CLI finden Sie [unter Ausnahmebehandlung unter/CLR](../extensions/exception-handling-cpp-component-extensions.md).

> [!NOTE]
> Die strukturierte Ausnahmebehandlung arbeitet mit Win32 für C- und C++-Quelldateien. Sie ist jedoch nicht speziell für C++ entwickelt. Sie können sicherstellen, dass der Code portabler ist, indem Sie die C++-Ausnahmebehandlung verwenden. Die C++-Ausnahmebehandlung ist auch flexibler, da sie Ausnahmen eines beliebigen Typs behandeln kann. Bei C++ Programmen empfiehlt es sich, den Mechanismus für die C++ Ausnahmebehandlung zu verwenden ([try-, catch-und Throw](../cpp/try-throw-and-catch-statements-cpp.md) -Anweisungen).

Die Verbund Anweisung nach der **__try** -Klausel ist der geschützte Abschnitt. Die Verbund Anweisung nach der **__finally** -Klausel ist der Beendigungs Handler. Der Handler gibt eine Reihe von Aktionen an, welche ausgeführt werden, wenn der geschützte Bereich verlassen wird, ungeachtet dessen, ob der geschützte Bereich durch eine Ausnahme verlassen wird (nicht ordnungsgemäße Beendigung) oder durch ein standardmäßiges Fortsetzen (gewöhnliche Beendigung).

Das Steuerelement erreicht eine **__try** -Anweisung durch einfache sequenzielle Ausführung (durchlaufen). Wenn das Steuerelement in den **__try**wechselt, wird der zugehörige Handler aktiv. Wenn die Ablaufsteuerung das Ende des try-Blocks erreicht, wird die Ausführung wie folgt fortgesetzt:

1. Der Beendigungshandler wird aufgerufen.

1. Wenn der Beendigungs Handler abgeschlossen ist, wird die Ausführung nach der **__finally** -Anweisung fortgesetzt. Unabhängig davon, wie der geschützte Abschnitt endet (z. b. über ein **goto** aus dem abgesicherten Text oder über eine **Return** -Anweisung), wird der Beendigungs Handler ausgeführt, *bevor* die Ablauf Steuerung aus dem geschützten Abschnitt heraus bewegt wird.

   Eine **__finally** -Anweisung blockiert nicht das Suchen nach einem entsprechenden Ausnahmehandler.

Wenn im **__try** -Block eine Ausnahme auftritt, muss das Betriebssystem einen Handler für die Ausnahme finden, oder das Programm schlägt fehl. Wenn ein Handler gefunden wird, werden alle **__finally** Blöcke ausgeführt, und die Ausführung wird im Handler fortgesetzt.

Nehmen Sie z. B. an, eine Reihe von Funktionsaufrufen verbindet Funktion A mit Funktion D, wie in der folgenden Abbildung dargestellt. Jede Funktion verfügt über einen Beendigungshandler. Wenn eine Ausnahme in Funktion D ausgelöst und in A behandelt wird, werden die Beendigungshandler in folgender Reihenfolge aufgerufen, während das System den Stapel abwickelt: D, C, B.

![Reihenfolge der&#45;Beendigungs Handler-Ausführung](../cpp/media/vc38cx1.gif "Reihenfolge der&#45;Beendigungs Handler-Ausführung") <br/>
Reihenfolge für das Beenden bei Handlerausführung

> [!NOTE]
> Das Verhalten von try-endlich unterscheidet sich von einigen anderen Sprachen, die die Verwendung von **schließlich**unterstützen C#, z. b.  Ein einzelner **__try** kann entweder **__finally** und **__except**haben, aber nicht beides.  Wenn beide zusammen verwendet werden sollen, muss eine äußere try-except-Anweisung die innere try-finally-Anweisung einschließen.  Es gelten andere Regeln für die Angabe, wann ein einzelner Block ausgeführt wird.

Aus Kompatibilitätsgründen mit früheren Versionen sind **_try**, **_finally**und **_leave** Synonyme für **__try**, **__finally**und **__leave** , es sei denn, die Compileroption [/Za \(Deaktivieren von Spracherweiterungen)](../build/reference/za-ze-disable-language-extensions.md) ist angegeben.

## <a name="the-__leave-keyword"></a>Das __leave-Schlüsselwort

Das **__leave** -Schlüsselwort ist nur innerhalb des geschützten Abschnitts einer **Try-End-** Anweisung gültig, und seine Auswirkung besteht darin, zum Ende des geschützten Abschnitts zu springen. Die Ausführung wird mit der ersten Anweisung im Beendigungshandler fortgesetzt.

Eine **goto** -Anweisung kann auch aus dem abgesicherten Abschnitt herausspringen, beeinträchtigt jedoch die Leistung, da Sie die Stapel Auflösung aufruft. Die **__leave** -Anweisung ist effizienter, da Sie keine Stapel Auflösung verursacht.

## <a name="abnormal-termination"></a>Nicht ordnungsgemäße Beendigung

Das Beenden einer **try-endlich-** Anweisung mit der [longjmp](../c-runtime-library/reference/longjmp.md) -Lauf Zeitfunktion wird als nicht ordnungsgemäße Beendigung angesehen. Das Springen in eine **__try** -Anweisung ist unzulässig, aber es ist zulässig, von einem zu springen. Alle **__finally** -Anweisungen, die zwischen dem Punkt der Abfahrt (normale Beendigung des **__try** Blocks) und dem Ziel (dem **__except** Block, der die Ausnahme behandelt) aktiv sind, müssen ausgeführt werden. Dies wird als "lokale Entladung" bezeichnet.

Wenn ein **try** -Block aus irgendeinem Grund vorzeitig beendet wird, einschließlich eines Ausschnitts aus dem **-Block,** führt das System die zugeordnete Block Ende-Sperre im Rahmen des Entsperrens des Stapels aus. In solchen Fällen gibt die [abnormalbeendigungs](/windows/win32/Debug/abnormaltermination) Funktion " **true** " zurück, wenn Sie von **innerhalb des letzten** Blocks aufgerufen wird. Andernfalls wird **false**zurückgegeben.

Der Beendigungs Handler wird nicht aufgerufen, wenn ein Prozess in der Mitte der Ausführung einer **try-schließlich-** Anweisung abgebrochen wird.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Schreiben eines Beendigungs Handlers](../cpp/writing-a-termination-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[Beendigungs HandlerSyntax](/windows/win32/Debug/termination-handler-syntax)