---
title: Try-finally-Anweisung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __try
- __leave_cpp
- __leave
- __finally_cpp
- __try_cpp
- __finally
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea792bde6e50f0e4149f802a5c852192def0fefa
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943321"
---
# <a name="try-finally-statement"></a>try-finally-Anweisung
**Microsoft-spezifisch**  
  
 Die folgende Syntax beschreibt die `try-finally`-Anweisung:  
  
```cpp 
__try {  
   // guarded code  
}  
__finally {  
   // termination code  
}  
```  
  
## <a name="grammar"></a>Grammatik  
 *try-finally-statement*:  
 **__try** *Compound-Statement*  
  
 **__finally** *Compound-Statement*  
  
 Die `try-finally`-Anweisung ist eine Microsoft-Erweiterung für die Programmiersprachen C und C++, die es Zielanwendungen ermöglicht, Bereinigungscode auszuführen, wenn die Ausführung eines Codeblocks unterbrochen wird. Die Bereinigung besteht aus Aufgaben wie z. B. Neuzuweisung von Arbeitsspeicher, Schließen von Dateien und Freigeben von Dateihandles. Die `try-finally`-Anweisung ist besonders nützlich für Routinen, in denen an mehreren Stellen eine Fehlerüberprüfung durchgeführt wird, die eine vorzeitige Rückgabe von der Routine verursachen könnte.  
  
 Weitere Informationen und ein Codebeispiel finden Sie unter [versuchen-except-Anweisung](../cpp/try-except-statement.md). Weitere Informationen über die strukturierte Ausnahmebehandlung im Allgemeinen, finden Sie unter [Structured Exception Handling](../cpp/structured-exception-handling-c-cpp.md). Weitere Informationen zur Behandlung von Ausnahmen in verwalteten Anwendungen finden Sie unter [Ausnahmebehandlung unter/CLR](../windows/exception-handling-cpp-component-extensions.md).  
  
> [!NOTE]
>  Die strukturierte Ausnahmebehandlung arbeitet mit Win32 für C- und C++-Quelldateien. Sie ist jedoch nicht speziell für C++ entwickelt. Sie können sicherstellen, dass der Code portabler ist, indem Sie die C++-Ausnahmebehandlung verwenden. Die C++-Ausnahmebehandlung ist auch flexibler, da sie Ausnahmen eines beliebigen Typs behandeln kann. Für C++-Programme wird empfohlen, dass Sie den C++-Mechanismus für die Ausnahmebehandlung verwenden ([versuchen, catch- und throw-](../cpp/try-throw-and-catch-statements-cpp.md) Anweisungen).  
  
 Die verbundanweisung nach der **__try** -Klausel ist der abgesicherte Abschnitt. Die verbundanweisung nach der **__finally** -Klausel ist der Beendigungshandler. Der Handler gibt eine Reihe von Aktionen an, welche ausgeführt werden, wenn der geschützte Bereich verlassen wird, ungeachtet dessen, ob der geschützte Bereich durch eine Ausnahme verlassen wird (nicht ordnungsgemäße Beendigung) oder durch ein standardmäßiges Fortsetzen (gewöhnliche Beendigung).  
  
 Erreicht eine **__try** -Anweisung durch einfache sequenzielle Ausführung (fortfahren). Wenn Eintritte der **__try**, der zugehörige Handler aktiv. Wenn die Ablaufsteuerung das Ende des try-Blocks erreicht, wird die Ausführung wie folgt fortgesetzt:  
  
1.  Der Beendigungshandler wird aufgerufen.  
  
2.  Wenn der Beendigungshandler abgeschlossen ist, die Ausführung wird fortgesetzt, nachdem die **__finally** Anweisung. Unabhängig davon, wie der abgesicherte Abschnitt endet (z. B. über eine **"GoTo"** aus dem abgesicherten Text oder ein **zurückgeben** Anweisung), wird der Beendigungshandler ausgeführt *vor* der ablaufsteuerung wird aus dem abgesicherten Abschnitt verschoben.  
  
     Ein **__finally** Anweisung blockiert nicht die Suche nach einer entsprechenden Ausnahmehandler übergeben.  
  
 Im Falle eine Ausnahme der **__try** blockieren, muss das Betriebssystem einen Handler finden, für die Ausnahme oder die Anwendung schlägt fehl. Wenn ein Handler für alle gefunden wird, **__finally** -blocke ausgeführt werden, und die Ausführung im Handler fortgesetzt wird.  
  
 Nehmen Sie z. B. an, eine Reihe von Funktionsaufrufen verbindet Funktion A mit Funktion D, wie in der folgenden Abbildung dargestellt. Jede Funktion verfügt über einen Beendigungshandler. Wenn eine Ausnahme in Funktion D ausgelöst und in A behandelt wird, werden die Beendigungshandler in folgender Reihenfolge aufgerufen, während das System den Stapel abwickelt: D, C, B.  
  
 ![Reihenfolge der Beendigung&#45;Handler Ausführung](../cpp/media/vc38cx1.gif "vc38CX1")  
Reihenfolge für das Beenden bei Handlerausführung  
  
> [!NOTE]
>  Das Verhalten des Try-finally-unterscheidet sich von einigen anderen Sprachen, die die Verwendung von unterstützen **schließlich**, wie z. B. c#.  Ein einzelnes **__try** möglicherweise, jedoch nicht beide von **__finally** und **__except**.  Wenn beide zusammen verwendet werden sollen, muss eine äußere try-except-Anweisung die innere try-finally-Anweisung einschließen.  Es gelten andere Regeln für die Angabe, wann ein einzelner Block ausgeführt wird.  
  
## <a name="the-leave-keyword"></a>Das __leave-Schlüsselwort  
 Die **__leave-** Schlüsselwort ist nur innerhalb der geschützte Bereich der gültigen eine `try-finally` -Anweisung und deren Auswirkung besteht darin, am Ende des abgesicherten Abschnitts wechseln. Die Ausführung wird mit der ersten Anweisung im Beendigungshandler fortgesetzt.  
  
 Ein **Goto** -Anweisung kann auch aus dem abgesicherten Abschnitt Herausspringen, jedoch wird die Leistung beeinträchtigt, da es eine stapelentladung aufruft. Die **__leave-** -Anweisung ist effizienter, da sie keine stapelentladung verursacht.  
  
## <a name="abnormal-termination"></a>Nicht ordnungsgemäße Beendigung  
 Beenden einer `try-finally` Anweisung mit der [Longjmp](../c-runtime-library/reference/longjmp.md) Run-Time-Funktion wird als nicht ordnungsgemäße Beendigung angesehen. Es ist nicht zulässig, wechseln in einem **__try** -Anweisung, jedoch aus einer solchen zulässig. Alle **__finally** Anweisungen, die zwischen dem Anfangspunkt aktiv sind (normale Beendigung der **__try** Block) und das Ziel (die **__except** blockiert wird, die Ausnahme behandelt) muss ausgeführt werden. Dies wird als "lokale Entladung" bezeichnet.  
  
 Wenn eine **versuchen** Block vorzeitig aus irgendeinem Grund auch durch Herausspringen aus dem Block beendet wird, führt das System die zugeordnete **schließlich** Block als Teil der Prozess der stapelentladung. In solchen Fällen die [AbnormalTermination](http://msdn.microsoft.com/library/windows/desktop/ms679265) -Funktion zurückgegeben wird **"true"** bei Aufruf innerhalb der **schließlich** blockieren; andernfalls wird **"false"**.  
  
 Der Beendigungshandler wird nicht aufgerufen, wenn ein Prozess während der Ausführung einer `try-finally`-Anweisung abgebrochen wird.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)   
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Beendigungshandler Syntax](http://msdn.microsoft.com/library/windows/desktop/ms681393)