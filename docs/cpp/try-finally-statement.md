---
title: Try-finally-Anweisung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5bfaa7d2a2f75fa479f135a61c15f9fcf3bbf5ca
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="try-finally-statement"></a>try-finally-Anweisung
**Microsoft-spezifisch**  
  
 Die folgende Syntax beschreibt die `try-finally`-Anweisung:  
  
```  
__try {  
   // guarded code  
}  
__finally {  
   // termination code  
}  
```  
  
## <a name="grammar"></a>Grammatik  
 *try-finally-statement*:  
 `__try`*Compound-Statement*  
  
 `__finally`*Compound-Statement*  
  
 Die `try-finally`-Anweisung ist eine Microsoft-Erweiterung für die Programmiersprachen C und C++, die es Zielanwendungen ermöglicht, Bereinigungscode auszuführen, wenn die Ausführung eines Codeblocks unterbrochen wird. Die Bereinigung besteht aus Aufgaben wie z. B. Neuzuweisung von Arbeitsspeicher, Schließen von Dateien und Freigeben von Dateihandles. Die `try-finally`-Anweisung ist besonders nützlich für Routinen, in denen an mehreren Stellen eine Fehlerüberprüfung durchgeführt wird, die eine vorzeitige Rückgabe von der Routine verursachen könnte.  
  
 Verwandte Informationen und ein Codebeispiel finden Sie unter [versuchen-except-Anweisung](../cpp/try-except-statement.md). Weitere Informationen über die strukturierte Ausnahmebehandlung im Allgemeinen, finden Sie unter [strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md). Weitere Informationen zur Behandlung von Ausnahmen in verwalteten Anwendungen finden Sie unter [Ausnahmebehandlung unter/CLR](../windows/exception-handling-cpp-component-extensions.md).  
  
> [!NOTE]
>  Die strukturierte Ausnahmebehandlung arbeitet mit Win32 für C- und C++-Quelldateien. Sie ist jedoch nicht speziell für C++ entwickelt. Sie können sicherstellen, dass der Code portabler ist, indem Sie die C++-Ausnahmebehandlung verwenden. Die C++-Ausnahmebehandlung ist auch flexibler, da sie Ausnahmen eines beliebigen Typs behandeln kann. Für C++-Programme wird empfohlen, dass Sie den C++ Mechanismus zur Ausnahmebehandlung verwenden ([versuchen, catch- und throw-](../cpp/try-throw-and-catch-statements-cpp.md) Anweisungen).  
  
 Die Verbundanweisung nach der `__try`-Klausel ist der abgesicherte Abschnitt. Die Verbundanweisung nach der `__finally`-Klausel ist der Beendigungshandler. Der Handler gibt eine Reihe von Aktionen an, welche ausgeführt werden, wenn der geschützte Bereich verlassen wird, ungeachtet dessen, ob der geschützte Bereich durch eine Ausnahme verlassen wird (nicht ordnungsgemäße Beendigung) oder durch ein standardmäßiges Fortsetzen (gewöhnliche Beendigung).  
  
 Die Steuerung erreicht eine `__try`-Anweisung durch einfache sequenzielle Ausführung (Fortfahren). Wenn die Steuerung zu `__try` wechselt, wird der zugehörige Handler aktiv. Wenn die Ablaufsteuerung das Ende des try-Blocks erreicht, wird die Ausführung wie folgt fortgesetzt:  
  
1.  Der Beendigungshandler wird aufgerufen.  
  
2.  Wenn der Beendigungshandler abgeschlossen ist, wird die Ausführung nach der `__finally`-Anweisung fortgesetzt. Unabhängig davon, wie der abgesicherte Abschnitt endet (z. B. über ein `goto` aus dem abgesicherten Text oder eine `return`-Anweisung), wird der Beendigungshandler ausgeführt, `before` die Ablaufsteuerung aus dem abgesicherten Abschnitt herausbewegt wird.  
  
     Ein **__finally** Anweisung blockiert nicht die Suche nach einem passenden Ausnahmehandler.  
  
 Wenn eine Ausnahme im `__try`-Block auftritt, muss das Betriebssystem einen Handler für die Ausnahme finden, andernfalls tritt ein Fehler im Programm auf. Wenn ein Handler gefunden wird, werden sämtliche `__finally`-Blöcke ausgeführt, und die Ausführung wird im Handler fortgesetzt.  
  
 Nehmen Sie z. B. an, eine Reihe von Funktionsaufrufen verbindet Funktion A mit Funktion D, wie in der folgenden Abbildung dargestellt. Jede Funktion verfügt über einen Beendigungshandler. Wenn eine Ausnahme in Funktion D ausgelöst und in A behandelt wird, werden die Beendigungshandler in folgender Reihenfolge aufgerufen, während das System den Stapel abwickelt: D, C, B.  
  
 ![Reihenfolge der Beendigung &#45; Handler Ausführung](../cpp/media/vc38cx1.gif "vc38CX1")  
Reihenfolge für das Beenden bei Handlerausführung  
  
> [!NOTE]
>  Das Verhalten des Try-finally-unterscheidet sich von einigen anderen Sprachen, die die Verwendung von unterstützen **schließlich**, wie z. B. c#.  Ein einzelnes `__try` hat möglicherweise eines von `__finally` und `__except`, jedoch nicht beide.  Wenn beide zusammen verwendet werden sollen, muss eine äußere try-except-Anweisung die innere try-finally-Anweisung einschließen.  Es gelten andere Regeln für die Angabe, wann ein einzelner Block ausgeführt wird.  
  
## <a name="the-leave-keyword"></a>Das __leave-Schlüsselwort  
 Das `__leave`-Schlüsselwort ist nur im abgesicherten Abschnitt einer `try-finally`-Anweisung gültig. Als Resultat wird zum Ende des abgesicherten Abschnitts gesprungen. Die Ausführung wird mit der ersten Anweisung im Beendigungshandler fortgesetzt.  
  
 Eine `goto`-Anweisung kann auch aus dem abgesicherten Abschnitt herausspringen, jedoch wird die Leistung beeinträchtigt, da sie eine Stapelentladung aufruft. Die `__leave`-Anweisung ist effizienter, da sie keine Stapelentladung verursacht.  
  
## <a name="abnormal-termination"></a>Nicht ordnungsgemäße Beendigung  
 Beenden einer `try-finally` Anweisung mithilfe der [Longjmp](../c-runtime-library/reference/longjmp.md) Laufzeitfunktion wird als nicht ordnungsgemäße Beendigung angesehen. Es ist nicht zulässig, in eine `__try`-Anweisung zu springen, wohingegen das Herausspringen aus einer solchen zulässig ist. Alle `__finally`-Anweisungen, die zwischen dem Anfangspunkt (normale Beendigung des `__try`-Blocks) und dem Ziel (dem `__except`-Block, der die Ausnahme behandelt) aktiv sind, müssen ausgeführt werden. Dies wird als "lokale Entladung" bezeichnet.  
  
 Wenn eine **versuchen** Block irgendwelchen auch durch Herausspringen aus dem Block vorzeitig beendet, die das System führt die zugeordnete **schließlich** Block als Teil des Prozesses entladen des Stapels. In solchen Fällen das [AbnormalTermination](http://msdn.microsoft.com/library/windows/desktop/ms679265) Funktion gibt "true" zurück, wenn heraus aufgerufen der **schließlich** blockieren; andernfalls wird "false" zurückgegeben.  
  
 Der Beendigungshandler wird nicht aufgerufen, wenn ein Prozess während der Ausführung einer `try-finally`-Anweisung abgebrochen wird.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)   
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Beendigungshandler Syntax](http://msdn.microsoft.com/library/windows/desktop/ms681393)
