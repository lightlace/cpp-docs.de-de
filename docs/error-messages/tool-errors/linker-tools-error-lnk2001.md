---
title: Linkertoolfehler LNK2001
ms.date: 12/19/2019
f1_keywords:
- LNK2001
helpviewer_keywords:
- LNK2001
ms.assetid: dc1cf267-c984-486c-abd2-fd07c799f7ef
ms.openlocfilehash: b6d1e53d8f057ddc93e2dfde65cb951d247dfcc0
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302132"
---
# <a name="linker-tools-error-lnk2001"></a>Linkertoolfehler LNK2001

> nicht aufgelöstes externes Symbol "*Symbol*"

Der kompilierte Code erstellt einen Verweis oder einen Verweis auf das *Symbol*. Das Symbol ist in Bibliotheken oder Objektdateien, die vom Linker durchsucht wurden, nicht definiert.

Auf diese Fehlermeldung folgt ein schwerwiegender Fehler [Linkertoolfehler LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md). Beheben Sie zum Beheben von Fehler Linkertoolfehler LNK1120 zuerst alle LNK2001-und LNK2019-Fehler.

Es gibt viele Möglichkeiten, LNK2001 Fehler zu erhalten. Alle Elemente beinhalten einen *Verweis* auf eine Funktion oder Variable, die der Linker nicht *Auflösen*kann, oder es wird eine Definition für gefunden. Der Compiler kann ermitteln, wann Ihr Code kein Symbol *deklariert* , aber nicht, wenn er eine solche nicht *definiert* . Das liegt daran, dass sich die Definition in einer anderen Quelldatei oder Bibliothek befinden kann. Wenn sich Ihr Code auf ein Symbol bezieht, aber nie definiert ist, generiert der Linker einen Fehler.

## <a name="what-is-an-unresolved-external-symbol"></a>Was ist ein nicht aufgelöstes externes Symbol?

Ein *Symbol* ist der interne Name für eine Funktion oder eine globale Variable. Dabei handelt es sich um die Form des Namens, der in einer kompilierten Objektdatei oder-Bibliothek verwendet oder definiert wird. Eine globale Variable wird in der Objektdatei definiert, der Speicher zugeordnet wird. Eine Funktion wird in der Objektdatei definiert, in der der kompilierte Code für den Funktions Text platziert wird. Ein *externes Symbol* ist ein Objekt, auf das in einer Objektdatei verwiesen wird, das jedoch in einer anderen Bibliothek oder Objektdatei definiert ist. Ein *exportiertes Symbol* wird von der Objektdatei oder der Bibliothek, in der es definiert ist, öffentlich verfügbar gemacht.

Zum Erstellen einer Anwendung oder dll muss jedes verwendete Symbol über eine Definition verfügen. Der Linker muss alle externen Symbole *Auflösen*, auf die von den einzelnen Objektdateien verwiesen wird, oder die entsprechende Definition für finden. Der Linker generiert einen Fehler, wenn er ein externes Symbol nicht auflösen kann. Dies bedeutet, dass der Linker in keiner der verknüpften Dateien eine entsprechende exportierte Symbol Definition finden konnte.

## <a name="compilation-and-link-issues"></a>Kompilierungs-und Link Probleme

Dieser Fehler kann auftreten:

- Wenn das Projekt keinen Verweis auf eine Bibliothek () fehlt. LIB) oder Objekt (. Obj-Datei). Um dieses Problem zu beheben, fügen Sie dem Projekt einen Verweis auf die erforderliche Bibliothek oder Objektdatei hinzu. Weitere Informationen finden Sie unter [lib-Dateien als Eingabe](../../build/reference/dot-lib-files-as-linker-input.md)für den Linker.

- Wenn das Projekt einen Verweis auf eine Bibliothek enthält (. LIB) oder Objekt (. Obj-Datei), die ihrerseits Symbole aus einer anderen Bibliothek erfordert. Dies kann auch vorkommen, wenn Sie keine Funktionen aufzurufen, die die Abhängigkeit verursachen. Um dieses Problem zu beheben, fügen Sie dem Projekt einen Verweis auf die andere Bibliothek hinzu. Weitere Informationen finden Sie Untergrund Legendes [zum klassischen Modell für das Verknüpfen: übernehmen von Symbolen für die Fahrt](https://devblogs.microsoft.com/oldnewthing/20130108-00/?p=5623).

- Wenn Sie die Optionen [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) oder [/Zl](../../build/reference/zl-omit-default-library-name.md) verwenden. Wenn Sie diese Optionen angeben, sind Bibliotheken, die erforderlichen Code enthalten, nicht mit dem Projekt verknüpft, es sei denn, Sie haben Sie explizit eingeschlossen. Um dieses Problem zu beheben, schließen Sie explizit alle Bibliotheken ein, die Sie in der Befehlszeile für den Link verwenden. Wenn viele fehlende CRT-oder Standard Bibliotheks Funktionsnamen angezeigt werden, wenn Sie diese Optionen verwenden, schließen Sie die CRT-und Standardbibliothek-DLLs bzw. Bibliotheksdateien explizit in den Link ein.

- Bei der Kompilierung mit der **/CLR** -Option. Möglicherweise fehlt ein Verweis auf `.cctor`. Weitere Informationen zum Beheben dieses Problems finden Sie unter [Initialisierung gemischter](../../dotnet/initialization-of-mixed-assemblies.md)Assemblys.

- Wenn Sie bei der Erstellung einer Debugversion einer Anwendung eine Verknüpfung mit den Releasemodusbibliotheken herstellen. Wenn Sie die Optionen **/MTD** oder **/MDD** verwenden oder `_DEBUG` definieren und dann Links zu den Releasebibliotheken verwenden, sollten Sie neben anderen Problemen auch viele potenziell nicht aufgelöste externale erwarten. Durch das Verknüpfen eines Releasemodusbuilds mit den Debugbibliotheken werden auch ähnliche Probleme verursacht. Um dieses Problem zu beheben, stellen Sie sicher, dass Sie die Debugbibliotheken in ihren Debugbuilds und die Einzelhandels Bibliotheken in ihren Einzelhandels Builds verwenden.

- Wenn sich Ihr Code auf ein Symbol aus einer Bibliotheksversion bezieht, verknüpfen Sie aber eine andere Version der Bibliothek. Im Allgemeinen ist es nicht möglich, Objektdateien oder Bibliotheken zu mischen, die für unterschiedliche Versionen des Compilers erstellt wurden. Die Bibliotheken, die in einer Version enthalten sind, enthalten möglicherweise Symbole, die in den Bibliotheken in anderen Versionen nicht gefunden werden können. Um dieses Problem zu beheben, erstellen Sie alle Objektdateien und Bibliotheken mit der gleichen Version des Compilers, bevor Sie miteinander verknüpft werden. Weitere Informationen finden [ C++ Sie unter binäre Kompatibilität 2015-2019](../../porting/binary-compat-2015-2017.md).

- , Wenn Bibliothekspfade veraltet sind. Im Dialogfeld Extras **> Optionen > Projekte > Dialogfeld "VC + +-Verzeichnisse** " unter der Auswahl von **Bibliotheksdateien** können Sie die Such Reihenfolge der Bibliothek ändern. Der Linker-Ordner im Dialogfeld Eigenschaften Seiten des Projekts kann auch Pfade enthalten, die möglicherweise veraltet sind.

- Wenn eine neue Windows SDK installiert ist (möglicherweise an einem anderen Speicherort). Die Bibliotheks Such Reihenfolge muss aktualisiert werden, um auf den neuen Speicherort zu verweisen. Normalerweise sollten Sie den Pfad zu den neuen SDK include-und lib-Verzeichnissen vor dem standardmäßigen C++ visuellen Speicherort platzieren. Außerdem kann ein Projekt, das eingebettete Pfade enthält, immer noch auf alte Pfade verweisen, die gültig sind, aber nicht aktuell sind. Aktualisieren Sie die Pfade für neue Funktionen, die von der neuen Version hinzugefügt werden, die an einem anderen Speicherort installiert ist.

- Wenn Sie in der Befehlszeile erstellen und eigene Umgebungsvariablen erstellt haben. Überprüfen Sie, ob die Pfade zu Tools, Bibliotheken und Header Dateien in eine konsistente Version gelangen. Weitere Informationen finden Sie unter [Festlegen der Pfad-und Umgebungsvariablen für Befehlszeilenbuilds](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md) .

## <a name="coding-issues"></a>Codierungs Probleme

Dieser Fehler kann die folgenden Ursachen haben:

- Nicht übereinstimmender Fall in Ihrem Quellcode oder in der Modul Definitionsdatei (. def). Wenn Sie z. b. eine Variable `var1` in einer C++ Quelldatei benennen und versuchen, auf die Variable als `VAR1` in einer anderen zuzugreifen, wird dieser Fehler generiert. Um dieses Problem zu beheben, verwenden Sie konsistent geschriebene und Schreibweise Namen.

- Ein Projekt, das das [Inlining von Funktionen](../../error-messages/tool-errors/function-inlining-problems.md)verwendet. Dies kann vorkommen, wenn Sie die Funktionen als `inline` in einer Quelldatei anstatt in einer Header Datei definieren. Inline Funktionen können nicht außerhalb der Quelldatei angezeigt werden, in der Sie definiert sind. Um dieses Problem zu beheben, definieren Sie die Inline Funktionen in den Headern, in denen Sie deklariert werden.

- Aufrufen einer c-Funktion von C++ einem Programm ohne Verwendung einer `extern "C"` Deklaration für die C-Funktion. Der Compiler verwendet andere interne Symbol Benennungs Konventionen für C C++ und Code. Beim Auflösen von Symbolen sucht der Linker nach dem internen Symbolnamen. Um dieses Problem zu beheben, verwenden Sie einen `extern "C"` Wrapper um alle Deklarationen von C- C++ Funktionen, die in Ihrem Code verwendet werden. Dies bewirkt, dass der Compiler die interne C-Benennungs Konvention für diese Symbole verwendet. Die Compileroptionen [/tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) und [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) bewirken, dass der Compiler C++ Dateien als bzw. C kompiliert, unabhängig von der Dateinamenerweiterung. Diese Optionen können dazu führen, dass interne Funktionsnamen von Ihren Erwartungen abweichen.

- Es wurde versucht, auf Funktionen oder Daten zu verweisen, für die keine externe Verknüpfung vorhanden ist. Inline C++Funktionen und `const` Daten in verfügen über interne Verknüpfungen, es sei denn, Sie werden explizit als `extern`angegeben. Um dieses Problem zu beheben, verwenden Sie explizite `extern` Deklarationen für Symbole, auf die außerhalb der definierenden Quelldatei verwiesen wird.

- Ein [fehlender Funktions Text oder eine Variablen](../../error-messages/tool-errors/missing-function-body-or-variable.md) Definition. Dieser Fehler wird häufig beim Deklarieren, aber nicht beim Definieren von Variablen, Funktionen oder Klassen im Code angezeigt. Der Compiler benötigt nur einen Funktionsprototyp oder eine `extern` Variablen Deklaration, um eine Objektdatei zu generieren, ohne dass ein Fehler aufgetreten ist, aber der Linker kann einen aufrufungstyp oder einen Verweis auf die Variable nicht auflösen, da kein Funktionscode oder variabler Speicherplatz reserviert ist. Um dieses Problem zu beheben, stellen Sie sicher, dass alle referenzierten Funktionen und Variablen in einer Quelldatei oder-Bibliothek definiert werden, die Sie verknüpfen.

- Ein Funktionsaufruf, der Rückgabe-und Parametertypen oder Aufruf Konventionen verwendet, die nicht mit denen in der Funktionsdefinition übereinstimmen. In C++ Objektdateien codiert die [namens](../../error-messages/tool-errors/name-decoration.md) Ergänzung die Aufruf Konvention, den Klassen-oder Namespace Bereich und die Rückgabe-und Parametertypen einer Funktion. Die codierte Zeichenfolge wird Teil des endgültigen ergänzten Funktionsnamens. Dieser Name wird vom Linker verwendet, um Aufrufe der Funktion aus anderen Objektdateien aufzulösen oder abzugleichen. Um dieses Problem zu beheben, stellen Sie sicher, dass die Funktionsdeklaration, die Definition und die Aufrufe die gleichen Bereiche, Typen und Aufruf Konventionen verwenden.

- C++der von Ihnen aufzurufende Code, wenn Sie einen Funktionsprototyp in eine Klassendefinition einschließen, aber nicht [die Implementierung](../../error-messages/tool-errors/missing-function-body-or-variable.md) der Funktion einschließen. Um dieses Problem zu beheben, stellen Sie sicher, dass Sie eine Definition für alle Klassenmember angeben, die Sie anrufen.

- Es wurde versucht, eine rein virtuelle Funktion aus einer abstrakten Basisklasse aufzurufen. Eine rein virtuelle Funktion verfügt über keine Basisklassen Implementierung. Um dieses Problem zu beheben, stellen Sie sicher, dass alle sogenannten virtuellen Funktionen implementiert sind.

- Es wird versucht, eine Variable zu verwenden, die innerhalb einer Funktion ([einer lokalen Variablen](../../error-messages/tool-errors/automatic-function-scope-variables.md)) außerhalb des Gültigkeits Bereichs dieser Funktion deklariert ist. Um dieses Problem zu beheben, entfernen Sie den Verweis auf die Variable, die sich nicht im Gültigkeitsbereich befindet, oder verschieben Sie die Variable in einen höheren Bereich.

- Wenn Sie eine Releaseversion eines ATL-Projekts erstellen, wird eine Nachricht erstellt, die den CRT-Startcode erfordert. Um dieses Problem zu beheben, führen Sie einen der folgenden Schritte aus:

  - Entfernen Sie `_ATL_MIN_CRT` aus der Liste der Präprozessordefinitionen, damit CRT-Startcode eingefügt werden kann. Weitere Informationen finden Sie unter [Allgemeine Eigenschaften Seite (Projekt)](../../build/reference/general-property-page-project.md).

  - Entfernen Sie nach Möglichkeit Aufrufe von CRT-Funktionen, die CRT-Startcode erfordern. Verwenden Sie stattdessen ihre Win32-Entsprechungen. Verwenden Sie z. B. `lstrcmp` statt `strcmp`. Bekannte Funktionen, die CRT-Startcode erfordern, sind einige der Zeichen folgen-und Gleit Komma Funktionen.

## <a name="consistency-issues"></a>Konsistenzprobleme

Zurzeit gibt es keinen Standard [ C++ ](../../error-messages/tool-errors/name-decoration.md) für die namens Ergänzung zwischen compileranbietern oder sogar zwischen verschiedenen Versionen desselben Compilers. Objektdateien, die mit anderen Compilern kompiliert wurden, verwenden möglicherweise nicht dasselbe Benennungs Schema. Das verknüpfen kann zu Fehlern führen, LNK2001.

Das [Mischen von Inline-und nicht-Inline-Kompilierungsoptionen](../../error-messages/tool-errors/function-inlining-problems.md) für verschiedene Module kann LNK2001 verursachen. Wenn eine C++ Bibliothek mit aktivierter Funktion Inlining ( **/ob1** oder **/Ob2**) erstellt wird, aber in der entsprechenden Header Datei, die die Funktionen beschreibt, das Inlining deaktiviert ist (kein `inline` Schlüsselwort), tritt dieser Fehler auf. Um dieses Problem zu beheben, definieren Sie die Funktionen `inline` in der Header Datei, die Sie in andere Quelldateien einschließen.

Wenn Sie die `#pragma inline_depth` Compiler-Direktive verwenden, stellen Sie sicher, dass Sie den [Wert 2 oder höher](../../error-messages/tool-errors/function-inlining-problems.md)festgelegt haben, und stellen Sie sicher, dass Sie auch die [/ob1](../../build/reference/ob-inline-function-expansion.md) -oder [/Ob2](../../build/reference/ob-inline-function-expansion.md) -Compileroption verwenden.

Dieser Fehler kann auftreten, wenn Sie die Link Option/NOENTRY beim Erstellen einer reinen Ressourcen-DLL weglassen. Um dieses Problem zu beheben, fügen Sie dem Link-Befehl die Option/NOENTRY hinzu.

Dieser Fehler kann auftreten, wenn Sie in Ihrem Projekt falsche/Subsystem-oder/Entry-Einstellungen verwenden. Wenn Sie z. b. eine Konsolenanwendung schreiben und/Subsystem: Windows angeben, wird ein nicht aufgelöster externer Fehler für `WinMain`generiert. Um dieses Problem zu beheben, stellen Sie sicher, dass Sie die Optionen mit dem Projekttyp vergleichen. Weitere Informationen zu diesen Optionen und Einstiegspunkten finden Sie unter den Linkeroptionen [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) und [/Entry](../../build/reference/entry-entry-point-symbol.md) .

## <a name="exported-def-file-symbol-issues"></a>Probleme beim Exportieren von DEF-Datei Symbolen

Dieser Fehler tritt auf, wenn ein in einer DEF-Datei aufgeführter Export nicht gefunden wurde. Dies kann daran liegen, dass der Export nicht vorhanden ist, falsch geschrieben ist C++ oder ergänzte Namen verwendet. Eine DEF-Datei nimmt keine ergänzten Namen. Um dieses Problem zu beheben, entfernen Sie nicht benötigte Exporte, und verwenden Sie `extern "C"` Deklarationen für exportierte Symbole.

## <a name="use-the-decorated-name-to-find-the-error"></a>Verwenden Sie den ergänzten Namen, um den Fehler zu finden

Der C++ Compiler und der Linker verwenden die [namens](../../error-messages/tool-errors/name-decoration.md)Ergänzung, auch bekannt als *Name-Mangling*. Bei der namens Ergänzung werden zusätzliche Informationen über den Typ einer Variablen in ihren Symbolnamen codiert. Der Symbol Name für eine Funktion codiert den Rückgabetyp, die Parametertypen, den Gültigkeitsbereich und die Aufruf Konvention. Dieser ergänzte Name ist der Symbol Name, der vom Linker zum Auflösen externer Symbole gesucht wird.

Ein Link Fehler kann auftreten, wenn die Deklaration einer Funktion oder Variablen nicht *exakt* mit der Definition der Funktion oder Variablen übereinstimmt. Das liegt daran, dass jeder Unterschied zu einem Teil des Symbol namens wird. Der Fehler kann auch auftreten, wenn dieselbe Header Datei sowohl im aufrufenden Code als auch im definierenden Code verwendet wird. Eine Möglichkeit besteht darin, die Quelldateien mit unterschiedlichen Compilerflags zu kompilieren. Beispielsweise, wenn Ihr Code für die Verwendung der `__vectorcall` Aufruf Konvention kompiliert wird, Sie jedoch eine Verknüpfung zu einer Bibliothek herstellen, die erwartet, dass Clients Sie mithilfe der standardmäßigen `__cdecl` oder `__fastcall` Aufruf Konvention aufrufen. In diesem Fall stimmen die Symbole nicht überein, da die Aufruf Konventionen unterschiedlich sind.

Um die Ursache zu finden, werden in der Fehlermeldung zwei Versionen des Namens angezeigt. Dabei werden sowohl der "Anzeige Name", der im Quellcode verwendete Name als auch der ergänzte Name (in Klammern) angezeigt. Sie müssen nicht wissen, wie der ergänzte Name interpretiert werden soll. Sie können nach wie vor nach anderen ergänzten Namen suchen und diese vergleichen. Befehlszeilen Tools können dabei helfen, den erwarteten Symbolnamen und den eigentlichen Symbolnamen zu finden und zu vergleichen:

- Die Optionen [/Exports](../../build/reference/dash-exports.md) und [/Symbols](../../build/reference/symbols.md) des DUMPBIN-Befehlszeilen Tools sind hier nützlich. Sie können Sie dabei unterstützen, herauszufinden, welche Symbole in den dll-und Objekt-oder Bibliotheksdateien definiert sind. Mithilfe der Symbolliste können Sie überprüfen, ob die exportierten ergänzten Namen den ergänzten Namen entsprechen, nach denen der Linker sucht.

- In einigen Fällen kann der Linker nur den ergänzten Namen für ein Symbol melden. Sie können das Befehlszeilen Tool "undname" verwenden, um die nicht ergänzte Form eines ergänzten Namens zu erhalten.

## <a name="additional-resources"></a>Weitere Ressourcen

Weitere Informationen finden Sie in der Stack Overflow Frage ["Was ist ein nicht definierter Verweis/nicht aufgelöstes externes Symbol, und wie kann ich das Problem beheben?"](https://stackoverflow.com/q/12573816/2002113).
