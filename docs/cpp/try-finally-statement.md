---
title: "try-finally-Anweisung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__try"
  - "__leave_cpp"
  - "__leave"
  - "__finally_cpp"
  - "__try_cpp"
  - "__finally"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__finally-Schlüsselwort [C++]"
  - "__finally-Schlüsselwort [C++], try-finally-Anweisung (Syntax)"
  - "__leave-Schlüsselwort [C++]"
  - "__leave-Schlüsselwort [C++], try-finally-Anweisung"
  - "__try-Schlüsselwort [C++]"
  - "Strukturierte Ausnahmebehandlung, try-finally"
  - "try-catch-Schlüsselwort [C++], try-finally-Schlüsselwort"
  - "try-finally-Schlüsselwort [C++]"
ms.assetid: 826e0347-ddfe-4f6e-a7bc-0398e0edc7c2
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# try-finally-Anweisung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Die folgende Syntax beschreibt die `try-finally`\-Anweisung:  
  
```  
__try {  
   // guarded code  
}  
__finally {  
   // termination code  
}  
```  
  
## Grammatik  
 *try\-finally\-statement*:  
 `__try` *compound\-statement*  
  
 `__finally` *compound\-statement*  
  
 Die `try-finally`\-Anweisung ist eine Microsoft\-Erweiterung für die Programmiersprachen C und C\+\+, die es Zielanwendungen ermöglicht, Bereinigungscode auszuführen, wenn die Ausführung eines Codeblocks unterbrochen wird.  Die Bereinigung besteht aus Aufgaben wie z. B. Neuzuweisung von Arbeitsspeicher, Schließen von Dateien und Freigeben von Dateihandles.  Die `try-finally`\-Anweisung ist besonders nützlich für Routinen, in denen an mehreren Stellen eine Fehlerüberprüfung durchgeführt wird, die eine vorzeitige Rückgabe von der Routine verursachen könnte.  
  
 Weitere Informationen und ein Codebeispiel finden Sie unter [try\-except\-Anweisung](../cpp/try-except-statement.md).  Weitere Informationen über die strukturierte Ausnahmebehandlung im Allgemeinen finden Sie unter [Strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md).  Weitere Informationen über die Behandlung von Ausnahmen in verwalteten Anwendungen finden Sie unter [Ausnahmebehandlung unter "\/clr"](../windows/exception-handling-cpp-component-extensions.md).  
  
> [!NOTE]
>  Die strukturierte Ausnahmebehandlung arbeitet mit Win32 für C\- und C\+\+\-Quelldateien.  Sie ist jedoch nicht speziell für C\+\+ entwickelt.  Sie können sicherstellen, dass der Code portabler ist, indem Sie die C\+\+\-Ausnahmebehandlung verwenden.  Die C\+\+\-Ausnahmebehandlung ist auch flexibler, da sie Ausnahmen eines beliebigen Typs behandeln kann.  Für C\+\+\-Programme wird empfohlen, dass Sie den C\+\+\-Mechanismus zur Ausnahmebehandlung verwenden \([try\-, catch\- und throw](../cpp/try-throw-and-catch-statements-cpp.md)\-Anweisungen\).  
  
 Die Verbundanweisung nach der `__try`\-Klausel ist der abgesicherte Abschnitt.  Die Verbundanweisung nach der `__finally`\-Klausel ist der Beendigungshandler.  Der Handler gibt eine Reihe von Aktionen an, welche ausgeführt werden, wenn der geschützte Bereich verlassen wird, ungeachtet dessen, ob der geschützte Bereich durch eine Ausnahme verlassen wird \(nicht ordnungsgemäße Beendigung\) oder durch ein standardmäßiges Fortsetzen \(gewöhnliche Beendigung\).  
  
 Die Steuerung erreicht eine `__try`\-Anweisung durch einfache sequenzielle Ausführung \(Fortfahren\).  Wenn die Steuerung zu `__try` wechselt, wird der zugehörige Handler aktiv.  Wenn die Ablaufsteuerung das Ende des try\-Blocks erreicht, wird die Ausführung wie folgt fortgesetzt:  
  
1.  Der Beendigungshandler wird aufgerufen.  
  
2.  Wenn der Beendigungshandler abgeschlossen ist, wird die Ausführung nach der `__finally`\-Anweisung fortgesetzt.  Unabhängig davon, wie der abgesicherte Abschnitt endet \(z. B. über ein `goto` aus dem abgesicherten Text oder eine `return`\-Anweisung\), wird der Beendigungshandler ausgeführt, `before` die Ablaufsteuerung aus dem abgesicherten Abschnitt herausbewegt wird.  
  
     Eine **\_\_finally**\-Anweisung sperrt keine Suchvorgänge für einen geeigneten Ausnahmehandler.  
  
 Wenn eine Ausnahme im `__try`\-Block auftritt, muss das Betriebssystem einen Handler für die Ausnahme finden, andernfalls tritt ein Fehler im Programm auf.  Wenn ein Handler gefunden wird, werden sämtliche `__finally`\-Blöcke ausgeführt, und die Ausführung wird im Handler fortgesetzt.  
  
 Nehmen Sie z. B. an, eine Reihe von Funktionsaufrufen verbindet Funktion A mit Funktion D, wie in der folgenden Abbildung dargestellt.  Jede Funktion verfügt über einen Beendigungshandler.  Wenn eine Ausnahme in Funktion D ausgelöst und in A behandelt wird, werden die Beendigungshandler in folgender Reihenfolge aufgerufen, während das System den Stapel abwickelt: D, C, B.  
  
 ![Reihenfolge für das Beenden bei Handlerausführung](../cpp/media/vc38cx1.png "vc38CX1")  
Reihenfolge für das Beenden bei Handlerausführung  
  
> [!NOTE]
>  Das Verhalten von "try\-finally" unterscheidet sich von einigen anderen Sprachen, die die Verwendung von **finally** unterstützen, z. B. C\#.  Ein einzelnes `__try` hat möglicherweise eines von `__finally` und `__except`, jedoch nicht beide.  Wenn beide zusammen verwendet werden sollen, muss eine äußere try\-except\-Anweisung die innere try\-finally\-Anweisung einschließen.  Es gelten andere Regeln für die Angabe, wann ein einzelner Block ausgeführt wird.  
  
## Das \_\_leave\-Schlüsselwort  
 Das `__leave`\-Schlüsselwort ist nur im abgesicherten Abschnitt einer `try-finally`\-Anweisung gültig. Als Resultat wird zum Ende des abgesicherten Abschnitts gesprungen.  Die Ausführung wird mit der ersten Anweisung im Beendigungshandler fortgesetzt.  
  
 Eine `goto`\-Anweisung kann auch aus dem abgesicherten Abschnitt herausspringen, jedoch wird die Leistung beeinträchtigt, da sie eine Stapelentladung aufruft.  Die `__leave`\-Anweisung ist effizienter, da sie keine Stapelentladung verursacht.  
  
## Nicht ordnungsgemäße Beendigung  
 Eine `try-finally`\-Anweisung unter Verwendung der [longjmp](../c-runtime-library/reference/longjmp.md)\-Laufzeitfunktion zu beenden, wird als nicht ordnungsgemäße Beendigung angesehen.  Es ist nicht zulässig, in eine `__try`\-Anweisung zu springen, wohingegen das Herausspringen aus einer solchen zulässig ist.  Alle `__finally`\-Anweisungen, die zwischen dem Anfangspunkt \(normale Beendigung des `__try`\-Blocks\) und dem Ziel \(dem `__except`\-Block, der die Ausnahme behandelt\) aktiv sind, müssen ausgeführt werden.  Dies wird als "lokale Entladung" bezeichnet.  
  
 Wenn ein **try**\-Block aus irgendeinem Grund vorzeitig beendet wird \(auch durch Herausspringen aus dem Block\), führt das System den zugeordneten **finally**\-Block als Teil der Entladung des Stapels aus.  In solchen Fällen gibt die [AbnormalTermination](http://msdn.microsoft.com/library/windows/desktop/ms679265)\-Funktion TRUE zurück, wenn sie aus dem **finally**\-Block aufgerufen wird. Andernfalls wird FALSE zurückgegeben.  
  
 Der Beendigungshandler wird nicht aufgerufen, wenn ein Prozess während der Ausführung einer `try-finally`\-Anweisung abgebrochen wird.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)   
 [Strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Termination\-Handler Syntax](http://msdn.microsoft.com/library/windows/desktop/ms681393)