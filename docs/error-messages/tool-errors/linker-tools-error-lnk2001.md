---
title: Linkertoolfehler Lnk2001 | Microsoft Docs
ms.custom: 
ms.date: 05/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2001
dev_langs: C++
helpviewer_keywords: LNK2001
ms.assetid: dc1cf267-c984-486c-abd2-fd07c799f7ef
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51f78f436d0e19779d0ebca499a559a60d12bcf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2001"></a>Linkertoolfehler LNK2001
nicht aufgelöstes externes Symbol "*Symbol*"  
  
Der kompilierte Code wird ein Verweis oder ein Aufruf von *Symbol*, allerdings Symbol befindet sich nicht in einer der an den Linker festgelegten Objektdateien oder Bibliotheken definiert.  
  
Diese Fehlermeldung wird gefolgt von Schwerwiegender Fehler [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md). Sie müssen alle LNK2001 und LNK2019 Fehler zum Beheben von Fehler LNK1120 beheben.  
  
## <a name="possible-causes"></a>Mögliche Ursachen  
  
Es gibt viele Möglichkeiten, diesen Fehler zu erhalten, aber alle umfassen einen Verweis auf eine Funktion oder Variable, die nicht vom Linker *beheben*, oder suchen Sie eine Definition für. Der Compiler erkennen, wenn ein Symbol, das nicht *deklariert*, aber nicht wenn kein *definiert*, da die Definition in einer anderen Quelldatei oder Bibliothek sein kann. Wenn ein Symbol bezeichnet, aber nie definiert, generiert der Linker einen Fehler aus.  
  
### <a name="coding-issues"></a>Codeprobleme  
  
Dieser Fehler kann verursacht werden, nicht übereinstimmende Schreibweise in Ihrem Quellcode oder Moduldefinitionsdatei (.def) Datei. Angenommen, Sie benennen Sie eine Variable `var1` in einer C++-Quelldatei, und versuchen Sie es für den Zugriff darauf als `VAR1` in eine andere, dieser Fehler wird generiert. Um dieses Problem zu beheben, verwenden Sie konsistent geschrieben und Groß-/Kleinschreibung beachtet Namen.  
  
Dieser Fehler kann verursacht werden, in ein Projekt, verwendet [Inlinefunktionen](../../error-messages/tool-errors/function-inlining-problems.md) Wenn Sie die Funktionen in einer Quelldatei und nicht in einer Headerdatei definieren. Inlinefunktionen können nicht außerhalb der Quelldatei sichtbar ist, die sie definiert. Um dieses Problem zu beheben, definieren Sie die Inlinefunktionen in den Headern, in dem sie deklariert werden.  
  
Dieser Fehler kann verursacht werden, wenn Sie eine C-Funktion aus einem C++-Programm, ohne Aufrufen eine `extern "C"` Deklaration für die C-Funktion. Der Compiler verwendet unterschiedliche interne symbolnamenskonventionen für C- und C++-Code, und es ist die interne Symbolnamen, den der Linker sucht nach beim Auflösen von Symbolen. Verwenden Sie zum Beheben dieses Problems eine `extern "C"` Wrapper für alle Deklarationen von C-Funktionen verwendet, die im C++-Code, wodurch den Compiler die interne C-Namenskonvention für diese Symbole verwenden. Compileroptionen [/TP](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) und [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) bewirken, dass der Compiler Dateien unabhängig von der Erweiterung bzw. als C++- oder C, zu kompilieren. Diese Optionen können dazu führen, dass interne Funktionsnamen unterscheiden, was Sie erwarten.  
  
Dieser Fehler kann verursacht werden, versucht, Funktionen oder Daten, die externen Verknüpfung besitzen verweisen. In C++ sind Inlinefunktionen und `const` Daten eine interne Bindung haben, es sei denn, Sie explizit als angegeben `extern`. Um dieses Problem zu beheben, verwenden Sie explizite `extern` Deklarationen auf Symbole außerhalb der definierenden Quelldatei bezeichnet.  
  
Dieser Fehler kann verursacht werden, indem eine [fehlender Funktionsrumpf oder fehlende Variable](../../error-messages/tool-errors/missing-function-body-or-variable.md) Definition. Dieser Fehler ist üblich, wenn Sie deklarieren, aber nicht definieren, Variablen, Funktionen oder Klassen in Ihrem Code. Der Compiler benötigt nur einen Funktionsprototyp oder `extern` Variablendeklaration ohne Fehler, sondern der Linker eine Objektdatei generiert kann einen Aufruf der Funktion oder ein Verweis auf die Variable auflösen, da keine Funktion Code oder eine Variable Speicherplatz vorhanden ist reserviert. Zur Behebung dieses Problems sicher, dass jeder Funktion verwiesen wird und die Variable in einer Quelldatei oder die Bibliothek, die in Ihrem Link enthalten vollständig definiert ist.  
  
Dieser Fehler kann durch einen Funktionsaufruf verursacht werden, die verwendet Rückgabe- und Parametertypen oder Aufrufkonventionen, die nicht in der Definition der Funktion entsprechen. In C++-Objektdateien [benennen Sie die Ergänzung](../../error-messages/tool-errors/name-decoration.md) umfasst die Aufrufkonvention, die Klasse oder Namespace-Gültigkeitsbereich und die Rückgabe- und Parametertypen einer Funktion in der endgültigen ergänzten Funktionsnamen ein, die verwendet wird, wie das Symbol entsprechend wann Aufrufe die Funktion aus anderen Objektdateien werden aufgelöst. Um dieses Problem zu beheben, stellen Sie sicher, dass die Deklaration, Definition und Aufrufe an die Funktion, die alle die gleichen Bereiche, Typen und Aufrufkonventionen verwenden.  
  
Dieser Fehler kann in C++-Code verursacht werden, wenn Sie einen Funktionsprototyp in einer Klassendefinition einschließen, aber nicht mehr [enthalten die Implementierung](../../error-messages/tool-errors/missing-function-body-or-variable.md) der Funktion, und nennen Sie es. Um dieses Problem zu beheben, werden Sie sicher, dass eine Definition für alle aufgerufen, die Member einer Klasse deklariert bereitzustellen.  
  
Dieser Fehler kann durch ein Versuch, eine reine virtuelle Funktion von einer abstrakten Basisklasse aufzurufen verursacht werden. Eine reine virtuelle Funktion verfügt über keine Implementierung der Basisklasse. Zur Behebung dieses Problems sicher, dass alle aufgerufen virtuelle Funktionen implementiert werden.  
  
Dieser Fehler kann verursacht werden, indem Sie versuchen, eine Variable deklariert, die innerhalb einer Funktion verwenden ([eine lokale Variable](../../error-messages/tool-errors/automatic-function-scope-variables.md)) außerhalb des Bereichs dieser Funktion. Um dieses Problem zu beheben, entfernen Sie den Verweis auf die Variable, die nicht im Gültigkeitsbereich befindet, oder verschieben Sie die Variable auf einen höheren Bereich.  
  
Dieser Fehler kann auftreten, beim Erstellen einer Releaseversion eines ATL-Projekts, erzeugen eine Meldung, dass CRT-Startcode erforderlich ist. Um dieses Problem zu beheben, führen Sie eine der folgenden  
  
-   Entfernen Sie `_ATL_MIN_CRT` definiert, aus der Liste der Präprozessor zum Zulassen von CRT-Startcode eingeschlossen werden sollen. Finden Sie unter [Eigenschaftenseite "Allgemein" (Projekt)](../../ide/general-property-page-project.md) für Weitere Informationen.  
  
-   Entfernen Sie nach Möglichkeit, Aufrufe von CRT-Funktionen, die CRT-Startcode erfordern. Verwenden Sie stattdessen ihre Win32-Entsprechungen. Verwenden Sie z. B. `lstrcmp` anstelle von `strcmp`. Bekannte Funktionen, die CRT-Startcode erfordern, sind Teil der Zeichenfolge und Gleitkommafunktionen.  
  
### <a name="compilation-and-link-issues"></a>Probleme mit der Kompilierung und Verknüpfung  
  
Dieser Fehler kann auftreten, wenn das Projekt einen Verweis auf eine Bibliothek nicht vorhanden ist (. LIB) oder ein Objekt (. OBJ)-Datei. Um dieses Problem zu beheben, fügen Sie dem Projekt einen Verweis auf die erforderliche Bibliothek oder Objektdatei hinzu. Weitere Informationen finden Sie unter [LIB-Dateien als Linkereingabe](../../build/reference/dot-lib-files-as-linker-input.md).  
  
Dieser Fehler kann auftreten, wenn Sie verwenden die [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) oder [Zl](../../build/reference/zl-omit-default-library-name.md) Optionen. Wenn Sie diese Optionen angeben, werden erforderliche Code enthaltenen Bibliotheken nicht in das Projekt verknüpft, es sei denn, Sie explizit aufgenommen haben. Um dieses Problem zu beheben, müssen schließen Sie explizit alle Bibliotheken ein, die in der Linkerbefehlszeile verwendet. Wenn viele fehlende CRT oder Standardbibliothek-Funktionsnamen angezeigt wird, wenn Sie diese Optionen verwenden, müssen enthalten Sie die Dateien CRT und Standard-Bibliothek-DLLs oder Bibliothek explizit, unter dem Link.  

Wenn Sie mit: Kompilieren Sie die **"/ CLR"** aktivieren, treten möglicherweise ein fehlenden Verweis auf ".cctor". Um dieses Problem zu beheben, finden Sie unter [Initialisierung gemischter Assemblys](../../dotnet/initialization-of-mixed-assemblies.md) für Weitere Informationen.  
  
Dieser Fehler kann auftreten, wenn Sie mit dem Modus Releasebibliotheken, beim Erstellen einer Debugversion einer Anwendung verknüpfen. Auf ähnliche Weise, wenn Sie Optionen verwenden **/MTd** oder **/MDd** oder definieren `_DEBUG` und dann mit den Releasebibliotheken zu verknüpfen, viele potenzielle nicht aufgelöste externen, neben anderen Problemen zu rechnen. Verknüpfen einen Releasebuild der Modus mit den Debugbibliotheken bewirkt auch, dass ähnliche Probleme. Zur Behebung dieses Problems sicher, Sie verwenden die Debugbibliotheken Debug-Builds und Retail-Bibliotheken in Ihrer Retail erstellt.  
  
Dieser Fehler kann auftreten, wenn Code bezieht sich auf ein Symbol, das von einer Version einer Bibliothek, aber Sie eine andere Version der Bibliothek an den Linker geben. Sie können im Allgemeinen nicht mischen, Objektdateien oder Bibliotheken, die für unterschiedliche Versionen des Compilers erstellt werden. Die Bibliotheken, die in einer neuen Version liefern können es sich um Symbole enthalten, die in den vorherigen Versionen und umgekehrt enthaltenen Bibliotheken nicht gefunden werden kann. Um dieses Problem zu beheben, erstellen Sie alle Objektdateien und Bibliotheken mit der gleichen Version des Compilers vor miteinander verknüpfen.  
  
-  Die Tools &#124; Optionen &#124; Projekte &#124; VC++-Verzeichnisse im Dialogfeld unter Dateiauswahl "Bibliothek" können Sie die Suchreihenfolge der Bibliothek ändern. Der Ordner "Linker" im Dialogfeld Eigenschaftenseiten des Projekts kann auch Pfade enthalten, die veraltet sein könnten.  
  
-  Dieses Problem kann auftreten, wenn ein neues SDK (vielleicht um einen anderen Speicherort) installiert ist, und die Suchreihenfolge nicht aktualisiert wird, um auf den neuen Speicherort zu verweisen. Normalerweise, platzieren Sie den Pfad zum neuen SDK enthalten und lib-Verzeichnissen, vor der Standardspeicherort für Visual C++. Darüber hinaus kann ein Projekt mit eingebetteten Pfaden weiterhin auf alte Pfade verweisen, die sind gültig, aber für neue Funktionen hinzugefügt, die von der neuen Version, die an einen anderen Speicherort installiert ist veraltet.  
  
-   Wenn Sie in der Befehlszeile erstellen und Ihren eigenen Umgebungsvariablen erstellt haben, stellen Sie sicher, dass die Pfade zu den Tools, Bibliotheken und Header-Dateien auf eine konsistente Version wechseln. Weitere Informationen finden Sie unter [Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)
  
Es gibt derzeit keinen Standard für [C++ naming](../../error-messages/tool-errors/name-decoration.md) zwischen compileranbietern oder sogar zwischen unterschiedlichen Versionen eines Compilers. Aus diesem Grund Verknüpfen von Objektdateien, die mit anderen Compilern kompiliert möglicherweise nicht dasselbe Benennungsschema erstellt und somit Fehler LNK2001 verursacht.  
  
[Kompilieren Sie mischen Inline- und nicht Optionen](../../error-messages/tool-errors/function-inlining-problems.md) auf verschiedenen Modulen können LNK2001. Wenn eine C++-Bibliothek mit Inlinefunktionen eingeschaltet erstellt wird (**/Ob1** oder **/Ob2**) jedoch die entsprechende Headerdatei, beschreibt die Funktionen inlining deaktiviert (kein `inline` Schlüsselwort), diesen Fehler Tritt auf. Um dieses Problem zu beheben, definieren Sie die Funktionen `inline` in der Headerdatei, die Sie in anderen Quelldateien enthalten.  
  
Bei Verwendung der `#pragma inline_depth` Compiler, stellen Sie sicher, dass Ihnen eine [Wert 2 oder höher festgelegt](../../error-messages/tool-errors/function-inlining-problems.md), und stellen Sie sicher, dass Sie auch verwenden, die [/Ob1](../../build/reference/ob-inline-function-expansion.md) oder [/Ob2](../../build/reference/ob-inline-function-expansion.md) -Compileroption.  
  
Dieser Fehler kann auftreten, wenn Sie den LINK weglassen/NOENTRY option, wenn Sie eine reine Ressourcen-DLL erstellen. Um dieses Problem zu beheben, fügen Sie die Option/NOENTRY auf den Linkbefehl.  
  
Dieser Fehler kann auftreten, wenn Sie falsch/Subsystem oder/Entry Einstellungen in Ihrem Projekt verwenden. Z. B. Wenn Sie eine Konsolenanwendung schreiben und geben Sie die/Subsystem: Windows, nicht aufgelöster externe Fehler generiert für `WinMain`. Um dieses Problem zu beheben, stellen Sie sicher, dass Sie die Optionen für den Projekttyp übereinstimmen. Weitere Informationen zu diesen Optionen und Einstiegspunkte finden Sie unter der [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) und [/Entry](../../build/reference/entry-entry-point-symbol.md) Optionen des Linkers.  
  
### <a name="exported-symbol-issues"></a>Exportierte Symbol-Probleme  
  
Dieser Fehler tritt auf, wenn ein Export aufgeführt, die in einer DEF-Datei nicht gefunden wird. Möglicherweise ist nicht vorhanden, ist falsch geschrieben oder ergänzte C++-Namen verwendet. Eine DEF-Datei wird nicht ergänzte Namen verwendet. Um dieses Problem zu beheben, entfernen Sie nicht benötigte Exporte, und verwenden `extern "C"` Deklarationen für die exportierten Symbolen.  
  
## <a name="what-is-an-unresolved-external-symbol"></a>Was ist ein nicht aufgelöstes externes Symbol?  
  
Ein *Symbol* ist der Name für eine Funktion oder globale Variable, die intern vom eine kompilierte Objektdatei oder Bibliothek verwendet. Ein Symbol ist *definiert* in der Objektdatei, dem Speicher zugeordnet ist, für eine globale Variable oder eine Funktion, in der kompilierte Code für den Funktionsrumpf platziert wird. Ein *externes Symbol* ist ein Symbol, die *referenzierte*, d. h. verwendet oder in einer Objektdatei aufgerufen, aber in einer anderen Bibliothek oder Objektdatei-Datei definiert. Ein *exportiert Symbol* eine, die öffentlich zur Verfügung gestellt werden, indem Sie die Objektdatei oder die Bibliothek, die es definiert ist. Der Linker muss *beheben*, oder suchen Sie die entsprechende Definition für jede externe Symbol auf einer Objektdatei verweisen, wenn sie in einer Anwendung oder DLL verknüpft ist. Der Linker generiert einen Fehler, wenn sie ein externes Symbol nicht auflösen kann, durch ein Symbol, das übereinstimmende exportierte in keiner der verknüpften Dateien suchen.    
  
## <a name="use-the-decorated-name-to-find-the-error"></a>Verwenden Sie den ergänzten Namen, um den Fehler zu finden
  
Die C++-Compiler und Linker Verwendung [Namensergänzung](../../error-messages/tool-errors/name-decoration.md), auch bekannt als *Name-mangling*, um zusätzliche Informationen zu den Typ einer Variablen oder den Rückgabetyp, Parametertypen, Bereich und Aufrufen codieren Konvention für eine Funktion in den Symbolnamen. Dieser ergänzter Name ist der Symbolname vom Linker, zum Auflösen externer Symbole gesuchte.  
  
Da die zusätzliche Informationen Teil des Symbolnamens wird, kann ein Linkfehler führen, wenn die Deklaration einer Funktion oder Variable nicht genau mit die Definition der Funktion oder Variable übereinstimmt. Dies kann geschehen, selbst wenn dieselbe Headerdatei in den aufrufenden Code und das Definieren von Code verwendet wird, wenn verschiedene Compilerflags verwendet werden, wenn die Quelldateien zu kompilieren. Beispielsweise können Sie diesen Fehler erhalten, wenn der Code kompiliert wird, um zu verwenden die `__vectorcall` Aufrufkonvention, aber Sie link in einer Bibliothek, die von Clients unter Verwendung des standardmäßigen Aufruf erwartet `__cdecl` oder `__fastcall` Aufrufkonvention. In diesem Fall stimmen die Symbole nicht überein, da die Aufrufkonventionen unterschiedlich sind.   
  
Um die Ursache für diese Art von Fehler leichter zu finden, zeigt der Linker eine Fehlermeldung sowohl der "Anzeigename" den Namen im Quellcode und den ergänzten Namen (in Klammern) für nicht aufgelöstes externes Symbol verwendet. Sie müssen nicht wissen, wie Sie übersetzen den ergänzten Namen in die Lage, mit anderen ergänzten Namen verglichen werden soll. Sie können Befehlszeilentools verwenden, die mit dem Compiler zum Vergleichen der erwarteten Symbolname und den tatsächlichen Symbolnamen enthalten sind:  

-   Die [/EXPORTS](../../build/reference/dash-exports.md) und [/SYMBOLS](../../build/reference/symbols.md) Optionen des DUMPBIN-Befehlszeilentools können Sie ermitteln, welche Symbole in den DLL- und Objekt- oder Bibliotheksdateien definiert sind. Sie können diese verwenden, um sicherzustellen, dass die exportierten Namen übereinstimmen ergänzt, die den ergänzten vom Linker gesucht werden.  
  
In einigen Fällen meldet der Linker kann nur den ergänzten Name für ein Symbol. Sie können das Befehlszeilentool UNDNAME verwenden, nicht ergänzte Format eines ergänzten Namens abgerufen.  
  
## <a name="additional-resources"></a>Zusätzliche Ressourcen  
  
Weitere Informationen zu möglichen Ursachen und Lösungen für LNK2001, finden Sie unter der Stack Overflow-Frage [Was ist ein nicht definierten Verweis/ein nicht aufgelöstes externes Symbol Fehler und wie behebe ich das Problem?](http://stackoverflow.com/q/12573816/2002113).  

