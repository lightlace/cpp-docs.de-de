---
title: Linkertoolfehler Lnk2001 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2001
dev_langs:
- C++
helpviewer_keywords:
- LNK2001
ms.assetid: dc1cf267-c984-486c-abd2-fd07c799f7ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3da81f46514fbdd7d01ce9c2a9d8be6007301b45
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861576"
---
# <a name="linker-tools-error-lnk2001"></a>Linkertoolfehler LNK2001

nicht aufgelöstes externes Symbol "*Symbol*"

Der kompilierte Code stellt einen Verweis oder einen Aufruf von *Symbol*, aber dieses Symbol ist nicht definiert, in die Bibliotheken oder Objektdateien, die dem Linker angegeben.

Diese Fehlermeldung folgt Schwerwiegender Fehler [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md). Sie müssen alle LNK2001 und LNK2019 Fehler zum Beheben von Fehler LNK1120 beheben.

## <a name="possible-causes"></a>Mögliche Ursachen

Es gibt viele Möglichkeiten, um diesen Fehler zu erhalten, aber alle umfassen einen Verweis auf eine Funktion oder Variable, die der Linker kann nicht *beheben*, oder suchen Sie eine Definition für. Der Compiler erkennen, wenn ein Symbol nicht *deklariert*, aber nicht bei nicht *definiert*, weil die Definition in einer anderen Quelldatei oder eine Bibliothek sein kann. Wenn ein Symbol ist bezeichnet, aber nicht definiert, generiert der Linker einen Fehler aus.

### <a name="coding-issues"></a>Codierungsprobleme

Dieser Fehler kann verursacht werden, nicht übereinstimmenden Groß-/Kleinschreibung in Ihrem Quellcode oder eine Moduldefinitionsdatei (.def) Datei. Wenn Sie den Namen einer Variablenverweis z. B. `var1` in einer C++-Quelldatei, und versuchen Sie es für den Zugriff als `VAR1` in einer anderen, kann dieser Fehler wird generiert. Um dieses Problem zu beheben, verwenden Sie konsistent Schreibweise und Groß-/Kleinschreibung Namen.

Dieser Fehler kann verursacht werden, in ein Projekt, verwendet [inlineersetzung](../../error-messages/tool-errors/function-inlining-problems.md) , wenn Sie die Funktionen in einer Quelldatei und nicht in einer Headerdatei definieren. Inlinefunktionen können nicht außerhalb der Quelldatei angezeigt werden, die sie definiert. Um dieses Problem zu beheben, definieren Sie die Inline-Funktionen in den Headern, in dem sie deklariert werden.

Dieser Fehler kann verursacht werden, wenn Sie eine C-Funktion aus einem C++-Programm, ohne Aufrufen eine `extern "C"` Deklaration für die C-Funktion. Der Compiler verwendet verschiedene interne symbolnamenskonventionen für C- und C++-Code, und den internen Symbolnamen, den der Linker sucht nach, wenn Symbole aufgelöst werden kann. Um dieses Problem zu beheben, verwenden Sie eine `extern "C"` Wrapper für alle Deklarationen von C-Funktionen, die in Ihren C++-Code, wodurch den Compiler verwendet die interne C-Namenskonvention für diese Symbole verwendet. Compileroptionen [/TP](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) und [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) bewirken, dass der Compiler Dateien als C++- oder C, unabhängig von der Erweiterung bzw. kompilieren. Diese Optionen können dazu führen, dass interne Funktionsnamen unterscheiden, was Sie erwarten.

Dieser Fehler kann verursacht werden, versucht, auf Sie verweisen, Funktionen oder Daten, die externen Bindung verfügen. In C++ sind Inlinefunktionen und `const` Daten eine interne Bindung haben, sofern nicht ausdrücklich angegeben als `extern`. Um dieses Problem zu beheben, verwenden Sie explizite `extern` Deklarationen von Symbolen außerhalb der definierenden Quelldatei bezeichnet.

Dieser Fehler kann verursacht werden, indem eine [fehlender Funktionsrumpf oder fehlende Variable](../../error-messages/tool-errors/missing-function-body-or-variable.md) Definition. Dieser Fehler ist häufig, wenn Sie deklarieren, aber nicht festlegen, Variablen, Funktionen oder Klassen in Ihrem Code. Der Compiler benötigt nur einen Funktionsprototyp oder `extern` Variablendeklaration eine Objektdatei ohne Fehler, sondern der Linker generiert kann einen Aufruf der Funktion oder ein Verweis auf die Variable auflösen, da die Funktion Code oder eine Variable ein Leerzeichen vorhanden ist reserviert. Um dieses Problem zu beheben, stellen Sie sicher, dass alle referenzierten Funktion und die Variable in einer Quelldatei oder in Ihrem Link-Bibliothek vollständig definiert ist.

Dieser Fehler kann durch einen Funktionsaufruf verursacht werden, die Rückgabe-und Parametertypen oder Aufrufkonventionen, die nicht in der Definition der Funktion entsprechen verwendet. In C++-Objektdateien [Namen Decoration](../../error-messages/tool-errors/name-decoration.md) umfasst die Aufrufkonvention, Klasse oder Namespace-Gültigkeitsbereich und die Rückgabe- und Parametertypen einer Funktion in der endgültigen ergänzten Funktionsnamen ein, die verwendet wird, wie das Symbol entsprechend Wenn Aufrufe die Funktion aus anderen Objektdateien werden aufgelöst. Um dieses Problem zu beheben, stellen Sie sicher, dass die Deklaration, Definition und Aufrufe an die Funktion, die alle die gleichen Bereiche, Typen und Aufrufkonventionen verwenden.

Dieser Fehler kann in C++-Code verursacht werden, wenn Sie einen Funktionsprototyp in einer Klassendefinition enthalten, aber nicht [enthalten die Implementierung](../../error-messages/tool-errors/missing-function-body-or-variable.md) der Funktion, und dann aufgerufen wird. Um dieses Problem zu beheben, werden Sie Sie sicher, dass eine Definition für alle aufgerufen, die Member einer Klasse deklariert.

Dieser Fehler kann von einem Versuch, eine reine virtuelle Funktion aus einer abstrakten Klasse aufrufen verursacht werden. Eine reine virtuelle Funktion verfügt über keine Implementierung der Basisklasse. Um dieses Problem zu beheben, stellen Sie sicher, dass alle virtuellen Funktionen implementiert werden.

Dieser Fehler kann verursacht werden, indem Sie versuchen, eine Variable deklariert, die innerhalb einer Funktion verwenden ([eine lokale Variable](../../error-messages/tool-errors/automatic-function-scope-variables.md)) außerhalb des Bereichs dieser Funktion. Um dieses Problem zu beheben, entfernen Sie den Verweis auf die Variable, die nicht im Bereich befindet, oder verschieben Sie die Variable in einem höheren Bereich.

Dieser Fehler kann auftreten, bei der Erstellung einer Releaseversion der ein ATL-Projekt, erstellen eine Meldung, dass CRT-Startcode erforderlich ist. Um dieses Problem beheben, führen Sie eine der folgenden

- Entfernen Sie `_ATL_MIN_CRT` aus der Liste der Präprozessor definiert werden, um die CRT-Startcode enthalten sein kann. Finden Sie unter [Eigenschaftenseite "Allgemein" (Projekt)](../../ide/general-property-page-project.md) für Weitere Informationen.

- Wenn möglich, entfernen Sie Aufrufe von CRT-Funktionen, für die CRT-Startcode erforderlich. Verwenden Sie stattdessen ihre Win32-Entsprechungen. Verwenden Sie z. B. `lstrcmp` anstelle von `strcmp`. Bekannten Funktionen, die CRT-Startcode erfordern sind Teil der Zeichenfolge und Gleitkommafunktionen.

### <a name="compilation-and-link-issues"></a>Probleme mit der Kompilierung und Verknüpfung

Dieser Fehler kann auftreten, wenn das Projekt einen Verweis auf eine Bibliothek fehlt (. LIB) oder ein Objekt (. OBJ)-Datei. Um dieses Problem zu beheben, fügen Sie dem Projekt einen Verweis auf die erforderliche Bibliothek oder Objektdatei hinzu. Weitere Informationen finden Sie unter [LIB-Dateien als Linkereingabe](../../build/reference/dot-lib-files-as-linker-input.md).

Dieser Fehler kann auftreten, wenn Sie verwenden die [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) oder [/Zl](../../build/reference/zl-omit-default-library-name.md) Optionen. Wenn Sie diese Optionen angeben, werden erforderlichen Code enthaltenen Bibliotheken nicht in das Projekt verknüpft, es sei denn, Sie explizit eingeschlossen haben. Um dieses Problem zu beheben, müssen enthalten Sie explizit alle Bibliotheken, die Sie auf die Link-Befehlszeile verwenden. Wenn viele fehlende CRT oder Funktionsnamen angezeigt wird, wenn Sie diese Optionen verwenden, müssen enthalten Sie die CRT und Standard-Bibliothek-DLLs oder Bibliotheksdateien Dateien explizit, unter dem Link.

Wenn Sie mit der Kompilierung der **"/ CLR"** option, es kann ein fehlender Verweis auf ".cctor". Um dieses Problem zu beheben, finden Sie unter [Initialization of Mixed Assemblies](../../dotnet/initialization-of-mixed-assemblies.md) für Weitere Informationen.

Dieser Fehler kann auftreten, wenn Sie die Release-Modus-Bibliotheken beim Erstellen einer Debugversion einer Anwendung verknüpfen. Auf ähnliche Weise bei der Verwendung von Optionen **/MTd** oder **/MDd** oder definieren Sie `_DEBUG` , und klicken Sie dann auf die Version Bibliotheken verknüpfen, erwarten, dass viele potenzielle nicht aufgelöste externe, neben anderen Problemen. Verknüpfen einen Releasebuild der Modus mit den Debugbibliotheken bewirkt auch, dass ähnliche Probleme. Um dieses Problem zu beheben, stellen Sie sicher Verwendung der Debugbibliotheken in den Debugbuilds, Einzelhandel-Bibliotheken in Ihrer Retail-builds.

Dieser Fehler kann auftreten, wenn Ihr Code auf ein Symbol, von einer Version einer Bibliothek verweist, aber Sie eine andere Version der Bibliothek an den Linker bereitstellen. Sie können im Allgemeinen nicht mischen, Objektdateien oder Bibliotheken, die für verschiedene Versionen des Compilers erstellt werden. Die Bibliotheken, die in einer neuen Version liefern können es sich um Symbole enthalten, die in den Bibliotheken, die in früheren Versionen und umgekehrt enthalten nicht gefunden werden kann. Um dieses Problem zu beheben, erstellen Sie alle Objektdateien und Bibliotheken mit der gleichen Version des Compilers vor miteinander verknüpft werden.

- Die Tools &#124; Optionen &#124; Projekte &#124; VC++-Verzeichnisse im Dialogfeld unter die Auswahl des Library-Dateien, können Sie die Suchreihenfolge der Bibliothek zu ändern. Das Dialogfeld "Eigenschaftenseiten" des Projekts im Ordner Linker kann auch Pfade enthalten, die veraltet sein könnten.

- Dieses Problem kann auftreten, wenn ein neues SDK (z. B. an einen anderen Speicherort) installiert ist, und die Suchreihenfolge nicht aktualisiert wird, um auf den neuen Speicherort zu verweisen. In der Regel sollten Sie dort den Pfad zum neuen SDK enthalten und lib-Verzeichnisse vor den Standardspeicherort für die Visual C++. Darüber hinaus kann ein Projekt mit eingebetteten Pfaden nach wie vor auf alte Pfade verweisen, die sind gültig, aber für neue Funktionen hinzugefügt, indem die neue Version, die an einen anderen Speicherort installiert ist veraltet.

- Wenn Sie in der Befehlszeile erstellen und Ihre eigenen Umgebungsvariablen erstellt haben, stellen Sie sicher, dass die Pfade zu den Tools, Bibliotheken und Headerdateien zum eine konsistente Version wechseln. Weitere Informationen finden Sie unter [Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)

Es gibt derzeit keinen Standard für [C++ Benennung](../../error-messages/tool-errors/name-decoration.md) zwischen compileranbietern oder sogar zwischen unterschiedlichen Versionen eines Compilers. Aus diesem Grund Verknüpfen von Objektdateien, die mit anderen Compilern kompiliert möglicherweise nicht dasselbe Benennungsschema erstellt und somit Fehler LNK2001 verursacht.

[Mischen von Inline und nicht-Inline-Kompilierungsoptionen](../../error-messages/tool-errors/function-inlining-problems.md) können auf verschiedene Module LNK2001 verursacht. Wenn eine C++-Bibliothek mit Inlinefunktionen eingeschaltet erstellt wird (**/Ob1** oder **/Ob2**) jedoch die entsprechende Headerdatei, beschreibt die Funktionen inlining deaktiviert (kein `inline` Schlüsselwort), diesen Fehler Tritt auf. Um dieses Problem zu beheben, definieren Sie die Funktionen `inline` in der Headerdatei, die Sie in anderen Quelldateien enthalten.

Bei Verwendung der `#pragma inline_depth` Compiler, stellen Sie sicher, Sie haben eine [Wert 2 oder höher festgelegt](../../error-messages/tool-errors/function-inlining-problems.md), und stellen Sie sicher, dass Sie auch verwenden, die [/Ob1](../../build/reference/ob-inline-function-expansion.md) oder [/Ob2](../../build/reference/ob-inline-function-expansion.md) -Compileroption.

Dieser Fehler kann auftreten, wenn Sie den LINK weglassen option/NOENTRY, wenn Sie eine reine Ressourcen-DLL erstellen. Um dieses Problem zu beheben, fügen Sie die Option/NOENTRY auf den Linkbefehl.

Dieser Fehler kann auftreten, wenn Sie falsche/Subsystem oder/Entry-Einstellungen in Ihrem Projekt verwenden. Z. B. Wenn Sie eine Konsolenanwendung, und geben Sie die native, nicht aufgelöster externe Fehler generiert für `WinMain`. Um dieses Problem zu beheben, stellen Sie sicher, dass Sie mit den Optionen für den Projekttyp übereinstimmen. Weitere Informationen zu diesen Optionen und Einstiegspunkte finden Sie unter den [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) und [/Entry](../../build/reference/entry-entry-point-symbol.md) Optionen des Linkers.

### <a name="exported-symbol-issues"></a>Probleme mit dem exportierten symbol

Dieser Fehler tritt auf, wenn ein Export in eine DEF-Datei aufgelisteten nicht gefunden wird. Dies könnte sein, da er nicht vorhanden, falsch geschrieben oder ergänzte C++-Namen verwendet. Eine DEF-Datei nimmt nicht ergänzte Namen. Um dieses Problem zu beheben, entfernen Sie nicht benötigte Exporte aus, und verwenden Sie `extern "C"` Deklarationen für die exportierten Symbolen.

## <a name="what-is-an-unresolved-external-symbol"></a>Was ist ein nicht aufgelöstes externes Symbol?

Ein *Symbol* ist der Name für eine Funktion oder globale Variable, die intern von einer kompilierte Objektdatei oder Bibliothek verwendet. Ein Symbol ist *definiert* in der Objektdatei, dem Speicher zugeordnet ist, für eine globale Variable oder eine Funktion, in der kompilierte Code für den Funktionsrumpf befindet. Ein *externes Symbol* ein Symbolzeichen ist, dass das *auf die verwiesen wird*, d. h. verwendet oder in einer Objektdatei Namens, jedoch in einer anderen Bibliothek oder Objektdatei-Datei definiert. Ein *exportierten Symbol* ist ein, der öffentlich zur Verfügung gestellt werden, indem Sie die Objektdatei oder eine Bibliothek, die es definiert. Der Linker muss *beheben*, oder suchen Sie die entsprechende Definition für jede externe Symbol auf die durch eine Objektdatei verwiesen wird, wenn sie in einer Anwendung oder DLL verknüpft ist. Der Linker generiert einen Fehler auf, wenn er ein externes Symbol nicht auflösen kann, durch eine entsprechende exportierten Symbol in einer der verknüpften Dateien suchen.

## <a name="use-the-decorated-name-to-find-the-error"></a>Verwenden Sie den ergänzten Namen, um den Fehler zu finden

Die C++-Compiler und Linker Verwendung [Namensergänzung](../../error-messages/tool-errors/name-decoration.md), auch bekannt als *Name-mangling*, um zusätzliche Informationen zu den Typ einer Variablen oder der Rückgabetyp, Parametertypen, Bereich und Aufruf codieren die Konvention für die eine Funktion in den Symbolnamen an. Dieses ergänzte Name wird den Symbolnamen, die vom Linker, zum Auflösen externer Symbole verwendet gesuchte.

Da die zusätzliche Informationen Teil des Symbolnamens wird, kann ein Linkfehler führen, wenn die Deklaration einer Funktion oder Variable nicht genau mit die Definition der Funktion oder Variable übereinstimmt. Dies kann passieren, auch wenn dieselbe Headerdatei sowohl der aufrufende Code und den Code definieren verwendet wird, wenn verschiedene Compilerflags verwendet werden, wenn die Quelldateien zu kompilieren. Beispielsweise erhalten Sie diesen Fehler, wenn der Code kompiliert wird, um Sie verwenden die `__vectorcall` Aufrufkonvention, aber Sie link zu einer Bibliothek, die von Clients mithilfe der standardmäßigen aufrufen erwartet `__cdecl` oder `__fastcall` Aufrufkonvention. In diesem Fall stimmen die Symbole nicht überein, da die Aufrufkonventionen unterschiedlich sind.

Damit können Sie die Ursache für diese Art von Fehler zu finden, zeigt die Fehlermeldung für den Linker sowohl der "Anzeigename" den Namen, die in Quellcode und den ergänzten Namen (in Klammern) für die nicht aufgelöstes externes Symbol verwendet. Sie müssen nicht wissen, wie der ergänzte Name werden sollen, vergleicht sie mit anderen ergänzten Namen zu übersetzen. Sie können Befehlszeilentools verwenden, die mit dem Compiler zum Vergleichen der erwarteten Symbolname und den tatsächlichen Symbolnamen enthalten sind:

- Die [/EXPORTS](../../build/reference/dash-exports.md) und [& gt; SYMBOLE](../../build/reference/symbols.md) Optionen des DUMPBIN-Befehlszeilentools können Sie ermitteln, welche Symbole in den DLL- und Objekt- oder Bibliotheksdateien definiert sind. Sie können dies verwenden, um sicherzustellen, dass die exportierten Namen übereinstimmen ergänzt, die der ergänzten den Linker sucht nach Namen.

In einigen Fällen meldet der Linker kann nur den ergänzten Name für ein Symbol. Sie können das Befehlszeilentool UNDNAME verwenden, zum Abrufen eines ergänzten Namens nicht ergänzten Formulars.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Weitere Informationen zu möglichen Ursachen und Lösungen für LNK2001 finden Sie unter der Stack Overflow-Frage [Was ist ein Fehler für undefined Reference/unresolved external Symbol, und wie behebe ich es?](http://stackoverflow.com/q/12573816/2002113).

